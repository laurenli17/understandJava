# understandJava
My questions and understanding on the path of studying Java

1. Implements

- The **implements** relation may hold between a class and an interface.
- If C **implements** I then class C contains code for the behavior specified in interface I, C has method bodies for **instance (only)
** methods whose contracts are specified in I.
- Code for C:
```
class C implements I {
    //bodies 
    //Java compiler only checks that C contains bodies for the methods in I, 
    //but does not check that those bodies are correstly implement the method contracts!
}
```

2. Extends

- The **entends** relation may hold between:
  - 2 interfaces
  - 2 classes
- If B **extends** A, then B **inherits** all the methods of A. 
  - B implicitly starts out with all the method contracts (for interfaces)/method bodies (for classes) that A has.
  - B can then add more method contracts/bodies.
- Caveats about Java interfaces
  - Interfaces cannot have constructors
    - No good place to write separate contracts for the **constructors** of classes that implement an interface
  - Interfaces **cannot** have **static method** contracts without also providing corresponding method bodies
    - No good place to write separate contracts for **public static methods** of classes that implement an interface

- Caveats about Java classes
  - Constructors are **not** inherited
    - B must include bodies for any constructors that are expected, even if there are same bodies in A, B cannot inherited them without constructor bodies
    - The bodies of constructors in B generally would simply invoke (调用) the constructors of A, which is done using the special notation super(...)
  - Static methods are inherited
 
2. Java division: truncating zero (趋近零), not exactly rounding.

3. Javadoc的符号是/** ... */ (The notation for Javadoc is /** ... */)

4. [List](https://docs.oracle.com/javase/7/docs/api/index.html?java/util/List.html)
  - Allow duplicates;
  - If they allow null elements at all, they typically allow multiple null elements;
  - Lists are zero based;
  - Methods Summary:
    - List interface provides 4 methods for positional access to list elements  
    - 1 special iterator: ListIterator
    - 2 methods to search for a specified object:
    - 2 methods to efficiently insert and remove multiple elements at an arbitrary point in the list:    
  - > Note: While it is permissible for lists to contain themselves as elements, extreme caution is advised: the equals and hashCode methods are no longer well defined on such a list.
  - Specific methods:
    - E get(int index)
    - boolean add(E e)
    - void add(int index, E element)
    - E remove (int index)
    - boolean remove(Object o)
    - void clear()
    - boolean equals(Object o)
    - boolean contains(Object o)
    - int size()
    - E set(int index, E element)
    - int indexOf(Object o)
    - int lastIndexOf(Object o)
    - int hashCode()
    
  - Homework thinking:
    - You may have observed that the add(E e) and remove(int index) methods are marked as optional operations. Briefly discuss the benefits vs. pitfalls of this design decision.
    - Consider this quote from the java.util.List description:
> Some list implementations have restrictions on the elements that they may contain. For example, some implementations prohibit null elements, and some have restrictions on the types of their elements.

Briefly discuss the benefits vs. pitfalls of this design decision.

5. Integer range: [−2^31,  2^31 − 1]
6. Static/Instance method: (hwk9)

- Static: Static methods are the methods in Java that can be called without creating an object of class. They are referenced by the class name itself or reference to the Object of that class.

- Instance: Static methods are the methods in Java that can be called without creating an object of class. They are referenced by the class name itself or reference to the Object of that class.

- [Example](https://www.cnblogs.com/shenliang123/archive/2011/10/27/2226923.html)
7. Generic method: (hwk9)
- "Generic methods are methods that introduce their own type parameters. This is similar to declaring a generic type, but the type parameter's scope is limited to the method where it is declared. Static and non-static generic methods are allowed, as well as generic class constructors."
- [Oracle explaination](https://docs.oracle.com/javase/tutorial/java/generics/methods.html#:~:text=Generic%20Methods,introduce%20their%20own%20type%20parameters.&text=Static%20and%20non%2Dstatic%20generic,before%20the%20method's%20return%20type.)
8. Require**s** / Ensure**s** clauses (Both with a 's')
9. String method s.substring():
- s = "abcdefg"
- s.substring(3) = "defg" <Starting from index 3>
- s.substring(3,5) = "de" <Starting from index 3, end before 5>
10. Instance variable: 
    - declared in a class, but outside a method, constructor or any block
    - Instance variables are created when an object is created with the use of the keyword 'new' and destroyed when the object is destroyed.
    - [Example](https://www.tutorialspoint.com/Instance-variables-in-Java)
    
    Static/class variable: 
    - [Detailed comparison](https://www.geeksforgeeks.org/difference-between-static-and-non-static-variables-in-java/)
11. Syntactic sugar: make things easier to read/express.


   
  
  
