# Week 4 Assessment

### Setup
* Fork and clone this repository
* Open your forked repo in Visual Studio.
* Complete the two exercises and the questions

## Exercise 1: Inheritance and Dependency Injection (8 points)

Open up `Program.cs` and run your program. It should run with no errors, if you get an error reach out to your instructor.

This exercise involves some refactoring and some new features.

**Step 1:** Currently there are two classess `Student` and `Teacher` that have a lot of repeated code between them. Create a new class `Person` that will be the base class. Then update `Student` and `Teacher` to be derived from `Person`. Include as much in your `Person` class as you can to keep your code DRY (Don't Repeat Yourself). 

**Testing Step 1:** Uncomment the code under "Step 1:" in the Main method. That code should now run without error.

**Step 2:** Implement a new class called `School` that uses dependency injection and takes in a list of people as a dependency. Implement a method called `ListBirthdays` in your school class that calls the `GetBirthday` method and prints to the console each student and teacher's birthday.

**Testing Step 2:** Uncomment the code under "Step 2:" in the Main method. That code should now run without error and output a bunch of names and birthdays.

Ungraded extra challenge: If you have time, improve the way the birthdays are output. Can you group them by month or by Student/Teacher?

### Exercise 2: Interfaces (4 points)
Open up `InterfacePractice.cs`. You should not need to run this file, you will just edit it.

**Step 1:** Take a look at the two classes `Car` and `Bicycle`. They both implement an interface called `InterfaceNameHere`. Replace all three uses of `InterfaceNameHere` with a fitting name for this interface.

**Step 2:** The interface has already been created for you on line 5. Fill in the details for any methods and/or properties that make sense based on the two classes implementing this interface.

## Questions (8 points)

Edit this file with your answers.

1. What are some of the benefits of using inheritance? (1 point)
    * `Code Reusability` - Using inheritance allows you to 'inherit' properties and methods of a base class.
	* `Maintenance` - When we update a base class, it updates all classes that are derived from it.
	
2. What might be some of the disadvantages of using inheritance? (1 point)
    * `Maintenance` - While also an advantage, if you make one change in the base class, you may have to change all classes that are derived from it.
	* `Non-Multiple Inheritance` -  C# only supports single inheritance, so attempting to derive a class off of several base classes will not work, this forces us to use other strategies like `interfaces`, which greatly increases the complexity.
	
3. How would you describe the difference between the base class and the derived class when working with inheritance? (1 point)
	* I like to think that the `base class` is the class that sets the guidelines and structure(methods, properties) that the `derived class` **must** use.
	* Another thing to mention is that often times the base class contains empty properties and methods(though it can contain `default` methods and properties), in other words it is an abstract class - the actual implementation of those methods and properties is determined by the derived class.

4.  What happens if you define the same method in the parent class and the child class? (1 point)
	* Whichever is more specific is the method that will be run(similar to css), so if we have identical methods, the method inside of the child class will be run because it is the most specific. Since inheritance allows multiple classes to inherit from the same base class, it is not specific to any class in particular, unlike a method in a child class.
	* Additionally, we can use keywords such as `new` or `override`, to force one method or the other to be run. For instance, if we use `new` when defining a method in the derived class, the method in the base class is hidden. Likewise, if we use `override` when defining a method in the derived class, this will override the base class's method (override is used in conjunction with `polymorphism`).

5. In your own words, how would you define an Interface? (1 point)
    * Similarily to inheritance, interfaces act as structure that classes **must** adopt. The `interface` provides a blueprint of methods, properties, and more that classes can use. One key difference between interfaces and inheritance is that classes can implement multiple interfaces at once, unlike inheritance.

6. Does a class implementing an interface need to implement all of the methods in that interface? Why or why not? (1 point)
    * Yes - a class that use an interface **must** utilize all methods and satisfy all properties definined in the interface.
	* The class must use all methods, so that any class implementing this structure(interface) adheres to the same rules. In otherwords if I have two classes, one is a `House` and the other is a `Shape`, and I implement an interface: `IMath` that contains methods: `CalculateSQFT` and `CalculateArea`. It seems obvious that I would use CalculateSQFT for the House class, and CalculateArea for Shape, however I have to implement both - otherwise I completely break the structure of `IMath`. Additionally, if the compiler or runtime recognizes that something has not been implemented it can greatly reduce performance and functionality.

7. Both Inheritance and Interfaces use the `:` symbol after a class name. If you're looking at a class, what's one thing that can help you determine if the class is implementing an interface of extending a base class? (1 point)
	* The best way to tell is by understanding the industry convention. For Interfaces its "required" to use an I before the name, for instance: `IMyInterface`. Another way to tell, is if the class has multiple implementationsl, since a class can only inherit one base class, if there are multiple implementations (i.e `MyClass : IMyInterface, IMyInterface2`) it must be an interface.

8. If asked in an interview, how would you describe the purpose of the IOC container in a .NET application? (1 point)
	* an Inversion of Control container is a tool that manages dependencies in the application. IoC uses Dependency Injection to pass dependencies into a class rather than creating them inside the class.

## Rubric

This assessment has a total of 20 points.  A score of 15 or higher is a pass.

As a reminder, this assessment is for students and instructors to determine if there are any areas that need additional reinforcement!
