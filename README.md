# reimagined-design-patterns

Give a summary description of Four design patterns that you choose from the following design patterns: **Adapter,  Builder, Composite, Decorator, Observer, Interpreter, State, Mediator, Memento, Prototype, Proxy**. In your summaries say:

- what kind of problem(s) you can solve with that pattern and when you use it, maybe with a short example
- how the pattern works, what the basic idea of the pattern is
- what the main advantage and what the the main disadvantage is of using this pattern
- Write a short summary for each of the four patterns, about half a page for each pattern (rather less than more). 

> Do not add diagrams, and do not try to give a complete description of the patterns as found in the books. Rather think of how you would explain the essential ideas of these patterns in a few sentences to a colleague while drinking coffee.

## Adapter Pattern

### Summary
The adapter pattern is a structural software design pattern (also known as wrapper) that allows the interface of an existing class to be used as another interface. It is often used to make existing classes work with others without modifying their source code.

### Example
An example is an adapter that converts the interface of a Document Object Model of an XML document into a tree structure that can be displayed. 

### Kind of Problem it solves
The adapter design pattern solves problems like:
  - How can a class be reused that does not have an interface that a client requires?
  - How can classes that have incompatible interfaces work together?
  - How can an alternative interface be provided for a class?
    
### Advantages & Disadvantages
Pros:
  - Helps achieve reusability and flexibility.
  - Client class is not complicated by having to use a different interface and can use polymorphism to swap between different implementations of adapters.

Cons: 
  - Harder to override Adaptee behavior. 
  - Customer object behavior can’t be changed without subclassing it. 

## Mediator Pattern

### Summary
The mediator pattern defines an object that encapsulates how a set of objects interact. This pattern is considered to be a behavioral pattern due to the way it can alter the program's running behavior. In object-oriented programming, programs often consist of many classes. Business logic and computation are distributed among these classes. However, as more classes are added to a program, especially during maintenance and/or refactoring, the problem of communication between these classes may become more complex. This makes the program harder to read and maintain. Furthermore, it can become difficult to change the program, since any change may affect code in several other classes. With the mediator pattern, communication between objects is encapsulated within a mediator object. Objects no longer communicate directly with each other, but instead communicate through the mediator. This reduces the dependencies between communicating objects, thereby reducing coupling. 

### Example

Air traffic controller is a great example of mediator pattern where the airport control room works as a mediator for communication between different flights.. 

### Kind of Problem it solves
The mediator design pattern solves problems such as:
    - Tight coupling between a set of interacting objects should be avoided.
    - It should be possible to change the interaction between a set of objects independently.

### Advantages & Disadvantages
Pros:
 -  It limits subclassing. A mediator localizes behavior that otherwise would be distributed among several objects. Changing this behaviour requires subclassing Mediator only, colleague classes can be reused as is.

Cons:
 - It centralizes control. The mediator pattern trades complexity of interaction for complexity in the mediator. Because a mediator encapsulates protocols, it can become more complex than any individual colleague. This can make the mediator itself a monolith that’s hard to maintain
   
## Decorator Pattern

### Summary
The decorator pattern is a design pattern that allows behavior to be added to an individual object, dynamically, without affecting the behavior of other objects from the same class. The decorator pattern is often useful for adhering to the Single Responsibility Principle, as it allows functionality to be divided between classes with unique areas of concern. Decorator use can be more efficient than subclassing, because an object's behavior can be augmented without defining an entirely new object. 

### Example
Real World Scenario: 
Lets take an example of pizza, where the base topping remains the same and based on the customer requests, additional toppings can be added which alters the pricing.

Similarly, if we have some rest api web service reponse in xml, but the customer demand to get the response in different formats such as JSON, PJSON, HTML, we could use the decorator patterns

### Kind of Problem it solves
The decorator design pattern solves problems such as:
  - Responsibilities should be added to (and removed from) an object dynamically at run-time.
  - A flexible alternative to subclassing for extending functionality should be provided.

### Advantages & Disadvantages
Pros:
 - Can be used to make it possible to extend (decorate) the functionality of a certain object at runtime.
 - It is an alternative to subclassing. Subclassing adds behavior at compile time, and the change affects all instances of the original class; decorating can provide new behavior at runtime for individual objects.
 - it offers a pay-as-you-go approach to adding responsibilities. Instead of trying to support all foreseeable features in a complex, customizable class, you can define a simple class and add functionality incrementally with Decorator objects.

Cons:
 - It can complicate the process of instantiating the component because you not only have to instantiate the component, but wrap it in a number of decorators.
 - It can be complicated to have decorators keep track of other decorators, because to look back into multiple layers of the decorator chain starts to push the decorator pattern beyond its true intent.

## Proxy Pattern

### Summary
Proxy is a structural pattern which is used as replica/substitute of the original component. It has reference to the original component

### Example
A real world example can be a cheque or credit card is a proxy for what is in our bank account. It can be used in place of cash, and provides a means of accessing that cash when required

### Kind of Problem it solves
The Proxy design pattern solves problems such as:
  - The access to an object should be controlled.
  - Additional functionality should be provided when accessing an object.

### Advantages & Disadvantages
Pros:
  - One of the advantages of Proxy pattern is security.
  - This pattern avoids duplication of objects which might be huge size and memory intensive. This in turn increases the performance of the application.
  - The remote proxy also ensures about security by installing the local code proxy (stub) in the client machine and then accessing the server with help of the remote code

Cons:
  - This pattern introduces another layer of abstraction which sometimes may be an issue if the RealSubject code is accessed by some of the clients directly and some of them might access the Proxy classes. This might cause disparate behaviour.
