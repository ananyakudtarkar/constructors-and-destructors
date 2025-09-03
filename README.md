# Constructors & Destructors in C++
## Aim
To understand, use, and implement C++ Constructors and Destructors, exploring their role in object initialization, cleanup, and lifecycle management.

## Theory
In C++, constructors and destructors are special member functions that manage the lifecycle of an object — from creation to destruction.

## Constructor
A constructor is a special member function that is automatically invoked when an object of a class is created.
Its main purpose is to initialize the object’s data members and ensure it starts in a valid state.

Key Characteristics:

Name: Same as the class name.<br>
Return type: None (not even void).<br>
Automatic call: Invoked when an object is created.<br>
Overloading: Multiple constructors can exist with different parameter lists.<br>
Access specifier: Usually public for object creation.<br>

Types of Constructors:

Default Constructor – No parameters; sets default or user‑input values.
Parameterized Constructor – Accepts arguments to set specific values.
Copy Constructor – Creates a new object as a copy of an existing object.
Delegating Constructor (C++11+) – Calls another constructor in the same class.
Explicit Constructor – Prevents implicit conversions.

## Destructor
A destructor is a special member function that is automatically invoked when an object’s lifetime ends.
Its main purpose is to release resources acquired during the object’s existence.

Key Characteristics:

Name: Same as the class name but prefixed with ~.
Return type: None.
Parameters: None.
Overloading: Not allowed — only one destructor per class.
Responsibilities:

Free dynamically allocated memory.
Close files or network connections.
Release locks or other system resources.
Perform logging or cleanup tasks.
Order of Destruction:

Local objects: destroyed in reverse order of creation when scope ends.
Global/static objects: destroyed in reverse order of construction at program termination.
Inheritance: derived class destructor runs first, then base class destructor.
## Constructor–Destructor Lifecycle
Memory Allocation (if dynamic).
Constructor Call → Initialization.
Object Usage → Program logic.
Destructor Call → Cleanup.
Memory Deallocation (if dynamic).
This follows the RAII principle (Resource Acquisition Is Initialization), ensuring safe and automatic resource management.

## Algorithms
Destructor with Global Counter<br>
Start<br>
Declare a global integer count = 0 to track the number of objects.<br>
Define a class Student with:<br>
Constructor: Increment count and display "No of objects created: " followed by count.<br>
Destructor: Decrement count and display "No of objects destroyed: " followed by the updated count.<br>
In main():<br>
Create three objects: aa, bb, cc.<br>
Enter a nested scope {}:<br>
Create one object dd.<br>
When scope ends, dd is destroyed and destructor runs.<br>
At the end of main(), cc, bb, and aa are destroyed in reverse order.<br>
End<br>


Copy Constructor<br>
Start<br>
Define a class Student with private members: name, age, roll_no.<br>
Create a parameterized constructor to initialize these members.<br>
Create a copy constructor that:<br>
Copies values from another Student object.<br>
Displays "Copy constructor called!".<br>
Create a display() method to print the object’s details.<br>
In main():<br>
Create object s1 using the parameterized constructor.<br>
Display s1’s details.<br>
Create object s2 as a copy of s1 (invokes copy constructor).<br>
Display s2’s details.<br>
End
<br>

Parameterized Constructor<br>
Start<br>
Define a class Date with private members: d, m, y.<br>
Create a parameterized constructor that:<br>
Accepts day, month, year as arguments.<br>
Assigns them to d, m, y.<br>
Create a display() method to print the date in d/m/y format.<br>
In main():<br>
Prompt the user to enter day, month, and year.<br>
Create object d1 using the parameterized constructor.<br>
Call display() to show the date.<br>
End<br>


Default Constructor<br>
Start<br>
Define a class Student with private members: name, fee.<br>
Create a default constructor that:<br>
Prompts the user to enter the student’s name.<br>
Prompts the user to enter the fee.<br>
Stores these values in the object’s members.<br>
Create a display() method to print the stored details.<br>
In main():<br>
Create object s (default constructor runs automatically).<br>
Call display() to show the details.<br>
End<br>


Basic Constructor & Destructor Lifecycle<br>
Start<br>
Define a class with:<br>
Constructor: Displays a message when an object is created.<br>
Destructor: Displays a message when an object is destroyed.<br>
In main():<br>
Create one or more objects to trigger constructor calls.<br>
Optionally, create objects inside a nested scope to see early destruction.<br>
Observe that destructors are called in reverse order of creation.<br>
End<br>


## Conclusion
This experiment demonstrates the importance of constructors and destructors in managing the lifecycle of C++ objects.
Constructors → Ensure proper initialization.
Destructors → Ensure proper cleanup.
