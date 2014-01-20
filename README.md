# Exercises for Spring 4.0 framework 


A set of exercises created by myself (or found in the internet) to help me learn the spring framework

## IoC - Basic


### Exercise 1

Using Spring Dependecy Injection to print to console "Hello World" using the class MyMessagePrinter

```java
class MyMessagePrinter {
  private final PrintStream printer;
  public MyMessagePrinter(PrintStream printer) {
    this.printer = printer;

  }

  void printMessage(String hello) {
    printer.println(hello);
  }
  
}
```
traditionally this can be achieved like this:
```java
public static void main( String[] args )
{
  MyMessagePrinter p = new MyMessagePrinter(System.out);
  p.printMessage("Hello, World!");
}
```

### Exercise 2
Modify Exercise 1 to print to a file
