# Runtime-Polymorphism
Runtime Poly and Upcasting 


Upcasting occurs when a reference variable in the Parent class refers to an object in the Child class. In Java, we use this to resolve the overridden methods at run time.


The Example given below depicts how upcasting is done. 

class Parent {}
class child extends Parent {}

class Test {
    public static void main(String[] args) {
        Parent P = new child();                       //Here upcasting is done
    }
}
Here, upcasting happens when the superclass named parent’s reference variable refers to the object of its subclass child. This is the way we override methods from the base class to the inherited classes to achieve runtime polymorphism.

Let’s look at some examples of runtime polymorphism:

Example 1:

//Defining a parent class 
class Country{
 
    // Implementing a method
    public void method ()
    {
        System.out.println("India");
    }
}
 
// Defining a child class
class State extends Country {
 
    // Overriding the parent method
    public void method ()
    {
        System.out.println("Delhi");
    }

    
    public static void main(String[] args)
    {
         Country obj = new State();
         obj.method();
    }
}
Output:

Delhi
When an overridden method is invoked via a parent class reference, the object type decides which method is invoked. Since both the child and parent classes have the same method. JVM determines which version of the method (child class or parent class) will be invoked at runtime.

Example 2:

class Animal{
  public void eat (){
    System.out.println ("parent class");
  }
}
class Cat extends Animal{
  public void eat (){
    System.out.println ("first inherited class");
  }
}
class Dog extends Animal{
  public void eat (){
    System.out.println ("second inherited class");
  }
}
class Test{
  public static void main (String[]args){
     Animal a;
      a = new Cat ();
      a.eat ();
      a = new Dog ();
      a.eat ();
  }
}
Output:

first inherited class
second inherited class
