# understandJava
My question and understanding on the path of studying Java

1. Implements

- The **implements** relation may hold between a class and an interface.
- If C **implements** I then class C contains code for the behavior specified in interface I, C has method bodies for **instance (only)
** methods whose contracts are specified in I.
- Code for C:
```
class C implements I {
    //bodies 
    //Java compiler only checks that C contains bodies for the methods in I, but does not check that those bodies are correstly implement the method contracts!
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
