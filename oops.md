Q1. What is the purpose of Python's OOP?

ans- The purpose of Object oriented programming is to create objects which are real life entities having some properties and some functions which tells them about their characteristics and their behaviour. The object oriented programming helps relating to  real life scenarios very well and increase the code reusability.

Q2. Where does an inheritance search look for an attribute?

ans- The inheritance search for an attribute starts with the object's own attributes then followed by current class attributes and then the search goes to the parent classes left to right .

Q3. How do you distinguish between a class object and an instance object?

ans- A class object is a object that is created once the class has been defined while a instance object is created manually by the user. The class object can only access static memebrs and functions of the class  .

```
class new:
    d=10                # static member of the class 
    def __init__(self,a):
        self.a=a
        
print(new)

x=new(10)
print(x)

output:
<class '__main__.new'>
<__main__.new object at 0x7f52cf44af10>

```

Q4. What makes the first argument in a class’s method function special?

ans - The first parameter or argument of the class function is the self argument which is used to refer to the object that is calling the function of this class.The self argument is not needed to be passed while calling this function.
```
class new:
    d=10               
    def __init__(self,a):
        self.a=a
    def print(self):
        print(self.a)

x=new(10)
x.print()
```

Q5. What is the purpose of the init method?

ans- The init method is used to intialise the values of the variables of the class . It is the first function to be called after creating a instance of the class . 
```
class new:
    d=10               
    def __init__(self,a):
        self.a=a
    def print(self):
        print(self.a)

x=new(10)           # after creating the instance x the function init is called and the variable a is intialised with value 10
x.print()
```

Q6. What is the process for creating a class instance?

ans - The class instance is created by using the name of class followed by the round brackets "()".
Q7. What is the process for creating a class?

ans - To create a class we need to use the keyword class followed by the class name with a colon (:) to define the body of the class. The class data members and functions are declared after that . 
```
class new :             ## class keyword followed by the class name and then : to define the body of class
          
    def __init__(self,a):  ## init method to intialise the class members 
        self.a=a
    def print(self):       ## defining functions of the class   
        print(self.a)

x=new(10)                   ## creating the instance object of the class 
x.print()
``` 

Q8. How would you define the superclasses of a class?

ans- The superclass of a class is the parent of that class . The child class will inherit all the properties of the super class . 
```
class Person:                                           ## The superclass or the parent class

    def __init__(self,name,age):
        self.name=name
        self.age=age
    def print_person(self):
        print(self.name,"is ",self.age,"years old.")

class Student(Person):                                  ## The sub class or the child glass
    def __init__(self,name,age,roll_no,course):
        super().__init__(name,age)
        self.roll_no=roll_no
        self.course=course
        
    def print_student(self):
        print(self.name,"is ",self.age,"years old.",self.name,"is enrolled in",self.course,"Course.")

s1=Student("Tajbar",23,401,"BTech")
s1.print_student()
s1.print_person()

```

Q9. What is the relationship between classes and modules?

ans - classes in python are blueprint or template of the class objects which help us to initialize the entities of the same type . Modules on the other hand are python files that contains functions and classes inside it that can be used in another python program .The classes and modules enhances reusability of code . The modules in python may contain one or more classes in it.

Q10. How do you make instances and classes?

ans - A class is created by using the keyword "class" followed by the name of the class and then the attributes ,methods in the class . A instance of a class is created using the name of the class followed by the round brackets "()".

```
class Person:                                           ## The class defination

    def __init__(self,name,age):
        self.name=name
        self.age=age
    def print_person(self):
        print(self.name,"is ",self.age,"years old.")
p1=Person()                                             ## The instance
```

Q11. Where and how should be class attributes created?

ans -  The class attributres are attributes that belong to the class and not to any instance of that class. The class attributes are defined in the body of the class rather than the init method . 
```
class Person:                                           ## The class defination
    is_adult=True                                         ## class attribute
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def print_person(self):
        print(self.name,"is ",self.age,"years old.")

p1=Person()                                             ## The instance
print(Person.is_adult)                                   ## accessing the class attribute
```

Q12. Where and how are instance attributes created?

ans -  The instance attributres are attributes that belong to individual instances of the class . The instance attributes are defined in the body of the init method of the class . 
```
class Person:                                           ## The class defination
    is_adult=True                                         ## class attribute
    def __init__(self,name,age):
        self.name=name                                     ## instance attribute 
        self.age=age
    def print_person(self):
        print(self.name,"is ",self.age,"years old.")

p1=Person()                                             ## The instance
print(Person.is_adult)                                   ## accessing the class attribute
```

Q13. What does the term "self" in a Python class mean?

ans - The self keyword in Python refers to the instance of the class that is currently calling the method of the class .

Q14. How does a Python class handle operator overloading?

ans - In python operator overloading helps in giving a operator a different meaning other then its predefined meaning for the classes by the user.This is done by defining special function also called as magic functions that tells the compiler how to compute the result of that operator when applied to instances of that class.

```
# Python Program illustrate how
# to overload an binary + operator
# And how it actually works

class A:
	def __init__(self, a):
		self.a = a

	# adding two objects
	def __add__(self, o):
		return self.a + o.a
ob1 = A(1)
ob2 = A(2)

print(ob1 + ob2)

# Actual working when Binary Operator is used.
print(A.__add__(ob1 , ob2))

#And can also be Understand as :
print(ob1.__add__(ob2))

```

Q15. When do you consider allowing operator overloading of your classes?

ans - Operator overloading is useful to define specific functionality to the classes that are defined by the user . for e.g - A class defined as student has a attribute total marks , now to calculate the average marks of more than two students we need to get sum of all total marks of each student , so operator overloading helps us to define the add function here that makes the compiler understand what to do when adding two objects of the student class.

```
class Student:                                           ## The class defination
    
    def __init__(self,name,marks):
        self.name=name
        self.marks=marks
    def __add__(self,student2):
        return self.marks+student2.marks
        
s1=Student("Tajbar",96)
s2=Student("Shubham",93)
print(s1+s2)
```

Q16. What is the most popular form of operator overloading?

ans- 

Q17. What are the two most important concepts to grasp in order to comprehend Python OOP code?

ans - The two important concepts of OOPS are inheritence and polymorphism that gives python the power of formulate the real world situations in code . With Inheritance the python code enhances the reusability of the code and with polymorphism we get different functionality with the same function name . 

Q18. Describe three applications for exception processing.

ans - 1. Using exception handling to validate the input of the user .for e.g we can validate if the user has given in the input in correct form of not .
      2. while accessing resources and files try except blocks can help us to prevent any exceptions from being raised in case of the connection is not established or a file is not found.
      3. using exception handling we can safely access the database through our python code without running into any exceptions due to wrong passwords or port numbers .

Q19. What happens if you don't do something extra to treat an exception?

ans - If we don't treat an exception using the except block the program can stop abruptly without any reason if the exception gets raised ,making it hard to rectify the problem.

Q20. What are your options for recovering from an exception in your script?

ans - Exceptions are unexpected events that disrupt the normal control flow of your script.To prevent the program from stopping abruptly one needs to consider every possible origin of exception and handle them properly so it can be rectified with proper care with the help of try and except block which can be followed by a finally or else block.

Q21. Describe two methods for triggering exceptions in your script.

ans- The two methods for triggering exception are -
    1.raise method
       raise Keyword is used to raise exceptions or errors. The raise keyword raises an error and stops the control flow of the program.
       ```
    s = 'apple'

    try:
        num = int(s)
    except ValueError:
	    raise ValueError("String can't be changed into integer")

       ```      
    2.assert method
        assert statement is used to continue the execute if the given condition evaluates to True. If the assert condition evaluates to False, then it raises the AssertionError exception with the specified error message.
    ```
    x = 0
    assert x > 0, 'Only positive numbers are allowed'
    print('x is a positive number.')
    ```
 

Q22. Identify two methods for specifying actions to be executed at termination time, regardless of whether or not an exception exists.

ans-There are two methods for specifying actions to be executed at termination time in Python, regardless of whether or not an exception exists:

    1.Using finally block:  This block of code can be used in conjunction with a try-except block, and it will be executed regardless of whether an exception is raised or not. 

    ```
    a=10
    b=int(input())
    try:
        c=a/b
    except :
        print("Dividing by 0")
    finally:
        print("This statement will run no matter what")
    ```


    2.Using with statement: This statement allows you to define a context for a block of code, and specify actions to be taken when the block of code starts and when it ends. 
    For example: with open("file.txt") as f:


Q23. What is the purpose of the try statement?

ans-The try block lets you test a block of code for errors or exceptions.If there are exceptions in that piece of code then except block lets you handle that exception.

```
def divide(x, y):
	try:	
		result = x // y
		print("Yeah ! Your answer is :", result)
	except ZeroDivisionError:
		print("Sorry ! You are dividing by zero ")


divide(3, 0)

```

Q24. What are the two most popular try statement variations?

ans - The two most popular variations of the try statement in Python are the try-except block and the try-finally block.

1.The try-except block: The try-except block is the most commonly used variation of the try statement. It consists of a try block, which is the block of code that you want to test for errors, and one or more except blocks, which specify how to handle any errors that are raised in the try block. 

```
try :
    a=10/0
except:
    print("divides by 0")
```
2.The try-finally block: The try-finally block is another variation of the try statement. It consists of a try block, which is the block of code that you want to test for errors, and a finally block, which specifies code that will be executed regardless of whether an exception is raised or not.
```
try :
    a=10/0
except:
    print("divides by 0")
finally:
    print("this runs no matter what ")
```

Q25. What is the purpose of the raise statement?

ans- Raise Keyword is used to raise exceptions or errors. The raise keyword raises an error and stops the control flow of the program. 

```
a = 0
b=10
if ((b / a)>5) :
	raise Exception("The denominator cannot be 0")

```

Q26. What does the assert statement do, and what other statement is it like?

ans- assert keyword evaluates the boolean expression that checks if the statement is True or False. If the statement is true then it does nothing and continues the execution, but if the statement is False then it stops the execution of the program and throws an error.

```

a = 4
b = 0


print("The value of a / b is : ")
assert b != 0, "Zero Division Error"
print(a / b)

```
Q27. What is the purpose of the with/as argument, and what other statement is it like?

ans - The with/as argument in python are used in exception handling . These arguments ensures proper acquisiton and realease of resources without making additional calls which makes the code compact and more readable.
```
# using with statement
with open('new_file.txt', 'w+') as file:
	file.write('hello world !')

```

Q28. What are *args, **kwargs?
ans - In python *args and **kwargs refer to variable length arguments for a function . The **kwargs is keyworded variable length argument list and *args is non keyword variable length argument list.
```
def adder(*num):
    sum = 0
    
    for n in num:
        sum = sum + n

    print("Sum:",sum)

adder(3,5)
adder(4,5,6,7)

``` 

```
def intro(**data):
    print("\nData type of argument:",type(data))

    for key, value in data.items():
        print("{} is {}".format(key,value))

intro(Firstname="Sita", Lastname="Sharma", Age=22, Phone=1234567890)
intro(Firstname="John", Lastname="Wood", Email="johnwood@nomail.com", Country="Wa
```
Q29. How can I pass optional or keyword parameters from one function to another?


Q30. What are Lambda Functions?

ans- Lambda functions are anonymous functions without a name that are used to do a simple operation .It contains a list of argumnets and returns a value. for e.g 

```
x=lambda a,b : a*b
print(x(5,4))
```
Q31. Explain Inheritance in Python with an example?

ans -  Inheritance allows us to define a class that inherits all the methods and properties from another class. Parent class is the class being inherited from, also called base class.. Child class is the class that inherits from another class, also called derived class.

```
class Person:                                           ## The superclass or the parent class

    def __init__(self,name,age):
        self.name=name
        self.age=age
    def print_person(self):
        print(self.name,"is ",self.age,"years old.")

class Student(Person):                                  ## The sub class or the child glass
    def __init__(self,name,age,roll_no,course):
        super().__init__(name,age)
        self.roll_no=roll_no
        self.course=course
        
    def print_student(self):
        print(self.name,"is ",self.age,"years old.",self.name,"is enrolled in",self.course,"Course.")

s1=Student("Tajbar",23,401,"BTech")
s1.print_student()
s1.print_person()

```
Q32. Suppose class C inherits from classes A and B as class C(A,B).Classes A and B both have their own versions of method func(). If we call func() from an object of class C, which version gets invoked?

ans - The function of the class that is inherited first will be called which is 'A' in this case .

```

class A:
    def my_func(self):
        print("This is A")
        

class B:
    def my_func(self):
        print("This is B")

class C(A,B):
    pass
## The class defination
    
C().my_func()  ## prints "This is A"
 
```

Q33. Which methods/functions do we use to determine the type of instance and inheritance?

ans- To check the instance we can use the function isinstance() with two arguments first one is the object and the second one is the class for which we want to check .Similarly with the help of issubclass() we can check whether or not the first argument is a subclass of the second argument .

```
 
class MyClass(object):
  pass
class MySubClass(MyClass):
  pass
print(isinstance(MySubClass, object))           #prints True
print(issubclass(MySubClass, MyClass))          #Prints True
print(isinstance(MySubClass, MyClass))          #Prints False
```

Q34.Explain the use of the 'nonlocal' keyword in Python.

ans -The nonlocal keyword will not work on local or global variables and therefore must be used to reference variables in another scope except the global and local one. The nonlocal keyword is used in nested functions to reference a variable in the parent function. 

Q35. What is the global keyword?

ans-A global keyword is a keyword that allows a user to modify a variable outside the current scope. It is used to create global variables in Python from a non-global scope, i.e. inside a function. 