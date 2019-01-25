# JAVA 8 OCA STUDY TIPS

Tips for OCA exam

## Java Basics

".java" files are code files to be compiled.

".class" files are bytecodes generated from compiling a java code.

java command can use "." to separate packages.

javac receives a ".java" file to generate a ".class".

classes variable are static variable attached to the class and shared between every instance.

instance variables are a state variable attached to an instance. They has a default value from the start.

local variables are method variables within a method, they must be initialized, since they don't have a implicit starting value.

local variables can be final.

main structure: public static (final) void main([any String array declaration, like String[] args or String args[] or String... args])

package "java.lang" is imported implicity in every java class.

java identifiers are used in classes, methods and variables and its rule is ([A-Za-z]|_|$)+(([A-Za-z]|[0-9]|_|$)*. Identifier cannot take keywords.

The main methods will be only identified in public classes.

methods must have its data type before the name, the other modifiers has no order.

Java is pass-by-value, which means methods cannot change value from passed arguments, only the Object state.

A byte/short/int/long instance variable is always initialized with 0 value.

A float/double instance variable is always initialized with 0.0 value.

A char instance variable is always initialized with '' value.

A boolean instance variable is always initialized with false value.

Any object instance variable is always initialized with null.

a package import with "*" is not recursive, it means the import with * will import all classes from the specified package and not the subsequent package folders.

Inheritance is important due developers can minimize code duplicity.

All methods in java are pass-by-value which means that the value passed as argument on a method won't change its value. But an object atributes can be changed like arrays and Collections.

static member are related directly to the class and not to the instance, but it can be accessed from instance.

A static method cannot access instance variables, but instance methods can access static variables.

Garbage Collection cannot be forced to run, althought it has the method "System.gc()", it cannot force JVM to do the Garbage Collection.

Objects are elegible for Garbage Collection when they have no reference to an object from heap.

The finalize method is called when an object is about to get garbage collected. That can be at any time after it has become eligible for garbage collection.

finalize can be called zero or one time.

Java is multi-platform, a binarycode compiled on Linux will run on Windows

packages can or cannot be declared initially

imports are not mandatory

two imported classes with the same name, but from different packages, when simply referenced will cause compile error. Ex:
```
import java.util.*;
import java.sql.*;
public class DataManager {
	private Date data1 = new Date(); // compile error
	private java.util.Date data2 = new java.util.Date(); // right!
}
```

## Working With Java Data Types 

Primitives cannot be null.

Primitives will always start with lower case.

Possible numeric types declaration:

* double v = 1234567;
* double v = 1_234_567;
* double v = 1234567.00;
* double v = 1_234_567.00;
* double v = 1234567d;
* double v = 1_234_567d;
* double v = 1234567.00d;
* double v = 1_234_567.00d;
* double v = 1234567D;
* double v = 1_234_567D;
* double v = 1234567.00D;
* double v = 1_234_567.00D;
* float v = 1_234.00f;
* float v = 1_234.00F;
* long v = 1234567l;
* long v = 1234567L;

implicit cast list:

Reference  |  Value
-------------  |  -------------
char  |  byte
char  |  short
char  |  int
byte  |  char
short  |  char
short  |  byte
int  |  char
int  |  byte
int  |  short
long  |  char
long  |  byte
long  |  short
long  |  int
float  |  char
float  |  byte
float  |  short
float  |  int
float  |  long
double  |  char
double  |  byte
double  |  short
double  |  int
double  |  long
double  |  float
Object  |  any class
Created Object  |  covariants

Wrapper table:

Primitive  |  Wrapper
-------------  |  -------------
byte  |  Byte
short  |  Short
char  |  Character
int  |  Integer
long  |  Long
float  |  Float
double  |  Double
boolean  |  Boolean

bytes/bits: 

Primitive  |  bytes  |  bits
-------------  |  -------------  |  -------------
byte  |  1  |  8
short  |  2  |  16
char  |  2  |  16
int  |  3  |  32
long  |  4  |  64
float  |  3  |  32
double  |  4  |  64
boolean  |  -  |  1

Multiple declarations are possible separating variables with ",". Ex:
```
String a = "variavel",  b = "variavel";
String a = "variavel",  b;
String a,  b = "variavel";
String a,  b;
```

Wrappers have a "parse" method and "valueOf" method, each one will return a primitive or the wrapper. Example is that "Integer.parseInt()" will return int type and "Integer.valueOf()" will return Integer.

static variables can be used on instance and static methods.

instance variables can be used on instance methods.

## Using Operators and Decision Constructs 

Switch statement can only use:

* byte(and wrapper)
* short(and wrapper)
* char(and wrapper)
* int(and wrapper)
* String
* enum

++i/--i and i++/i-- diff:

* ++i/--i: increments or decrements and return new value
* i++/i--: increments or decrements and return original value

Precedence table:

Precedence  |  Operator |  Associativity
-------------  |  -------------  |  -------------
15  |  (), [], .  |  Left to Right
14  |  i++, i--  |  Right to Left
13  |  ++i, --i, +(unary), -(unary), !(unary), ~(unary), (cast)(unary)  |  Right to Left
12  |  *, /, %  |  Left to Right
11  |  +, -  |  Left to Right
10  |  <<, >>, >>>  |  Left to Right
9  |  <, <=, >, >=, instanceof  |  Left to Right
8  |  ==, !=  |  Left to Right
7  |  &  |  Left to Right
6  |  ^  |  Left to Right
5  |  &#124;  |  Left to Right
4  |  &&  |  Left to Right
3  |  &#124;&#124;  |  Left to Right
2  |  ? :(ternary)  |  Right to Left
1  |  =, +=, -=, +=, /=, %=  |  Right to Left

Larger number means higher precedence.

The equation of two bytes or short, must return int. Ex:
```
byte x = 10, y = 2;
int a = x + y; // sum of byte or short return int
```

The difference between & and &&/&#124; and &#124;&#124; are that &&/&#124;&#124; will validate only the left part of operation if the condition is already satisfied, and &/&#124; will mandatory validate both sides.

Ternary statement structure starts with a conditional expression and has the return from "true" case and return from "false" case. Ex:
```
(a > 5) ? "" : new Long(3)
```

If a variable is to receive a ternary statement, the cases must be covariant to be able to implicit cast to the reference. Ex:
Possible:
```
double w = (true) ? 1 : 'a';
```

Impossible:
```
byte w = (true) ? 1 : 1.3;
```

The "^" operator is an exclusive or, which means that will return true only in cases of "true ^ false" or "false ^ true".

## Creating and Using Arrays 

Types of array declarations:

* int[] myIntArray = new int[3];
* int[] myIntArray = {1,2,3};
* int[] myIntArray = new int[]{1,2,3};

Ways of declare simple arrays:

* int[] myIntArray = new int[3];
* int myIntArray[] = new int[3];

Ways to declare simple matrix:

* int[][] myIntArray = new int[3][3];
* int[] myIntArray[] = new int[3][3];
* int myIntArray[][] = new int[3][3];

Arrays are objects, not primitives.

The main argument, always has an array object, even if it is empty.

For example "new int[3]" will set three ([0, 0, 0]) and "new String[3]" will set three null([null, null, null]).

array index begin in 0 and goes until its length - 1.

When trying to access an inexistence index, it will throw an "ArrayIndexOutOfBoundsException".

arrays in java are objects, never primitives.

to print array structure you need "Arrays.toString()", otherwise will print a generic object String.

Arrays important methods:

* sort: Sorts the specified range of the specified array of objects/types into ascending order, according to the natural ordering of its elements
* binarySearch: Searches a key within an array, the array must be sorted before or be already sorted to return a valid index.
* asList: transforms an array into a List. Transformed List with asList cannot add new values to the list.

varargs are types defined with "..." after it, it's only usable as the last argument from a method.

varargs can be overriden or override an array, thought it throws a warning.

attention with Arrays.sort() from String arrays with numeric values. Ex:
```
String[] n = new String[] { "1", "9", "10" };
Arrays.sort(n); // order is "1", "10", "9"
```

The Arrays.binarySearch method when value is not found will return the negative value of the position it should be - 1.

length in arrays are public variables, not methods

On Collections, to check it's size is used the method "size()".

## Using Loop Constructs 

while structre: while(A) B, being A a boolean return condition, B will be ran only if condition A is true.

for structure: for(A;B;C) D, being A a initialization statement, ran before every statement.B is the conditional statement that needs a boolean return, ran after A. C is the update statement, but it's not ran before the first loop, it mean D runs before C. D is ran only if condition B is true.

do-while: do A while(B), being A the loop logic execution, it will run at least one time. B is the conditional statement that needs a boolean return, ran after B and validates if the execution will run again or not.

for-each: for (A) B, being A specific "for-each" statement that sets a non Collection or non array value to be treated in B execution, from a Collection or array value.

The conditionals within the loops, cannot be set to be constant true, it must have a way to break or at least make it unclear if the loop will be infinite or not.

for structure is "for(A;B;C) D", which the order of running from each statement is A, B, D, C, B, D, C, B, D...

On for structure, the initialization statement separates its statements by "," instead of ";"

On for structure, the update statement separates its statements by "," instead of ";"

## Working with Methods and Encapsulation 

modifiers(from most acess to least):

* public: any class has access to it.
* protected: any class within the same package and child class from the protected member class can access it.
* default or package-private: any class within the same package can access it.
* private: only the member owner can access it.

constructors does not have any return type.

finals variables can only be set one time

instance final variables cannot be set in methods.

super() is the method to call parent class constructor.

super() is mandatory within any constructor, in case of the parent constructor is a no argument constructor, it can be hidden in child constructor.

super() is mandatory to be the first declaration within a constructor.

super keyword can call parent accessible attributes and methods.

static blocks and methods can only use external static variables.

instance blocks and method can use external instance and static variable.

static final variables must declare within a static context and final can be declared on an instance context.

import static will only import static methods, not instance.

A setter on JavaBeans pattern must have a void return type, a prefix name as "set" and the first letter uppercase name of variable, with the argument of that variable and the assignment within the execution block.
Ex:
```
public void setItem(Item item) {
	this.item = item;
}
```

A getter on JavaBeans pattern must have the return type from variable modifier, a prefix name as "get" and the first letter uppercase name of variable, no arguments and the return from the instance variable within the execution block.
Ex:
```
public Item getItem() {
	return this.item;
}
```

Overloaded methods rules:

* methods must have the same name.
* methods must have different argument list.
* method can or cannot have different return types.
* method can or cannot have a different access modifier.
* method can or cannot have a different checked or unchecked exception.

## Working with Inheritance 

Java does not support multiple inheritance for classes, only for interfaces.

Methods from interface are implicit "public".

"final", "static" and any other access modifier besides "public" cannot be declared on an abstract method.

if two different interfaces has the same static or default method(dispite de implementation), the class implementing both, must implement a new method default or static.

Concrete classes must implement all abstract classes from its parent.

When calling instance methods, it uses polymorphism to execute the implementation, which mean that the implementation used will be from the instance.

When calling static methods, it uses the class implementation, which mean that the implementation used will be from the reference.

Attributes are always from reference.

Overriden method rules:

* methods must have the same name.
* methods must have the same arguments.
* methods must have the same return type or its covariants. 
* methods must not resctrict more the access, but can change to a broader access modifier(if parent --> protected then child --> private is not allowed)(if parent --> protected then child --> public is allowed).
* methods must not throw new or broader exception but can remove(if parent --> throws RuntimeException --> child throws Exception is not allowed)(if parent --> throws RuntimeException --> child does not throw nothing is allowed).
* only inherited methods can be overriden.
* Constructors and private methods are not inherited, so they cannot be overridden.
* Abstract methods must be overridden by the first concrete (non-abstract) subclass.
* final methods cannot be overridden.
* A subclass can use super.overridden_method() to call the superclass version of an overridden method.

A class that defines an instance variable with the same name as an instance variable from its parent class is referenced as "hidden".

A class that defines a static method with the same signature as a static method from its parent is referenced as "hidden".

Interface variables are constant, it means they are implicitly public static and final.

abstract methods can be overriden.

## Handling Exceptions 

![Throwable structure](http://journals.ecs.soton.ac.uk/java/tutorial/java/exceptions/images/throwableHierarchy_trans.gif)

Error's should not be declared or catch.

Exception and its covariants(except for RuntimeException and its covariants) are checked exceptions, and must be declared to method and/or catch within a try-catch statement.

RuntimeException and its covariants are unchecked exception, and can or cannot be declared to method and/or catch within a try-catch statement.

Important checked exceptions: IOException, FileNotFoundException, SQLException, DataAccessException

Important unchecked exceptions: NullPointerException, ArrayIndexOutOfBound, IllegalArgumentException, IllegalStateException, ClassCastException, ArithmeticException, NumberFormatException

Important Error's: StackOverflowError, OutOfMemoryError

Erros should never be used to catch.

The "catch" statements must always be orderer from least wide to most broader. 
Ex:
```
try {
} catch (Runtime re) {
} catch (Exception e) {
}
```

The order of statements:

* 1 - try: must have one.
* 2 - catch: zero or n, not necessary if a finally is present.
* 3 - finally: zero or one, not necessary if a catch is present.

The try statement must have try keyword, but it's not mandatory a catch or a finally, but it's necessary one of them at least.

The finally block will always run, except if the program forcebly exits on try or catch.

Thought the finally is the last block to run, on the following method, the finally exception is the one to be catch on method call:
```
public void fix() throws Exception {
	try {
		throw new RuntimeException("Found error");
	} catch (RuntimeException e) {
		throw new ArrayIndexOutOfBoundsException("Found catch error");
	} finally {
		throw new IllegalArgumentException("Found another error");
	}
}
```

Variables over consecutive catchs can have the same identifier.

Variables from an inner catch cannot have the same identifier from the outer.

The catch and finally must have "{}"

## Working with Selected classes from the Java API 

String is imutable and StringBuilder is mutable

String a = "somehting"; firstly search on the String pool for an existing String, if found it returns the older instance, otherwise it will create a new one.

String b = new String("something"); will always create a new instance.

String important methods: 

* charAt: char
* concat: String
* contains: boolean
* endsWith: boolean
* format: static String
* indexOf: int
* lastIndexOf: int
* length: int
* matches: boolean
* replace: String
* replaceAll: String
* replaceFirst: String
* startsWith: boolean
* substring: String
* valueOf: String

StringBuilder important methods:

* append: StringBuilder
* charAt: char
* delete: StringBuilder
* deleteCharAt: StringBuilder
* indexOf: int
* insert: StringBuilder
* lastIndexOf: int
* replace: StringBuilder
* reverse: StringBuilder
* substring: String

package java.time: LocalDate, LocalTime, LocalDateTime, Period

java.time package Classes are imutable

Period treats only days, weeks, months and years

LocalDate important methods:

* atTime: LocalDateTime
* format: String
* getDayOfMonth: int
* getDayOfWeek: DayOfWeek
* getDayOfYear: int
* getMonth: Month
* getMonthValue: int (1-12)
* getYear: int
* minus: LocalDate
* minusDays: LocalDate
* minusMonths: LocalDate
* minusWeeks: LocalDate
* minusYears: LocalDate
* now: static LocalDate
* of: static LocalDate
* plus: LocalDate
* plusDays: LocalDate
* plusMonths: LocalDate
* plusWeeks: LocalDate
* plusYears: LocalDate

LocalTime important methods:

* atDate: LocalDateTime
* format: String
* getHour: int
* getMinute: int
* getNano: int
* getSecond: int
* minus: LocalTime
* minusHours: LocalTime
* minusMinutes: LocalTime
* minusNanos: LocalTime
* minusSeconds: LocalTime
* now: static LocalTime
* of: static LocalTime
* ofNanoOfDay: static LocalTime
* ofSecondOfDay: static LocalTime
* parse: static LocalTime
* plus: LocalTime
* plusHours: LocalTime
* plusMinutes: LocalTime
* plusNanos: LocalTime
* plusSeconds: LocalTime

LocalDateTime important methods:

* format: String
* getDayOfMonth: int
* getDayOfWeek: DayOfWeek
* getDayOfYear: int
* getMonth: Month
* getMonthValue: int (1-12)
* getHour: int
* getMinute: int
* getNano: int
* getSecond: int
* minus: LocalDateTime
* minusDays: LocalDateTime
* minusMonths: LocalDateTime
* minusWeeks: LocalDateTime
* minusYears: LocalDateTime
* minusHours: LocalDateTime
* minusMinutes: LocalDateTime
* minusNanos: LocalDateTime
* minusSeconds: LocalDateTime
* now: static LocalDateTime
* of: LocalDateTime
* parse: LocalDateTime
* plus: LocalDateTime
* plusDays: LocalDateTime
* plusMonths: LocalDateTime
* plusWeeks: LocalDateTime
* plusYears: LocalDateTime
* plusHours: LocalDateTime
* plusMinutes: LocalDateTime
* plusNanos: LocalDateTime
* plusSeconds: LocalDateTime
* toLocalDate: LocalDate
* toLocalTime: LocalTime

Period important methods:

* between: static Period
* from: static Period
* getDays: int
* getMonths: int
* getYears: int
* isNegative: boolean
* isZero: boolean
* minus: LocalDateTime
* minusDays: LocalDateTime
* minusMonths: LocalDateTime
* minusYears: LocalDateTime
* negated: Period
* normalized: Period
* of: static Period
* ofDays: static Period	
* ofMonths: static Period	
* ofWeeks: static Period	
* ofYears: static Period	
* parse: static Period
* plus: Period
* plusDays: Period
* plusMonths: Period
* plusYears: Period	

Two different instances of ArrayList are "equal" when its contents are similar.

lambda is important to define deferred executions for functional interfaces.

List important methods:

* add: boolean
* addAll: boolean
* clear: void
* contains: boolean
* containsAll: boolean
* get: E
* indexOf: int
* isEmpty: boolean
* iterator: Iterator<E>
* remove: E
* removeAll: boolean
* replaceAll: default void
* set: E
* size: int
* sort: default void
* toArray: T[]

Set important methods:

* add: boolean
* addAll: boolean
* clear: void
* contains: boolean
* containsAll: boolean
* get: E
* isEmpty: boolean
* iterator: Iterator<E>
* remove: E
* removeAll: boolean
* size: int
* toArray: T[]

Map important methods:

* clear: void
* containsKey: boolean
* containsValue: boolean
* entrySet: Set<Map.Entry<K,V>
* forEach: void
* get: V
* getOrDefault: default V
* isEmpty: boolean
* keySet: Set<K>
* put: V
* putAll: void
* remove: V
* replace: default boolean
* replaceAll: default void
* size: int
* values: Collection<V>

Source  | Data
------------- | -------------
Take Exam  | <https://education.oracle.com/java-se-8-programmer-i/pexam_1Z0-808>
Java Exam Classes(en)  |  <not yet>
Java Exam Classes(pt-br)  |  <not yet>
Exam Simulation(en)  | <not yet>
Exam Simulation(pt-br)  | <https://www.udemy.com/metodologia-de-certificacao-java-8-oca-simulados/learn/v4/overview>