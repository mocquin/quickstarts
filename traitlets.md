# traitlets

 - doc : https://traitlets.readthedocs.io/en/stable/
 - https://github.com/gclen/python-tutorials/blob/master/tutorials/traitlets.md
 - https://coderzcolumn.com/tutorials/python/traitlets-eventful-classes-in-python

# Concept

Lacks in python : 
 - no typed values
 - hence, no default values (ex: for int, coulbd be 0 or None)
 - no callbacks/watch on attributes, which can ben called on attribute change

The traitlets package implements easy : 
 - typed values
 - type-checking 
 - default value
 - validation value checking
 - callback/watch


To create a class whose attributes are typed, it must inherit from `trailets.HasTraits`.
A class that inerhits from `traitlets.HasTraits`can be seen as having typed-attributes.
For the list of available trait types and their properties, see the [Trait Types section of the documentation](https://traitlets.readthedocs.io/en/stable/trait_types.html).


By default, if not attribute is set in the `__init__` method, the default values of the traits are used : 
 - 0 for traitlets.Int
 - "" for traitlets.Unicode
 
To override a default value for a trait, use the `traitlets.default("attribute_name")` to compute the default value :

```python
class Student(traitlets.HasTraits):
    studentId = traitlets.Int()
    studentName = traitlets.Unicode()

    def __init__(self, studentId):
        self.studentId = studentId

    @traitlets.default("studentName")
    def _get_default_name(self):
        return "Pappu"
```


# Simple example

Example without type-constraints : 
```python
class Student:
    def __init__(self, studentId, studentName):
        self.studentId = studentId
        self.studentName = studentName

student1 = Student(1, "Donald")
```
Here, anything can be done on `student1`, like assigning a str to its Id atribute, and float to its name attribute. Python does not enforce any type constraint or validation on the Student attributes.

Inherit from `traitelets.HasTraits`to enforce types of attributes :
```python
class Student(traitlets.HasTraits):
    studentId = traitlets.Int()
    studentName = traitlets.Unicode()

    def __init__(self, studentId, studentName):
        self.studentId = studentId
        self.studentName = studentName

student3 = Student(2, "Putin")
print("Student ID : ", student3.studentId)
print("Student Name : ", student3.studentName)
>>> 2
>>> Putin
```
Here, the `studentId`will always be of type `Int` and `studentName` will always be of type `string` (or Unicode) : the check is done at creation or when trying to change its value. If type is not respected, it will raise an exception :
```python
try:
    student3.studentId = 1.5
except Exception as e:
    print(e)
>>> The 'studentId' trait of a Student instance must be an int, but a value of 'Fake' <class 'str'> was specified.
```

Example showing default values : 
```python
class Student(traitlets.HasTraits):
    studentId = traitlets.Int()
    studentName = traitlets.Unicode()

    def __init__(self):
        pass

student5 = Student()

print("Student ID : ", student5.studentId)
print("Student Name : ", student5.studentName)
>>> 0
>>>  #empty string
```

Override default traits values : 
```python
class Student(traitlets.HasTraits):
    studentId = traitlets.Int()
    studentName = traitlets.Unicode()

    def __init__(self, studentId):
        self.studentId = studentId

    @traitlets.default("studentName")
    def _get_default_name(self):
        return "Pappu"

student6 = Student(2)

print("Student ID : ", student6.studentId)
print("Student Name : ", student6.studentName)
```

# Class example
```python
import traitlets

class Dude(traitlets.HasTraits):
    """
    By default, a Dude is 20 and called Senior Dude.
    """
    name = traitlets.Unicode()
    age = traitlets.Int()

    @traitlets.default("name")
    def _get_default_name(self):
        return "Senior Dude"
    
    @traitlets.default("age")
    def _get_default_age(self):
        return 20

    def __repr__(self):
        return f"Dude: {self.name}, {self.age}"
    
dude_jean = Dude(name="Jean", age=28)
dude_default = Dude()
print(dude_jean)
print(dude_default)
>>> Dude: Jean, 28
>>> Dude: Senior Dude, 20
```


# observing

The HasTraits defines a method/decorator called `observe` to watch any change on the object attribute. This can be used to do work when an attribute changes. There are 2 ways to do this : 
 - set an observe on a object instance with its `.observe` method : 
```python
student7.observe(monitor_address_change, names=["studentAddress"])
```
 - set an method in the class with the `traitlets.observe` decorator : 
```python
@traitlets.observe("studentAddress", "studentName") # observe 2 attributes
    def monitor_address_change(self, addr_change_details):
        # do something
```
 
In all cases, the callbacks function will receive a `change` dictionnary containing the old and new values of the attribute within `change["old"]` and `change["new"]`.

## observing on a single instance
First way to observe an attribute : by setting a function outside the class on an instance's attribute name, in 2 steps :
 - step 1 : define what to do, with a function
 - step 2 : define the association which instance to watch / what to do / for what attribute

```python
class Student(traitlets.HasTraits):
    studentId = traitlets.Int()
    studentName = traitlets.Unicode()
    studentAddress = traitlets.Dict()

    def __init__(self, studentId, studentName):
        self.studentId = studentId
        self.studentName = studentName

# step 1 : define what to do
def monitor_address_change(addr_change_details):
    print(addr_change_details)
    print("Old Address : ", addr_change_details["old"])
    print("New Address : ", addr_change_details["new"])


student7 = Student(7, "Angela")

# step 2 : define the association : which instance / what to do / for what attribute
student7.observe(monitor_address_change, names = ["studentAddress"])
```

## observing on all instances
Second way is to define an observe method in the class using a decorator : the method defines what todo, the decorator defines which attribute to observe

```python
class Student(traitlets.HasTraits):
    studentId = traitlets.Int()
    studentName = traitlets.Unicode()
    studentAddress = traitlets.Dict()

    def __init__(self, studentId, studentName):
        self.studentId = studentId
        self.studentName = studentName

    @traitlets.observe("studentAddress")
    def monitor_address_change(self, addr_change_details):
        print("Old Address : ", addr_change_details["old"])
        print("New Address : ", addr_change_details["new"])

student8 = Student(7, "Boris")

```

## observing multiple attributes

Multiple attributes can be observed with the same method by passing a tuple of attributes names to the decorator:

```python
class Student(traitlets.HasTraits):
    studentId = traitlets.Int()
    studentName = traitlets.Unicode()
    studentAddress = traitlets.Dict()

    def __init__(self, studentId):
        self.studentId = studentId

    @traitlets.observe("studentAddress", "studentName")
    def monitor_address_change(self, change_details):
        print("Old Data : ", change_details["old"])
        print("New Data : ", change_details["new"])

student9 = Student(7)
```


# validation
Validation further type-checking can be done through the `validate` decorator :

```python
    @traitlets.validate("studentId")
    def _validate_id(self, student_id_details):
        # do something on student_id_details["value"]
        return student_id_details["value"]
```


# Define new trait from TraitType
 - https://traitlets.readthedocs.io/en/stable/defining_traits.html
 
TraitType.error(obj, value) is used to say that value is not of type obj.
 
```python
class TCPAddress(TraitType):
    """A trait for an (ip, port) tuple.

    This allows for both IPv4 IP addresses as well as hostnames.
    """

    default_value = ('127.0.0.1', 0)
    info_text = 'an (ip, port) tuple'

    def validate(self, obj, value):
        if isinstance(value, tuple):
            if len(value) == 2:
                if isinstance(value[0], str) and isinstance(value[1], int):
                    port = value[1]
                    if port >= 0 and port <= 65535:
                        return value
        self.error(obj, value)

    def from_string(self, s):
        if self.allow_none and s == 'None':
            return None
        if ':' not in s:
            raise ValueError('Require `ip:port`, got %r' % s)
        ip, port = s.split(':', 1)
        port = int(port)
        return (ip, port)
```
