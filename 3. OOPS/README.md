# Object-oriented programming (OOP)

> **Object-oriented programming (OOP) is a programming paradigm that focuses on creating objects that interact with one another to accomplish a specific task. C++ is a powerful object-oriented programming language that supports many OOP concepts. Some of the key concepts of OOP in C++ include:**

## 1. Classes and objects: 
A class is a blueprint for creating objects, while an object is an instance of a class. Classes can have member variables (also called attributes or properties) and member functions (also called methods). In C++, classes are defined using the `class` keyword, and objects are created using the `new` keyword. 
Here is an example of a simple C++ class:

```cpp
class Person {
  private:
    string name;
    int age;
    
  public:
    void setName(string n) {
      name = n;
    }
    
    void setAge(int a) {
      age = a;
    }
    
    string getName() {
      return name;
    }
    
    int getAge() {
      return age;
    }
};
```
In this example, the Person class has two private member variables (`name` and `age`) and four public member functions (`setName`, `setAge`, `getName`, and `getAge`). The private member variables are hidden from the outside world and can only be accessed by the public member functions.

To create an object of the Person class, we can use the following code:

```cpp
Person* person = new Person();
person->setName("John");
person->setAge(30);
cout << person->getName() << " is " << person->getAge() << " years old." << endl;
```
This code creates a new Person object and sets its name and age using the `setName` and `setAge` functions. It then uses the `getName` and `getAge` functions to retrieve the values of the object's properties and print them to the console.

## 2. Encapsulation: 
 In C++, encapsulation is achieved by declaring class data members as private and providing public member functions (also called accessors or getters) to access and modify these private data members.

Here is an example of encapsulation in C++:
```cpp
class Employee {
private:
    int employeeId;
    std::string employeeName;
    double salary;

public:
    void setEmployeeId(int id) {
        employeeId = id;
    }
    void setEmployeeName(std::string name) {
        employeeName = name;
    }
    void setSalary(double sal) {
        salary = sal;
    }
    int getEmployeeId() const {
        return employeeId;
    }
    std::string getEmployeeName() const {
        return employeeName;
    }
    double getSalary() const {
        return salary;
    }
};
```

In this example, the `Employee` class has three private member variables: `employeeId`, `employeeName`, and `salary`. These variables are not accessible from outside the class, and can only be accessed or modified through the public member functions `setEmployeeId`, `setEmployeeName`, and `setSalary`.

The public member functions also include three getter functions `getEmployeeId`, `getEmployeeName`, and `getSalary`, which allow external code to retrieve the values of the private member variables, but not to modify them directly.

## 3. Inheritance: 
Inheritance is a mechanism in which a new class is created by deriving properties from an existing class. The new class, called the `derived class`, inherits the properties of the existing class, called the `base class`. In C++, inheritance is achieved using the public, private, and protected access specifiers.

```cpp
// Base class
class Shape {
   public:
      void setWidth(int w) {
         width = w;
      }
      void setHeight(int h) {
         height = h;
      }
   protected:
      int width;
      int height;
};

// Derived class
class Rectangle: public Shape {
   public:
      int getArea() {
         return (width * height);
      }
};

int main() {
   Rectangle Rect;

   Rect.setWidth(5);
   Rect.setHeight(7);

   // Print the area of the object.
   cout << "Total area: " << Rect.getArea() << endl;

   return 0;
}
```

In this example, we have a base class called `Shape` which has two properties, `width` and `height` and two methods to set these properties. We then define a derived class called `Rectangle` which inherits from the `Shape` class using the `public` access specifier. 
This means that all the public members of the base class will be accessible in the derived class. In this case, the `Rectangle` class only adds one method called `getArea` which calculates and returns the area of the rectangle.

In the main function, we create an object of the `Rectangle` class and set its width and height using the methods inherited from the base class. We then call the `getArea` method of the `Rectangle` object and print the result.

## 4. Polymorphism: 
Polymorphism is the ability of an object to take on multiple forms. In C++, polymorphism is achieved through function overloading (creating multiple functions with the same name but different parameter lists) and virtual functions (functions that can be overridden by derived classes).

```cpp
// Base class
class Shape {
   protected:
      int width;
      int height;
   public:
      Shape(int w, int h) {
         width = w;
         height = h;
      }
      virtual int getArea() {
         return 0;
      }
};

// Derived class
class Rectangle: public Shape {
   public:
      Rectangle(int w, int h): Shape(w, h) {}
      int getArea() {
         return (width * height);
      }
};

// Derived class
class Triangle: public Shape {
   public:
      Triangle(int w, int h): Shape(w, h) {}
      int getArea() {
         return (width * height / 2);
      }
};

int main() {
   Shape *shape;
   Rectangle rec(10, 7);
   Triangle tri(10, 5);

   // Store the address of Rectangle
   shape = &rec;
   // Call Rectangle area
   cout << "Rectangle area: " << shape->getArea() << endl;

   // Store the address of Triangle
   shape = &tri;
   // Call Triangle area
   cout << "Triangle area: " << shape->getArea() << endl;

   return 0;
}
```

In this example, we have a base class called `Shape` which has two properties, `width` and `height` and a virtual method called `getArea` that returns 0. We then define two derived classes called `Rectangle` and `Triangle` which inherit from the `Shape` class and override the `getArea` method to calculate the area of a rectangle and a triangle, respectively.

In the main function, we create objects of the `Rectangle` and `Triangle` classes and store their addresses in a pointer of the `Shape` type. We then call the `getArea` method of the `Shape` pointer, which dynamically resolves the correct method to call based on the actual type of the object pointed to. 
This allows us to treat objects of different classes as if they were the same type and call the same method on them.

## 5. Abstraction: 
Abstraction is the process of reducing complexity by hiding unnecessary details. In C++, abstraction is achieved by creating abstract classes, which have pure virtual functions (functions without implementations) that must be implemented by derived classes.

```cpp
// Abstract base class
class Shape {
   public:
      virtual double getArea() = 0;
};

// Derived class
class Rectangle: public Shape {
   private:
      double width;
      double height;
   public:
      Rectangle(double w, double h) {
         width = w;
         height = h;
      }
      double getArea() {
         return width * height;
      }
};

// Derived class
class Circle: public Shape {
   private:
      double radius;
   public:
      Circle(double r) {
         radius = r;
      }
      double getArea() {
         return 3.14 * radius * radius;
      }
};

int main() {
   Shape *shape;
   Rectangle rec(10, 7);
   Circle cir(5);

   // Store the address of Rectangle
   shape = &rec;
   // Call Rectangle area
   cout << "Rectangle area: " << shape->getArea() << endl;

   // Store the address of Circle
   shape = &cir;
   // Call Circle area
   cout << "Circle area: " << shape->getArea() << endl;

   return 0;
}
```

In this example, we have an abstract base class called `Shape` that defines a pure `virtual function` called `getArea`, which has no implementation and must be overridden by any derived class. We then define two derived classes called `Rectangle` and `Circle` that inherit from the `Shape` class and implement the `getArea` method to calculate the area of a rectangle and a circle, respectively.

In the main function, we create objects of the `Rectangle` and `Circle` classes and store their addresses in a pointer of the `Shape` type. We then call the `getArea` method of the `Shape` pointer, which dynamically resolves the correct method to call based on the actual type of the object pointed to.
This allows us to treat objects of different classes as if they were the same type and call the same method on them, without worrying about their implementation details.

## 6. Constructors and destructors: 
Constructors are special member functions that are called when an object is created, and are used to initialize the object's member variables. Destructors are special member functions that are called when an object is destroyed, and are used to clean up the object's resources.

```cpp
class Person {
   private:
      string name;
      int age;
   public:
      // Constructor
      Person(string n, int a) {
         name = n;
         age = a;
         cout << "Constructor called for " << name << endl;
      }

      // Destructor
      ~Person() {
         cout << "Destructor called for " << name << endl;
      }
};

int main() {
   // Create an object of the Person class
   Person p("John", 25);

   return 0;
}
```
In this example, we define a class called `Person` that has two private properties, `name` and `age`, and a constructor that takes two arguments, `n` and `a`, and initializes the properties with those values. We also define a destructor that prints a message indicating that the object is being destroyed.

In the main function, we create an object of the `Person` class called `p` and pass it the values `John` and 25. When the object is created, the constructor is called and the message `Constructor called for John` is printed. When the program exits, the destructor is called and the message `Destructor called for John` is printed.

Constructors and destructors are important for managing the lifetime of objects and ensuring that they are properly initialized and cleaned up. Constructors are called when an object is created, and destructors are called when an object is destroyed, either explicitly (using the `delete` keyword) or implicitly (when the object goes out of scope or the program exits).


> Overall, object-oriented programming in C++ provides a powerful and flexible way to create complex programs. By using classes and objects to model real-world entities and systems, C++ programmers can write code that is easier to read, maintain, and debug.
