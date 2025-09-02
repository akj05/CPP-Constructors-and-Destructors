
📚 Theory

In C++, constructors and destructors are special member functions that manage the lifecycle of an object — from creation to destruction.


🏗️ Constructor

A constructor is a special member function that is automatically invoked when an object of a class is created.

Its main purpose is to initialize the object’s data members and ensure it starts in a valid state.

Key Characteristics:

Name: Same as the class name.

Return type: None (not even void).

Automatic call: Invoked when an object is created.

Overloading: Multiple constructors can exist with different parameter lists.

Access specifier: Usually public for object creation.

Types of Constructors:

Default Constructor – No parameters; sets default or user‑input values.

Parameterized Constructor – Accepts arguments to set specific values.

Copy Constructor – Creates a new object as a copy of an existing object.

Delegating Constructor (C++11+) – Calls another constructor in the same class.

Explicit Constructor – Prevents implicit conversions.

🗑️ Destructor

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

🔄 Constructor–Destructor Lifecycle

Memory Allocation (if dynamic).

Constructor Call → Initialization.

Object Usage → Program logic.

Destructor Call → Cleanup.

Memory Deallocation (if dynamic).

This follows the RAII principle (Resource Acquisition Is Initialization), ensuring safe and automatic resource management.


📋 Algorithms

🧾 Destructor with Global Counter

Start

Declare a global integer count = 0 to track the number of objects.

Define a class Student with:

Constructor: Increment count and display "No of objects created: " followed by count.

Destructor: Decrement count and display "No of objects destroyed: " followed by the updated count.

In main():

Create three objects: aa, bb, cc.

Enter a nested scope {}:

Create one object dd.

When scope ends, dd is destroyed and destructor runs.

At the end of main(), cc, bb, and aa are destroyed in reverse order.

End

📋 Copy Constructor

Start

Define a class Student with private members: name, age, roll_no.

Create a parameterized constructor to initialize these members.

Create a copy constructor that:

Copies values from another Student object.

Displays "Copy constructor called!".

Create a display() method to print the object’s details.

In main():

Create object s1 using the parameterized constructor.

Display s1’s details.

Create object s2 as a copy of s1 (invokes copy constructor).

Display s2’s details.

End

📅 Parameterized Constructor

Start

Define a class Date with private members: d, m, y.

Create a parameterized constructor that:

Accepts day, month, year as arguments.

Assigns them to d, m, y.

Create a display() method to print the date in d/m/y format.

In main():

Prompt the user to enter day, month, and year.

Create object d1 using the parameterized constructor.

Call display() to show the date.

End

🧑‍🎓 Default Constructor

Start

Define a class Student with private members: name, fee.

Create a default constructor that:

Prompts the user to enter the student’s name.

Prompts the user to enter the fee.

Stores these values in the object’s members.

Create a display() method to print the stored details.

In main():

Create object s (default constructor runs automatically).

Call display() to show the details.

End

🔄 Basic Constructor & Destructor Lifecycle

Start

Define a class with:

Constructor: Displays a message when an object is created.

Destructor: Displays a message when an object is destroyed.

In main():

Create one or more objects to trigger constructor calls.

Optionally, create objects inside a nested scope to see early destruction.

Observe that destructors are called in reverse order of creation.

End

🧠 Conclusion

This experiment demonstrates the importance of constructors and destructors in managing the lifecycle of C++ objects.


🏗️ Constructors → Ensure proper initialization.
🗑️ Destructors → Ensure proper cleanup.
✅ Key Insights:
Different constructor types serve different initialization needs.
Destructors are crucial for resource management.
Together, they implement RAII for safer, cleaner code.
