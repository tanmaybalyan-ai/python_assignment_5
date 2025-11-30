# python_assignment_5
a) Base class Person with attributes name and age, and a method to display them.
#Base class Person
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display1(self):
        print(self.name)
        print(self.age)

# Derived class Student
class Student(Person):
    def __init__(self, course, name, age):
        self.course = course

        Person.__init__(self, name, age)

# Derived class Exam
class Exam(Student):
    def __init__(self, marks, course, name, age):
        self.marks = marks
        self.total = 0

        Student.__init__(self, course, name, age)

#Computing total marks
    def compute_total(self):
        for i in self.marks:
            self.total = sum(self.marks)

#Display of complete details
    def display_details(self):
        self.compute_total()
        print(f"Name: {self.name}, Age: {self.age}, Course: {self.course}, Marks of three subjects: {self.marks}, Total computation: {self.total}")

#Instance of class Exam
obj =Exam([98, 90, 95], "BCA(AI & DS)", "Tanmay", 17)
output:
Name: Tanmay, Age: 17, Course: BCA(AI & DS), Marks of three subjects: [98, 90, 95], Total computation: 283
b) Derived class Student adding the attribute course
# Derived class Student from Person
class Student(Person):
    def __init__(self, name, age, course):
        super().__init__(name, age)
        self.course = course

    def display_student(self):
        self.display_person()
        print("Course:", self.course)
        c) Derived class Exam including marks for three subjects and total computation
        # Derived class Exam from Student
class Exam(Student):
    def __init__(self, name, age, course, m1, m2, m3):
        super().__init__(name, age, course)
        self.m1 = m1
        self.m2 = m2
        self.m3 = m3
        self.total = m1 + m2 + m3

    def display_exam(self):
        self.display_student()
        print("Marks:", self.m1, self.m2, self.m3)
        print("Total Marks:", self.total)
        d) Instantiation of Exam class with sample data and display of complete details
        # Instantiating Exam class with sample data
obj = Exam("Tanmay", 20, "Computer Science", 85, 90, 88)

# Displaying complete details
obj.display_exam()

#method call of class Exam using object
obj.display_details()
