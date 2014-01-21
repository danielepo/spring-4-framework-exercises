# Exercises for Spring 4.0 framework 


A set of exercises created by myself (or found in the internet) to help me learn the spring framework

## IoC - Basic

### Exercise 1

Using Spring Dependecy Injection to print to console "Hello World" using the class MyMessagePrinter

```java
class LinePrinter {
  private final PrintStream printer;
  public LinePrinter() {
    this.printer = System.out;

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
  LinePrinter p = new LinePrinter();
  p.printMessage("Hello, World!");
}
```

### Exercise 2

Print to console the "Hello World" using the class LinePrinter and passing to the constructor the dependency to System.out

**suggestion:** check-out `<util:constant/>`

```java
class LinePrinter {
  private final PrintStream printer;
  
  public LinePrinter() {
    this.printer = System.out;

  }
  public LinePrinter(PrintStream printer) {
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
  LinePrinter p = new LinePrinter(System.out);
  p.printMessage("Hello, World!");
}
```

### Exercise 3
Modify Exercise 2 to print to a file

### Exercise 4

Now the class LinePrinter changes to expose only 2 factory methods that precofigure the PrintStream.


```java
class LinePrinter {

  private final PrintStream printer;

  public LinePrinter() {
    printer = null;
  }
  private LinePrinter(PrintStream printer) {
    this.printer = printer;
  }
  public LinePrinter createConsolePrinter(){
    return new LinePrinter(System.out);
  }
  public LinePrinter createFilePrinter() throws FileNotFoundException{
    return new LinePrinter(new PrintStream(new File("test.txt")));
  }
  void printMessage(String hello) {
    printer.println(hello);
  }

}
```
