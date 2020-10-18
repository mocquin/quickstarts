# traitlets

 - https://github.com/gclen/python-tutorials/blob/master/tutorials/traitlets.md
 - https://coderzcolumn.com/tutorials/python/traitlets-eventful-classes-in-python



# Simple example

Example without type-constraints : 
```python
class Student:
    def __init__(self, studentId, studentName):
        self.studentId = studentId
        self.studentName = studentName

student1 = Student(1, "Donald")
```
Use of traits to constraint types : 
```python
class Student(traitlets.HasTraits):
    studentId = traitlets.Int()
    studentName = traitlets.Unicode()

    def __init__(self, studentId, studentName):
        self.studentId = studentId
        self.studentName = studentName

student3 = Student(2, "Putin")
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

# Usage
Any class with trait attributes must inherit from HasTraits. For the list of available trait types and their properties, see the Trait Types section of the documentation.