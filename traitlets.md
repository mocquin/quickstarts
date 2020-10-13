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