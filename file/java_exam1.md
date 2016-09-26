## java exam1	

1. Given:
   11. public interface Status {
   12. /* insert code here */ int MY_VALUE = 10;
   13. }
       Which three are valid on line 12? (Choose three.)
       A. final
       B. static
       C. native
       D. public
       E. private
       F. abstract
       G. protected
2.  Given:
   10. public class Bar {
      11.static void foo(int...x) {
   11. // insert code here
   12. }
   13. }
       Which two code fragments, inserted independently at line 12, will allow
       the class to compile? (Choose two.)
       A. foreach(x) System.out.println(z);
       B. for(int z : x) System.out.println(z);
       C. while( x.hasNext()) System.out.println( x.next());
       D. for( int i=0; i< x.length; i++ ) System.out.println(x[i]);
3. Given:
   11. public class Test {
   12. public static void main(String [] args) {
   13. int x =5;
   14. boolean b1 = true;
   15. boolean b2 = false;
      16.
      17.if((x==4) && !b2)
   16. System.out.print(”l “);
   17. System.out.print(”2 “);
   18. if ((b2 = true) && b1)
   19. System.out.print(”3 “);
   20. }
   21. }
       What is the result?
       A. 2
       B. 3
       C. 1 2
       D. 2 3
       E. 1 2 3
       F. Compilation fails.
       G. Au exceptional is thrown at runtime.
4. Given:
   31. // some code here
   32. try {
   33. // some code here
   34. } catch (SomeException se) {
   35. // some code here
   36. } finally {
   37. // some code here
   38. }
       Under which three circumstances will the code on line 37 be executed?
       (Choose three.)
       A. The instance gets garbage collected.
       B. The code on line 33 throws an exception.
       C. The code on line 35 throws an exception.
       D. The code on line 31 throws an exception.
       E. The code on line 33 executes successfully.
5.  Given:
   10. interface Foo {}
   11. class Alpha implements Foo { }
   12. class Beta extends Alpha {}
   13. class Delta extends Beta {
   14. public static void main( String[] args) {
   15. Beta x = new Beta();
   16. // insert code here
   17. }
   18. }
       Which code, inserted at line 16, will cause a
       java.lang.ClassCastException?
       A. Alpha a = x;
       B. Foo f= (Delta)x;
       C. Foo f= (Alpha)x;
       D. Beta b = (Beta)(Alpha)x;
6.  Assume that country is set for each class.
   Given:
   10. public class Money {
   11. private String country, name;
   12. public getCountry() { return country; }
      13.}
      and:
   13. class Yen extends Money {
   14. public String getCountry() { return super.country; }
   15. }
      27.
   16. class Euro extends Money {
   17. public String getCountry(String timeZone) {
   18. return super.getCountry();
   19. }
   20. }
       Which two are correct? (Choose two.)
       A. Yen returns correct values.
       B. Euro returns correct values.
       C. An exception is thrown at runtime.
       D. Yen and Euro both return correct values.
       E. Compilation fails because of an error at line 25.
       F. Compilation fails because of an error at line 30.
7.  Which Man class properly represents the relationship “Man has a best
   friend who is a Dog”?
   A. class Man extends Dog { }
   B. class Man implements Dog { }
   C. class Man { private BestFriend dog; }
   D. class Man { private Dog bestFriend; }
   E. class Man { private Dog<bestFriend> }
   F. class Man { private BestFriend<dog> }
8.  Given:
   13. public class Pass {
   14. public static void main(String [1 args) {
   15. int x 5;
   16. Pass p = new Pass();
   17. p.doStuff(x);
   18. System.out.print(” main x = “+ x);
   19. }
      20.
   20. void doStuff(int x) {
   21. System.out.print(” doStuff x = “+ x++);
   22. }
   23. }
       What is the result?
       A. Compilation fails.
       B. An exception is thrown at runtime.
       C. doStuffx = 6 main x = 6
       D. doStuffx = 5 main x = 5
       E. doStuffx = 5 main x = 6
       F. doStuffx = 6 main x = 5
9.  Given:
   10. package com.sun.scjp;
   11. public class Geodetics {
   12. public static final double DIAMETER = 12756.32; // kilometers
   13. }
       Which two correctly access the DIAMETER member of the Geodetics
       class? (Choose two.)
       A. import com.sun.scjp.Geodetics;
       public class TerraCarta {
       public double halfway()
       { return Geodetics.DIAMETER/2.0; } }
       B. import static com.sun.scjp.Geodetics;
       public class TerraCarta {
       public double halfway() { return DIAMETER/2.0; } }
       C. import static com.sun.scjp.Geodetics. *;
       public class TerraCarta {
       public double halfway() { return DIAMETER/2.0; } }
       D. package com.sun.scjp;
       public class TerraCarta {
       public double halfway() { return DIAMETER/2.0; } }
10.  Given:
    10. class Nav{
    11. public enum Direction { NORTH, SOUTH, EAST, WEST }
    12. }
    13. public class Sprite{
    14. // insert code here
    15. }
        Which code, inserted at line 14, allows the Sprite class to compile?
        A. Direction d = NORTH;
        B. Nav.Direction d = NORTH;
        C. Direction d = Direction.NORTH;
        D. Nav.Direction d = Nav.Direction.NORTH;
11.  Given:
    10. interface Foo { int bar(); }
    11. public class Sprite {
    12. public int fubar( Foo foo) { return foo.bar(); }
    13. public void testFoo() {
    14. fubar(
    15. // insert code here
       16.);
    16. }
    17. }
        Which code, inserted at line 15, allows the class Sprite to compile?
        A. Foo { public int bar() { return 1; } }
        B. new Foo { public int bar() { return 1; } }
        C. newFoo() { public int bar(){return 1; } }
        D. new class Foo { public int bar() { return 1; } }
12.  Click the Exhibit button.
    10. interface Foo {
    11. int bar();
    12. }
       13.
    13. public class Beta {
       15.
    14. class A implements Foo {
    15. public int bar() { return 1; }
    16. }
       19.
    17. public int fubar( Foo foo) { return foo.bar(); }
       21.
    18. public void testFoo() {
       23.
    19. class A implements Foo {
    20. public int bar() { return 2; }
    21. }
       27.
    22. System.out.println( fubar( new A()));
    23. }
       30.
    24. public static void main( String[] argv) {
    25. new Beta().testFoo();
    26. }
    27. }
        Which three statements are true? (Choose three.)
        A. Compilation fails.
        B. The code compiles and the output is 2.
        C. If lines 16, 17 and 18 were removed, compilation would fail.
        D. If lines 24, 25 and 26 were removed, compilation would fail.
        E. If lines 16, 17 and 18 were removed, the code would compile and
        the output would be 2.
        F. If lines 24, 25 and 26 were removed, the code would compile and
        the output would be 1.
13.  Given:
    1. public interface A {
    2. String DEFAULT_GREETING = “Hello World”;
    3. public void method1();
    4. }
       A programmer wants to create an interface called B that has A as its
       parent. Which interface declaration is correct?
       A. public interface B extends A { }
       B. public interface B implements A {}
       C. public interface B instanceOf A {}
       D. public interface B inheritsFrom A { }
14.  Given:
    1. class TestA {
    2. public void start() { System.out.println(”TestA”); }
    3. }
    4. public class TestB extends TestA {
    5. public void start() { System.out.println(”TestB”); }
    6. public static void main(String[] args) {
    7. ((TestA)new TestB()).start();
    8. }
    9. }
       What is the result?
       A. TestA
       B. TestB
       C. Compilation fails.
       D. An exception is thrown at runtime.
15.  Given:
    1. interface TestA { String toString(); }
    2. public class Test {
    3. public static void main(String[] args) {
    4. System.out.println(new TestA() {
    5. public String toString() { return “test”; }
    6. });
    7. }
    8. }
       What is the result?
       A. test
       B. null
       C. An exception is thrown at runtime.
       D. Compilation fails because of an error in line 1.
       E. Compilation fails because of an error in line 4.
       F. Compilation fails because of an error in line 5.
16.  Given:
    11. public abstract class Shape {
    12. int x;
    13. int y;
    14. public abstract void draw();
    15. public void setAnchor(int x, int y) {
    16. this.x = x;
    17. this.y = y;
    18. }
    19. }
        and a class Circle that extends and fully implements the Shape class.
        Which is correct?
        A. Shape s = new Shape();
        s.setAnchor(10,10);
        s.draw();
        B. Circle c = new Shape();
        c.setAnchor(10,10);
        c.draw();
        C. Shape s = new Circle();
        s.setAnchor(10,10);
        s.draw();
        D. Shape s = new Circle();
        s->setAnchor(10,10);
        s->draw();
        E. Circle c = new Circle();
        c.Shape.setAnchor(10,10);
        c.Shape.draw();
17.  Given:
    10. abstract public class Employee {
    11. protected abstract double getSalesAmount();
    12. public double getCommision() {
    13. return getSalesAmount() * 0.15;
    14. }
    15. }
    16. class Sales extends Employee {
    17. // insert method here
    18. }
        Which two methods, inserted independently at line 17, correctly
        complete the Sales class? (Choose two.)
        A. double getSalesAmount() { return 1230.45; }
        B. public double getSalesAmount() { return 1230.45; }
        C. private double getSalesAmount() { return 1230.45; }
        D. protected double getSalesAmount() { return 1230.45; }
18.  Given:
    10. interface Data { public void load(); }
    11. abstract class Info { public abstract void load(); }
        Which class correctly uses the Data interface and Info class?
        A. public class Employee extends Info implements Data {
        public void load() { /*do something*/ }
        }
        B. public class Employee implements Info extends Data {
        public void load() { /*do something*/ }
        }
        C. public class Employee extends Info implements Data {
        public void load() { /*do something */ }
        public void Info.load() { /*do something*/ }
        }
        D. public class Employee implements Info extends Data {
        public void Data.load() { /*d something */ }
        public void load() { /*do something */ }
        }
        E. public class Employee implements Info extends Data {
        public void load() { /*do something */ }
        public void Info.load(){ /*do something*/ }
        }
        F. public class Employee extends Info implements Data{
        public void Data.load() { /*do something*/ }
        public void Info.load() { /*do something*/ }
        }
19.  Given:
    11. public abstract class Shape {
    12. private int x;
    13. private int y;
    14. public abstract void draw();
    15. public void setAnchor(int x, int y) {
    16. this.x = x;
    17. this.y = y;
    18. }
    19. }
        Which two classes use the Shape class correctly? (Choose two.)
        A. public class Circle implements Shape {
        private int radius;
        }
        B. public abstract class Circle extends Shape {
        private int radius;
        }
        C. public class Circle extends Shape {
        private int radius;
        public void draw();
        }
        D. public abstract class Circle implements Shape {
        private int radius;
        public void draw();
        }
        E. public class Circle extends Shape {
        private int radius;
        public void draw() {/* code here */}
        }
        F. public abstract class Circle implements Shape {
        private int radius;
        public void draw() { / code here */ }
        }
20.  Which two classes correctly implement both the java.lang.Runnable
    and the java.lang.Clonable interfaces? (Choose two.)
    A. public class Session
    implements Runnable, Clonable {
    public void run();
    public Object clone();
    }
    B. public class Session
    extends Runnable, Clonable {
    public void run() { / do something */ }
    public Object clone() { / make a copy */ }
    }
    C. public class Session
    implements Runnable, Clonable {
    public void run() { / do something */ }
    public Object clone() { /* make a copy */ }
    }
    D. public abstract class Session
    implements Runnable, Clonable {
    public void run() { / do something */ }
    public Object clone() { /*make a copy */ }
    }
    E. public class Session
    implements Runnable, implements Clonable {
    public void run() { / do something */ }
    public Object clone() { / make a copy */ }
    }
21.  Click the Exhibit button.
    1. public class GoTest {
    2. public static void main(String[] args) {
    3. Sente a = new Sente(); a.go();
    4. Goban b = new Goban(); b.go();
    5. Stone c = new Stone(); c.go();
    6. }
    7. }
       8.
    8. class Sente implements Go {
    9. public void go() { System.out.println(”go in Sente.”); }
    10. }
       12.
    11. class Goban extends Sente {
    12. public void go() { System.out.println(”go in Goban”); }
    13. }
       16.
    14. class Stone extends Goban implements Go { }
       18.
    15. interface Go { public void go(); }
       What is the result?
       A. go in Goban
       go in Sente
       go in Sente
       B. go in Sente
       go in Sente
       go in Goban
       C. go in Sente
       go in Goban
       go in Goban
       D. go in Goban
       go in Goban
       go in Sente
       E. Compilation fails because of an error in line 17.
22.  Click the Exhibit button.
    1. public class Test {
    2. int x= 12;
    3. public void method(int x) {
    4. x+=x;
    5. System.out.println(x);
    6. }
    7. }
       Given:
    8. Test t = new Test();
    9. t.method(5);
       What is the output from line 5 of the Test class?
       A. 5
       B. 10
       C. 12
       D. 17
       E. 24
23.  Given:
    55. int []x= {1, 2,3,4, 5};
       56.int y[] =x;
    56. System.out.println(y[2]);
        Which is true?
        A. Line 57 will print the value 2.
        B. Line 57 will print the value 3.
        C. Compilation will fail because of an error in line 55.
        D. Compilation will fail because of an error in line 56.
24.  Given:
    35. String #name = “Jane Doe”;
       36.int$age=24;
    36. Double_height = 123.5;
    37. double~temp = 37.5;
        Which two are true? (Choose two.)
        A. Line 35 will not compile.
        B. Line 36 will not compile.
        C. Line 37 will not compile.
        D. Line 38 will not compile.
25.  Which two code fragments correctly create and initialize a static array
    of int elements? (Choose two.)
    A. static final int[] a = { 100,200 };
    B. static final int[] a;
    static { a=new int[2]; a[0]=100; a[1]=200; }
    C. static final int[] a = new int[2] { 100,200 };
    D. static final int[] a;
    static void init() { a = new int[3]; a[0]=100; a[1]=200; }
    Answer: AB
26.  Given:
    11. public static void main(String[] args) {
    12. Object obj =new int[] { 1,2,3 };
    13. int[] someArray = (int[])obj;
    14. for (int i: someArray) System.out.print(i +“ “)
    15. }
        ‘What is the result?
        A. 1 2 3
        B. Compilation fails because of an error in line 12.
        C. Compilation fails because of an error in line 13.
        D. Compilation fails because of an error in line 14.
        E. A ClassCastException is thrown at runtime.
27. Given:
    10. class Foo {
    11. static void alpha() { /* more code here */ }
    12. void beta() { /* more code here */ }
    13. }
        Which two are true? (Choose two.)
        A. Foo.beta() is a valid invocation of beta().
        B. Foo.alpha() is a valid invocation of alpha().
        C. Method beta() can directly call method alpha().
        D. Method alpha() can directly call method beta().
28. A programmer needs to create a logging method that can accept an
    arbitrary number of arguments. For example, it may be called in these
    ways:
    logIt(”log message 1 “);
    logIt(”log message2”,”log message3”);
    logIt(”log message4”, “log message5”, “log message6);
    Which declaration satisfies this requirement?
    A. public void logIt(String * msgs)
    B. public void logIt(String [] msgs)
    C. public void logIt(String... msgs)
    D. public void logIt(String msg1, String msg2, String msg3)
29.  A programmer is designing a class to encapsulate the information
    about an inventory item. A JavaBeans component is needed to
    do this. The Inventoryltem class has private instance variables to store
    the item information:
    10. private int itemId;
    11. private String name;
    12. private String description;
        Which method signature follows the JavaBeans naming standards for
        modifying the itemld instance variable?
        A. itemID(int itemId)
        B. update(int itemId)
        C. setItemId(int itemId)
        D. mutateItemId(int itemId)
        E. updateItemID(int itemId)
30. Click the Exhibit button.
    1. public class A {
       2.
    2. private int counter = 0;
       4.
    3. public static int getInstanceCount() {
    4. return counter;
    5. }
       8.
    6. public A() {
    7. counter++;
    8. }
       12.
    9. }
       Given this code from Class B:
       25.A a1 =new A();
    10. A a2 =new A();
    11. A a3 =new A();
    12. System.out.printIn(A.getInstanceCount() );
       What is the result?
       A. Compilation of class A fails.
       B. Line 28 prints the value 3 to System.out.
       C. Line 28 prints the value 1 to System.out.
       D. A runtime error occurs when line 25 executes.
       E. Compilation fails because of an error on line 28.
31. A JavaBeans component has the following field:
    111. private boolean enabled;
        Which two pairs of method declarations follow the JavaBeans standard
        for accessing this field? (Choose two.)
        A. public void setEnabled( boolean enabled)
        public boolean getEnabled()
        B. public void setEnabled( boolean enabled)
        public void isEnabled()
        C. public void setEnabled( boolean enabled)
        public boolean isEnabled()
        D. public boolean setEnabled( boolean enabled)
        public boolean getEnabled()
        Answer: AC
32.  Given:
    100. class One {
    11. public One foo() { return this; }
    12. }
    13. class Two extends One {
    14. public One foo() { return this; }
    15. }
    16. class Three extends Two {
    17. // insert method here
    18. }
        Which two methods, inserted individually, correctly complete the Three
        class? (Choose two.)
        A. public void foo() { }
        B. public int foo() { return 3; }
        C. public Two foo() { return this; }
        D. public One foo() { return this; }
        E. public Object foo() { return this; }
33. Given:
    10. class One {
    11. void foo() {}
    12. }
    13. class Two extends One {
    14. //insert method here
    15. }
        Which three methods, inserted individually at line 14, will correctly
        complete class Two? (Choose three.)
        A. int foo() { /* more code here */ }
        B. void foo() { /* more code here */ }
        C. public void foo() { /* more code here */ }
        D. private void foo() { /* more code here */ }
        E. protected void foo() { /* more code here */ }
34. Click the Exhibit button.
    1. public interface A {
    2. public void doSomething(String thing);
    3. }
    4. public class AImpl implements A {
    5. public void doSomething(String msg) { }
    6. }
    7. public class B {
    8. public A doit() {
    9. // more code here
    10. }
       5.
    11. public String execute() {
    12. // more code here
    13. }
    14. }
    15. public class C extends B {
    16. public AImpl doit() {
    17. // more code here
    18. }
       5.
    19. public Object execute() {
    20. // more code here
    21. }
    22. }
       Which statement is true about the classes and interfaces in the
       exhibit?
       A. Compilation will succeed for all classes and interfaces.
       B. Compilation of class C will fail because of an error in line 2.
       C. Compilation of class C will fail because of an error in line 6.
       D. Compilation of class AImpl will fail because of an error in line 2.
35.  Click the Exhibit button.
    1. public class A {
    2. public String doit(int x, int y) {
    3. return “a”;
    4. }
       5.
    5. public String doit(int... vals) {
    6. return “b”;
    7. }
    8. }
       Given:
    9. A a=new A();
    10. System.out.println(a.doit(4, 5));
       What is the result?
       A. Line 26 prints “a” to System.out.
       B. Line 26 prints ‘b” to System.out.
       C. An exception is thrown at line 26 at runtime.
       D. Compilation of class A will fail due to an error in line 6.
36. Given:
    1. public class A {
    2. public void doit() {
    3. }
    4. public String doit() {
    5. return “a”;
    6. }
    7. public double doit(int x) {
    8. return 1.0;
    9. }
       10.}
       What is the result?
       A. An exception is thrown at runtime.
       B. Compilation fails because of an error in line 7.
       C. Compilation fails because of an error in line 4.
       D. Compilation succeeds and no runtime errors with class A occur.
37. Given:
    10. class Line {
    11. public static class Point { }
    12. }
       13.
    13. class Triangle {
    14. // insert code here
    15. }
        Which code, inserted at line 15, creates an instance of the Point class
        defined in Line?
        A. Point p = new Point();
        B. Line.Point p = new Line.Point();
        C. The Point class cannot be instatiated at line 15.
        D. Line 1 = new Line() ; 1.Point p = new 1.Point();
38. Given:
    10. class Line {
    11. public class Point { public int x,y; }
    12. public Point getPoint() { return new Point(); }
    13. }
    14. class Triangle {
    15. public Triangle() {
    16. // insert code here
    17. }
    18. }
        Which code, inserted at line 16, correctly retrieves a local instance of a
        Point object?
        A. Point p = Line.getPoint();
        B. Line.Point p = Line.getPoint();
        C. Point p = (new Line()).getPoint();
        D. Line.Point p = (new Line()).getPoint();
39. Given:
    10. class One {
    11. public One() { System.out.print(1); }
    12. }
    13. class Two extends One {
    14. public Two() { System.out.print(2); }
    15. }
    16. class Three extends Two {
    17. public Three() { System.out.print(3); }
    18. }
    19. public class Numbers{
    20. public static void main( String[] argv) { new Three(); }
    21. }
        What is the result when this code is executed?
        A. 1
        B. 3
        C. 123
        D. 321
        E. The code rims with no output.
40. Click the Exhibit button.
    11. class Person {
    12. String name = “No name’;
    13. public Person(String nm) { name = nm; }
    14. }
       15.
    15. class Employee extends Person {
    16. String emplD = “0000”;
    17. public Employee(String id) { empID = id; }
    18. }
       20.
    19. public class EmployeeTest {
    20. public static void main(String[] args) {
    21. Employee e = new Employee(”4321”);
    22. System.out.println(e.empID);
    23. }
    24. }
        What is the result?
        A. 4321
        B. 0000
        C. An exception is thrown at runtime.
        D. Compilation fails because of an error in line 18.
41. Given:
    1. public class Plant {
    2. private String name;
    3. public Plant(String name) { this.name = name; }
    4. public String getName() { return name; }
    5. }
    6. public class Tree extends Plant {
    7. public void growFruit() { }
    8. public void dropLeaves() { }
    9. }
       Which is true?
       A. The code will compile without changes.
       B. The code will compile if public Tree() { Plant(); } is added to the
       Tree class.
       C. The code will compile if public Plant() { Tree(); } is added to the
       Plant class.
       D. The code will compile if public Plant() { this(”fern”); } is added to
       the Plant class.
       E. The code will compile if public Plant() { Plant(”fern”); } is added to
       the Plant class.
42. public class Bootchy {
    12. int bootch;
    13. String snootch;
       14.
    14. public Bootchy() {
    15. this(”snootchy”);
    16. System.out.print(”first “);
    17. }
       19.
    18. public Bootchy(String snootch) {
    19. this(420, “snootchy”);
    20. System.out.print(”second “);
    21. }
       24.
    22. public Bootchy(int bootch, String snootch) {
    23. this.bootch = bootch;
    24. this.snootch = snootch;
    25. System.out.print(”third “);
    26. }
       30.
    27. public static void main(String[] args) {
    28. Bootchy b = new Bootchy();
    29. System.out.print(b.snootch +“ “ + b.bootch);
    30. }
    31. }
        What is the result?
        A. snootchy 420 third second first
        B. snootchy 420 first second third
        C. first second third snootchy 420
        D. third second first siiootchy 420
        E. third first second snootchy 420
        F. first second first third snootchy 420
43.  Given:
    12. public class Test {
    13. public enum Dogs {collie, harrier};
    14. public static void main(String [] args) {
    15. Dogs myDog = Dogs.collie;
    16. switch (myDog) {
    17. case collie:
    18. System.out.print(”collie “);
    19. case harrier:
    20. System.out.print(”harrier “);
    21. }
    22. }
    23. }
        What is the result?
        A. collie
        B. harrier
        C. Compilation fails.
        D. collie harrier
        E. An exception is thrown at runtime.
44. Given:
    11. public void testIfA() {
    12. if(testIfB(”True”)) {
    13. System.out.println(”True”);
    14. } else {
    15. System.out.println(”Not true”);
    16. }
    17. }
    18. public Boolean testIfB(String str) {
    19. return Boolean.valueOf(str);
    20. }
        What is the result when method testIfA is invoked?
        A. True
        B. Not true
        C. An exception is thrown at runtime.
        D. Compilation fails because of an error at line 12.
        E. Compilation fails because of an error at line 19.
45. Given:
    11. public static void main(String[] args) {
    12. Integer i = uew Integer(1) + new Integer(2);
    13. switch(i) {
    14. case 3: System.out.println(”three”); break;
    15. default: System.out.println(”other”); break;
    16. }
    17. }
        ‘What is the result?
        A. three
        B. other
        C. An exception is thrown at runtime.
        D. Compilation fails because of an error on line 12.
        E. Compilation fails because of an error on line 13.
        F. Compilation fails because of an error on line 15.
46. Given:
    11. public static void main(String[] args) {
    12. String str = “null’;
    13. if (str == null) {
    14. System.out.println(”null”);
    15. } else (str.length() == 0) {
    16. System.out.println(”zero”);
    17. } else {
    18. System.out.println(”some”);
    19. }
    20. }
        ‘What is the result?
        A. null
        B. zero
        C. some
        D. Compilation fails.
        E. An exception is thrown at runtime.
47. Given:
    11. Float pi = new Float(3.14f);
       12.if(pi>3) {
    12. System.out.print(”pi is bigger than 3. “);
    13. }
    14. else {
    15. System.out.print(”pi is not bigger than 3. “);
    16. }
    17. finally {
    18. System.out.println(”Have a nice day.”);
    19. }
        ‘What is the result?
        A. Compilation fails.
        B. pi is bigger than 3.
        C. An exception occurs at runtime.
        D. pi is bigger than 3. Have a nice day.
        E. pi is not bigger than 3. Have a nice day.
48. Given:
    10.int x=0;
    11.int y 10;
    12. do {
       l3. y--;
    13. ++x;
    14. } while (x < 5);
    15. System.out.print(x + “,“ + y);
        What is the result?
        A. 5,6
        B. 5,5
        C. 6,5
        D. 6,6
49. Given:
    25.intx=12;
    26. while (x < 10) {
    27. x--;
    28. }
    29. System.out.print(x);
        What is the result?
        A. 0
        B. 10
        C. 12
        D. Line 29 will never be reached
50. Given:
    35. int x= 10;
    36. do {
    37. x--;
    38. } while(x< 10);
        How many times will line 37 be executed?
        A. ten times
        B. zero times
        C. one to me times
        D. more than ten times
51. Give:
    11. public static Iterator reverse(List list) {
    12. Collections.reverse(list);
    13. return list.iterator();
    14. }
    15. public static void main(String[] args) {
    16. List list = new ArrayList();
    17. list.add(” 1”); list.add(”2”); list.add(”3”);
    18. for (Object obj: reverse(list))
    19. System.out.print(obj + “,”);
    20. }
        ‘What is the result?
        A. 3,2, 1,
        B. 1, 2, 3,
        C. Compilation fails.
        D. The code runs with no output.
        E. An exception is thrown at runtime.
52. Given:
    11. public static Collection get() {
    12. Collection sorted = new LinkedList();
    13. sorted.add(’B”); sorted.add(”C”); sorted.add(”A”);
    14. return sorted;
    15. }
    16. public static void main(String[] args) {
    17. for (Object obj: get()) {
    18. System.out.print(obj + “, “);
    19. }
    20. }
        What is the result?
        A. A, B, C,
        B. B, C, A,
        C. Compilation fails.
        D. The code runs with no output.
        E. An exception is thrown at runtime.
53. Given:
    11. public static void main(String[] args) {
    12. for (int i=0;i<= 10;i++){
    13. if( i>6) break;
    14. }
    15. System.out.println(i);
    16. }
        What is the result?
        A. 6
        B. 7
        C. 10
        D. 11
        E. Compilation fails.
        F. An exception is thrown at runtime.
54. Given:
    8. public class test {
    9. public static void main(String [] a) {
    10. assert a.length == 1;
    11. }
    12. }
       Which two will produce an AssertionError? (Choose two.)
       A. java test
       B. java -ea test
       C. java test file1
       D. java -ea test file1
       E. java -ea test file1 file2
       F. java -ea:test test file1
55. Given:
    12. public class AssertStuff {
       13.
    13. public static void main(String [] args) {
    14. int x= 5;
    15. int y= 7;
       17.
    16. assert (x> y): “stuff”;
    17. System.out.println(”passed”);
    18. }
    19. }
        And these command line invocations:
        java AssertStuff
        java -ea AssertStuff
        What is the result?
        A. passed
        stuff
        B. stuff
        passed
        C. passed
        An AssertionError is thrown with the word “stuff” added to the stack
        trace.
        D. passed
        An AssertionError is thrown without the word “stuff” added to the
        stack trace.
        E. passed
        An AssertionException is thrown with the word “stuff” added to the
        stack trace.
        F. passed
        An AssertionException is thrown without the word “stuff” added to the
        stack trace.
56. Click the Exhibit button.
    1. public class Test {
       2.
    2. public static void main(String [] args) {
    3. boolean assert = true;
    4. if(assert) {
    5. System.out.println(”assert is true”);
    6. }
    7. }
       9.
    8. }
       Given:
       javac -source 1.3 Test.java
       What is the result?
       A. Compilation fails.
       B. Compilation succeeds with errors.
       C. Compilation succeeds with warnings.
       D. Compilation succeeds without warnings or errors.
57. Click the Exhibit button.
    SomeException:
    1. public class SomeException {
    2. }
       Class A:
    3. public class A {
    4. public void doSomething() { }
    5. }
       Class B:
    6. public class B extends A {
    7. public void doSomething() throws SomeException { }
    8. }
       Which is true about the two classes?
       A. Compilation of both classes will fail.
       B. Compilation of both classes will succeed.
       C. Compilation of class A will fail. Compilation of class B will succeed.
       D. Compilation of class B will fail. Compilation of class A will succeed.
58. Click the Exhibit button.
    Class TestException
    1. public class TestException extends Exception {
    2. }
       Class A:
    3. public class A {
       2.
    4. public String sayHello(String name) throws TestException {
       4.
    5. if(name == null) {
    6. throw new TestException();
    7. }
       8.
    8. return “Hello “+ name;
    9. }
       11.
    10. }
       A programmer wants to use this code in an application:
    11. A a=new A();
    12. System.out.println(a.sayHello(”John”));
       Which two are true? (Choose two.)
       A. Class A will not compile.
       B. Line 46 can throw the unchecked exception TestException.
       C. Line 45 can throw the unchecked exception TestException.
       D. Line 46 will compile if the enclosing method throws a TestException.
       E. Line 46 will compile if enclosed in a try block, where TestException
       is caught.
59. Click the Exhibit button.
    10. public class ClassA {
    11. public void methodA() {
    12. ClassB classB = new ClassB();
    13. classB.getValue();
    14. }
    15. }
       And:
    16. class ClassB {
    17. public ClassC classC;
       22.
    18. public String getValue() {
    19. return classC.getValue();
    20. }
    21. }
        And:
    22. class ClassC {
    23. public String value;
       32.
    24. public String getValue() {
    25. value = “ClassB”;
    26. return value;
    27. }
    28. }
        Given:
        ClassA a = new ClassA();
        a.methodA();
        What is the result?
        A. Compilation fails.
        B. ClassC is displayed.
        C. The code runs with no output.
        D. An exception is thrown at runtime.
60. Given:
    10. public class Foo {
    11. static int[] a;
    12. static { a[0]=2; }
    13. public static void main( String[] args) {}
    14. }
        Which exception or error will be thrown when a programmer attempts
        to run this code?
        A. java.lang. StackOverflowError
        B. java.lang.IllegalStateException
        C. java.lang.ExceptionlnlnitializerError
        D. java.lang.ArraylndexOutOfBoundsException
61. Given:
    10. public class ClassA {
    11. public void count(int i) {
    12. count(++i);
    13. }
    14. }
       And:
    15. ClassA a = new ClassA();
    16. a.count(3);
        Which exception or error should be thrown by the virtual machine?
        A. StackOverflowError
        B. NullPointerException
        C. NumberFormatException
        D. IllegalArgumentException
        E. ExceptionlnlnitializerError
62. Given:
    1. public class Boxer1 {
    2. Integer i;
    3. int x;
    4. public Boxer1(int y) {
    5. x=i+y;
    6. System.out.println(x);
    7. }
    8. public static void main(String[] args) {
    9. new Boxer1(new Integer(4));
    10. }
    11. }
       What is the result?
       A. The value “4” is printed at the command line.
       B. Compilation fails because of an error in line 5.
       C. Compilation fails because of an error in line 9.
       D. A NullPointerException occurs at runtime.
       E. A NumberFormatException occurs at runtime.
       F. An IllegalStateException occurs at runtime.
63. Given:
    1. public class TestString 1 {
    2. public static void main(String[] args) {
    3. String str = “420”;
    4. str += 42;
    5. System.out.print(str);
    6. }
    7. }
       What is the output?
       A. 42
       B. 420
       C. 462
       D. 42042
       E. Compilation fails.
       F. An exception is thrown at runtime.
64.  Given:
    11. class Converter {
    12. public static void main(String[] args) {
    13. Integer i = args[0];
    14. int j = 12;
    15. System.out.println(”It is “ + (j==i) + “that j==i.”);
    16. }
    17. }
        What is the result when the programmer attempts to compile the code
        and run it with the command java Converter 12?
        A. It is true that j==i.
        B. It is false that j==i.
        C. An exception is thrown at runtime.
        D. Compilation fails because of an error in line 13.
65. Given this method in a class:
    21. public String toString() {
    22. StringBuffer buffer = new StringBuffer();
    23. buffer.append(’<’);
    24. buffer.append(this.name);
    25. buffer.append(’>’);
    26. return buffer.toString();
    27. }
        Which is true?
        A. This code is NOT thread-safe.
        B. The programmer can replace StringBuffer with StringBuilder with no
        other changes.
        C. This code will perform well and converting the code to use
        StringBuilder will not enhance the performance.
        D. This code will perform poorly. For better performance, the code
        should be rewritten: return “<“+ this.name + “>”;
66. Given:
    11. public String makinStrings() {
    12. String s = “Fred”;
    13. s = s + “47”;
    14. s = s.substring(2, 5);
    15. s = s.toUpperCase();
    16. return s.toString();
    17. }
        How many String objects will be created when this method is invoked?
        A. 1
        B. 2
        C. 3
        D. 4
        E. 5
        F. 6
67. Given:
    1. public class TestString3 {
    2. public static void main(String[] args) {
    3. // insert code here
    4. System.out.println(s);
    5. }
    6. }
       Which two code fragments, inserted independently at line 3, generate
       the output 4247? (Choose two.)
       A. String s = “123456789”;
       s = (s-”123”).replace(1,3,”24”) - “89”;
       B. StringBuffer s = new StringBuffer(”123456789”);
       s.delete(0,3).replace( 1,3, “24”).delete(4,6);
       C. StringBuffer s = new StringBuffer(”123456789”);
       s.substring(3,6).delete( 1 ,3).insert( 1, “24”);
       D. StringBuilder s = new StringBuilder(”123456789”);
       s.substring(3,6).delete( 1 ,2).insert( 1, “24”);
       E. StringBuilder s = new StringBuilder(”123456789”);
       s.delete(0,3).delete( 1 ,3).delete(2,5).insert( 1, “24”);
68. Given:
    11. public class Yikes {
       12.
    12. public static void go(Long n) {System.out.println(”Long “);}
    13. public static void go(Short n) {System.out.println(”Short “);}
    14. public static void go(int n) {System.out.println(”int “);}
    15. public static void main(String [] args) {
    16. short y= 6;
    17. long z= 7;
    18. go(y);
    19. go(z);
    20. }
    21. }
        What is the result?
        A. int Long
        B. Short Long
        C. Compilation fails.
        D. An exception is thrown at runtime.
69. Given:
    12. public class Wow {
    13. public static void go(short n) {System.out.println(”short”); }
    14. public static void go(Short n) {System.out.println(”SHORT”);}
    15. public static void go(Long n) {System.out.println(” LONG”); }
    16. public static void main(String [] args) {
    17. Short y= 6;
       18.int z=7;
    18. go(y);
    19. go(z);
    20. }
    21. }
        What is the result?
        A. short LONG
        B. SHORT LONG
        C. Compilation fails.
        D. An exception is thrown at runtime.
70. Given:
    10. class MakeFile {
    11. public static void main(String[] args) {
    12. try {
    13. File directory = new File(”d”);
    14. File file = new File(directory,”f”);
    15. if(!file.exists()) {
    16. file.createNewFile();
    17. }
    18. } catch (IOException e) {
    19. e.printStackTrace
    20. }
    21. }
    22. }
        The current directory does NOT contain a directory named “d.”
        Which three are true? (Choose three.)
        A. Line 16 is never executed.
        B. An exception is thrown at runtime.
        C. Line 13 creates a File object named “d.”
        D. Line 14 creates a File object named “f.’
        E. Line 13 creates a directory named “d” in the file system.
        F. Line 16 creates a directory named “d” and a file ‘f’ within it in the
        file system.
        G. Line 14 creates a file named ‘f’ inside of the directory named “d” in
        the file system.
71. When comparing java.io.BufferedWriter to java.io.FileWriter, which
    capability exists as a method in only one of the two?
    A. closing the stream
    B. flushing the stream
    C. writing to the stream
    D. marking a location in the stream
    E. writing a line separator to the stream
72. Given:
    1. class SuperClass {
    2. public A getA() {
    3. return new A();
    4. }
    5. }
    6. class SubClass extends SuperClass {
    7. public B getA() {
    8. return new B();
    9. }
    10. }
       Which is true?
73. Given:
    1. interface A { public void aMethod(); }
    2. interface B { public void bMethod(); }
    3. interface C extends A,B { public void cMethod(); }
    4. class D implements B {
    5. public void bMethod() { }
    6. }
    7. class E extends D implements C {
    8. public void aMethod() { }
    9. public void bMethod() { }
    10. public void cMethod() { }
    11. }
       What is the result?
       A. Compilation fails because of an error in line 3.
       B. Compilation fails because of an error in line 7.
       C. Compilation fails because of an error in line 9.
       D. If you define D e = new E(), then e.bMethod() invokes the version
       of bMethod() defined in Line 5.
       E. If you define D e = (D)(new E()), then e.bMethod() invokes the
       version of bMethod() defined in Line 5.
       F. If you define D e = (D)(new E()), then e.bMethod() invokes the
       version of bMethod() defined in Line 9.
74. Given:
    10. interface A { public int getValue() }
    11. class B implements A {
    12. public int getValue() { return 1; }
    13. }
    14. class C extends B {
    15. // insert code here
    16. }
        Which three code fragments, inserted individually at line 15, make use
        of polymorphism? (Choose three.)
        A. public void add(C c) { c.getValue(); }
        B. public void add(B b) { b.getValue(); }
        C. public void add(A a) { a.getValue(); }
        D. public void add(A a, B b) { a.getValue(); }
        E. public void add(C c1, C c2) { c1.getValue(); }
75. Given:
    1. class ClassA {
    2. public int numberOfinstances;
    3. protected ClassA(int numberOfinstances) {
    4. this.numberOflnstances = numberOfinstances;
    5. }
    6. }
    7. public class ExtendedA extends ClassA {
    8. private ExtendedA(int numberOfinstances) {
    9. super(numberOflnstances);
    10. }
    11. public static void main(String[] args) {
    12. ExtendedA ext = new ExtendedA(420);
    13. System.out.print(ext.numberOflnstances);
    14. }
    15. }
       Which is true?
       A. 420 is the output.
       B. An exception is thrown at runtime.
       C. All constructors must be declared public.
       D. Constructors CANNOT use the private modifier.
       E. Constructors CANNOT use the protected modifier.
76. Given:
    1. public class Base {
    2. public static final String FOO = “foo”;
    3. public static void main(String[] args) {
    4. Base b = new Base();
    5. Sub s = new Sub();
    6. System.out.print(Base.FOO);
    7. System.out.print(Sub.FOO);
    8. System.out.print(b.FOO);
    9. System.out.print(s.FOO);
    10. System.out.print(((Base)s).FOO);
    11. } }
    12. class Sub extends Base {public static final String FOO=bar;}
       What is the result?
       A. foofoofoofoofoo
       B. foobarfoobarbar
       C. foobarfoofoofoo
       D. foobarfoobarfoo
       E. barbarbarbarbar
       F. foofoofoobarbar
       G. foofoofoobarfoo
77. Which three statements are true? (Choose three.)
    A. A final method in class X can be abstract if and only if X is abstract.
    B. A protected method in class X can be overridden by any subclass of
    X.
    C. A private static method can be called only within other static
    methods in class X.
    D. A non-static public final method in class X can be overridden in any
    subclass of X.
    E. A public static method in class X can be called by a subclass of X
    without explicitly referencing the class X.
    F. A method with the same signature as a private final method in class
    X can be implemented in a subclass of X.
    G. A protected method in class X can be overridden by a subclass of A
    only if the subclass is in the same package as X.
78. Given:
    1. class Super {
    2. private int a;
    3. protected Super(int a) { this.a = a; }
    4. }
       .....
    5. class Sub extends Super {
    6. public Sub(int a) { super(a); }
    7. public Sub() { this.a= 5; }
    8. }
       Which two, independently, will allow Sub to compile? (Choose two.)
       A. Change line 2 to:
       public int a;
       B. Change line 2 to:
       protected int a;
       C. Change line 13 to:
       public Sub() { this(5); }
       D. Change line 13 to:
       public Sub() { super(5); }
       E. Change line 13 to:
       public Sub() { super(a); }
79. Click the Exhibit button.
    1. public class SimpleCalc {
    2. public int value;
    3. public void calculate() { value += 7; }
    4. }
       And:
    5. public class MultiCalc extends SimpleCalc {
    6. public void calculate() { value -= 3; }
    7. public void calculate(int multiplier) {
    8. calculate();
    9. super.calculate();
    10. value *=multiplier;
    11. }
    12. public static void main(String[] args) {
    13. MultiCalc calculator = new MultiCalc();
    14. calculator.calculate(2);
    15. System.out.println(”Value is: “+ calculator.value);
    16. }
    17. }
       What is the result?
       A. Value is: 8
       B. Compilation fails.
       C. Value is: 12
       D. Value is: -12
       E. The code runs with no output.
       F. An exception is thrown at runtime.
80. Given:
    10. public class Hello {
    11. String title;
    12. int value;
    13. public Hello() {
    14. title += “ World”;
    15. }
    16. public Hello(int value) {
    17. this.value = value;
    18. title = “Hello”;
    19. Hello();
    20. }
    21. }
       and:
    22. Hello c = new Hello(5);
    23. System.out.println(c.title);
        What is the result?
        A. Hello
        B. Hello World
        C. Compilation fails.
        D. Hello World 5
        E. The code runs with no output.
        F. An exception is thrown at runtime.
81. Click the Exhibit button.
    1. public class Car {
    2. private int wheelCount;
    3. private String vin;
    4. public Car(String vin) {
    5. this.vin = vin;
    6. this.wheelCount = 4;
    7. }
    8. public String drive() {
    9. return “zoom-zoom”;
    10. }
    11. public String getInfo() {
    12. return “VIN: “+ vin + “wheels: “+ wheelCount;
    13. }
    14. }
       And:
    15. public class MeGo extends Car {
    16. public MeGo(String vin) {
    17. this.wheelCount = 3;
    18. }
    19. }
       What two must the programmer do to correct the compilation errors?
       (Choose two.)
       A. insert a call to this() in the Car constructor
       B. insert a call to this() in the MeGo constructor
       C. insert a call to super() in the MeGo constructor
       D. insert a call to super(vin) in the MeGo constructor
       E. change the wheelCount variable in Car to protected
       F. change line 3 in the MeGo class to super.wheelCount = 3;
82. Click the Exhibit button.
    1. public class Employee {
    2. String name;
    3. double baseSalary;
    4. Employee(String name, double baseSalary) {
    5. this.name = name;
    6. this.baseSalary = baseSalary;
    7. }
    8. }
       And:
    9. public class Salesperson extends Employee {
    10. double commission;
    11. public Salesperson(String name, double baseSalary,
    12. double commission) {
    13. // insert code here
    14. }
    15. }
       Which code, inserted at line 7, completes the Salesperson constructor?
       A. this.commission = commission;
       B. superb();
       commission = commission;
       C. this.commission = commission;
       superb();
       D. super(name, baseSalary);
       this.commission = commission;
       E. super();
       this.commission = commission;
       F. this.commission = commission;
       super(name, baseSalary);
83. Given:
    1. public class Blip {
    2. protected int blipvert(int x) { return 0; }
    3. }
    4. class Vert extends Blip {
    5. // insert code here
    6. }
       Which five methods, inserted independently at line 5, will compile?
       (Choose five.)
       A. public int blipvert(int x) { return 0; }
       B. private int blipvert(int x) { return 0; }
       C. private int blipvert(long x) { return 0; }
       D. protected long blipvert(int x) { return 0; }
       E. protected int blipvert(long x) { return 0; }
       F. protected long blipvert(long x) { return 0; }
       G. protected long blipvert(int x, int y) { return 0; }
84. Given:
    10. public class Foo {
    11. public int a;
    12. public Foo() { a = 3; }
    13. public void addFive() { a += 5; }
    14. }
       and:
    15. public class Bar extends Foo {
    16. public int a;
    17. public Bar() { a = 8; }
    18. public void addFive() { this.a +=5; }
    19. }
       invoked with:
    20. Foo foo = new Bar();
    21. foo.addFive();
    22. System.out.println(”Value: “+ foo.a);
        What is the result?
        A. Value: 3
        B. Value: 8
        C. Value: 13
        D. Compilation fails.
        E. The code runs with no output.
        F. An exception is thrown at runtime.
85. Given:
    10. public class SuperCaic {
    11. protected static int multiply(int a, int b) { return a * b; }
    12. }
       and:
    13. public class SubCalc extends SuperCalc {
    14. public static int multiply(int a, int b) {
    15. int c = super.multiply(a, b);
    16. return c;
    17. }
    18. }
       and:
    19. SubCalc sc = new SubCalc();
    20. System.out.println(sc.multiply(3,4));
    21. System.out.println(SubCalc.multiply(2,2));
        What is the result?
        A. 12
        4
        B. The code runs with no output.
        C. An exception is thrown at runtime.
        D. Compilation fails because of an error in line 21.
        E. Compilation fails because of an error in line 22.
        F. Compilation fails because of an error in line 31.
86. Which four are true? (Choose four.)
    A. Has-a relationships should never be encapsulated.
    B. Has-a relationships should be implemented using inheritance.
    C. Has-a relationships can be implemented using instance variables.
    D. Is-a relationships can be implemented using the extends keyword.
    E. Is-a relationships can be implemented using the implements
    keyword.
    F. The relationship between Movie and Actress is an example of an is-a
    relationship.
    G. An array or a collection can be used to implement a one-to-many
    has-a relationship.
87. Which two are true about has-a and is-a relationships? (Choose two.)
    A. Inheritance represents an is-a relationship.
    B. Inheritance represents a has-a relationship.
    C. Interfaces must be used when creating a has-a relationship.
    D. Instance variables can be used when creating a has-a relationship.
88. Given:
    10. interface Jumper { public void jump(); }
       ......
    11. class Animal {}
       ......
    12. class Dog extends Animal {
    13. Tail tail;
    14. }
       ......
    15. class Beagle extends Dog implements Jumper {
    16. public void jump() { }
    17. }
        .......
    18. class Cat implements Jumper {
    19. public void jump() { }
    20. }
        Which three are true? (Choose three.)
        A. Cat is-a Animal
        B. Cat is-a Jumper
        C. Dog is-a Animal
        D. Dog is-a Jumper
        E. Cat has-a Animal
        F. Beagle has-a Tail
        G. Beagle has-a Jumper
89. Given classes defined in two different files:
    1. package util;
    2. public class BitUtils {
    3. private static void process(byte[] b) { }
    4. }
    5. package app;
    6. public class SomeApp {
    7. public static void main(String[] args) {
    8. byte[] bytes = new byte[256];
    9. // insert code here
    10. }
    11. }
       What is required at line 5 in class SomeApp to use the process method
       of BitUtils?
       A. process(bytes);
       B. BitUtils.process(bytes);
       C. app.BitUtils.process(bytes);
       D. util.BitUtils.process(bytes);
       E. import util.BitUtils. *; process(bytes);
       F. SomeApp cannot use the process method in BitUtils.
90. Given classes defined in two different files:
    1. package packageA;
    2. public class Message {
    3. String getText() { return “text”; }
    4. }
       and:
    5. package packageB;
    6. public class XMLMessage extends packageA.Message {
    7. String getText() { return “<msg>text</msg>”; }
    8. public static void main(String[] args) {
    9. System.out.println(new XMLMessage().getText());
    10. }
    11. }
       What is the result of executing XMLMessage.main?
       A. text
       B. <msg>text</msg>
       C. An exception is thrown at runtime.
       D. Compilation fails because of an error in line 2 of XMLMessage.
       E. Compilation fails because of an error in line 3 of XMLMessage.
91. Given a file GrizzlyBear.java:
    1. package animals.mammals;
       2.
    2. public class GrizzlyBear extends Bear {
    3. void hunt() {
    4. Salmon s = findSalmon();
    5. s.consume();
    6. }
    7. }
       and another file, Salmon.java:
    8. package animals.fish;
       2.
    9. public class Salmon extends Fish {
    10. void consume() { /* do stuff */ }
    11. }
       Assume both classes are defined in the correct directories for theft
       packages, and that the Mammal class correctly defines the
       findSalmon() method. Which two changes allow this code to compile
       correctly? (Choose two.)
       A. add public to the start of line 4 in Salmon.java
       B. add public to the start of line 4 in GrizzlyBear.java
       C. add import animals.mammals.*; at line 2 in Salmon.java
       D. add import animals.fish.*; at line 2 in GrizzlyBear.java
       E. add import animals.fish.Salmon.*; at line 2 in GrizzlyBear.java
       F. add import animals.mammals.GrizzlyBear.*;at line 2 in Salmon.java
92. package utils;
    2.
    3. public class Repetition {
    4. public static String twice(String s) { return s + s; }
    5. }
       and given another class Demo:
    6. // insert code here
       2.
    7. public class Demo {
    8. public static void main(String[] args) {
    9. System.out.println(twice(”pizza”));
    10. }
    11. }
       Which code should be inserted at line 1 of Demo.java to compile and
       run Demo to print “pizzapizza”?
       A. import utils.*;
       B. static import utils.*;
       C. import utils.Repetition.*;
       D. static import utils.Repetition. *;
       E. import utils.Repetition.twice();
       F. import static utils.Repetition.twice;
       G. static import utils.Repetition.twice;
93. Given:
    11. interface DeclareStuff{
    12. public static final int EASY = 3;
    13. void doStuff(int t); }
    14. public class TestDeclare implements DeclareStuff {
    15. public static void main(String [] args) {
    16. int x=5;
    17. new TestDeclare().doStuff(++x);
    18. }
    19. void doStuff(int s) {
    20. s += EASY + ++s;
    21. System.out.println(”s “ + s);
    22. }
    23. }
        What is the result?
        A. s 14
        B. s 16
        C. s 10
        D. Compilation fails.
        E. An exception is thrown at runtime.
94. Given:
    1. interface DoStuff2 {
    2. float getRange(int low, int high); }
       3.
    3. interface DoMore {
    4. float getAvg(int a, int b, int c); }
       6.
    5. abstract class DoAbstract implements DoStuff2, DoMore { }
       8.
    6. class DoStuff implements DoStuff2 {
    7. public float getRange(int x, int y) { return 3.14f; } }
       11.
    8. interface DoAll extends DoMore {
    9. float getAvg(int a, int b, int c, int d); }
       What is the result?
       A. The file will compile without error.
       B. Compilation fails. Only line 7 contains an error.
       C. Compilation fails. Only line 12 contains an error.
       D. Compilation fails. Only line 13 contains an error.
       E. Compilation fails. Only lines 7 and 12 contain errors.
       F. Compilation fails. Only lines 7 and 13 contain errors.
       G. Compilation fails. Lines 7, 12, and 13 contain errors.
95. Given:
    11. public class Counter {
    12. public static void main(String[] args) {
    13. int numArgs = /* insert code here */;
    14. }
    15. }
        and the command line:
        java Counter one fred 42
        Which code, inserted at line 13, captures the number of arguments
        passed into the program?
        A. args.count
        B. args.length
        C. args.count()
        D. args.length()
        E. args.getLength()
96. Given the command line java Pass2 and:
    15. public class Pass2 {
    16. public void main(String [] args) {
       17.int x=6;
    17. Pass2 p = new Pass2();
    18. p.doStuff(x);
    19. System.out.print(” main x = “+ x);
    20. }
       22.
    21. void doStuff(int x) {
    22. System.out.print(” doStuffx = “+ x++);
    23. }
    24. }
        What is the result?
        A. Compilation fails.
        B. An exception is thrown at runtime.
        C. doStuffx = 6 main x = 6
        D. doStuffx = 6 main x = 7
        E. doStuffx = 7 main x = 6
        F. doStuffx = 7 main x = 7
97. Given:
    15. public class Yippee {
    16. public static void main(String [] args) {
    17. for(int x = 1; x < args.length; x++) {
    18. System.out.print(args[x] +“ “);
    19. }
    20. }
    21. }
        and two separate command line invocations:
        java Yippee
        java Yippee 1234
        What is the result?
        A. No output is produced.
        123
        B. No output is produced.
        234
        C. No output is produced.
        1234
        D. An exception is thrown at runtime.
        123
        E. An exception is thrown at runtime.
        234
        F. An exception is thrown at rijntime.
        1234
98. Given:
    12. public class Yippee2 {
       13.
    13. static public void main(String [] yahoo) {
    14. for(int x= 1; x<yahoo.length; x++) {
    15. System.out.print(yahoo[x] + “ “);
    16. }
    17. }
    18. }
        and the command line invocation:
        java Yippee2 a b c
        What is the result?
        A.a b
        B.b c
        C.a b c
        D. Compilation fails.
        E. An exception is thrown at runtime.
99. Click the Exhibit button.
    11. class Payload {
    12. private int weight;
    13. public Payload(int wt) { weight = wt; }
    14. public void setWeight(mt w) { weight = w; }
    15. public String toString { return Integer.toString(weight); }
    16. }
       17.
    17. public class TestPayload {
    18. static void changePayload(Payload p) {
    19. /* insert code here */
    20. }
       22.
    21. public static void main(String[] args) {
    22. Payload p = new Payload();
    23. p.setWeight(1024);
    24. changePayload(p);
    25. System.out.println(”The value of p is “+ p);
    26. }
    27. }
        Which statement, placed at line 20, causes the code to print “The
        value of p is 420.”?
        A. p.setWeight(420);
        B. p.changePayload(420);
        C. p = new Payload(420);
        D. Payload.setWeight(420);
        E. p = Payload.setWeight(420);
        F. p = new Payload();
        p.setWeight(420);
100. Click the Exhibit button.
     1. public class Item {
     2. private String desc;
     3. public String getDescription() { return desc; }
     4. public void setDescription(String d) { desc = d; }
        5.
     5. public static void modifyDesc(Item item, String desc) {
     6. item = new Item();
     7. item.setDescription(desc);
     8. }
     9. public static void main(String[] args) {
     10. Item it = new Item();
     11. it.setDescription(”Gobstopper”);
     12. Item it2 = new Item();
     13. it2.setDescription(”Fizzylifting”);
     14. modifyDesc(it, “Scrumdiddlyumptious”);
     15. System.out.println(it.getDescription());
     16. System.out.println(it2.getDescription());
     17. }
     18. }
        What is the outcome of the code?
        A. Compilation fails.
        B. Gobstopper
        Fizzylifting
        C. Gobstopper
        Scrumdiddlyumptious
        D. Scrumdiddlyumptious
        Fizzylifltng
        E. Scrumdiddlyumptious
        Scrumdiddlyumptious