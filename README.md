# JAVA 8 OCA STUDY TIPS

Tips for OCA exam

## Java Basics

main structure: public static (final) void main([any String array declaration, like String[] args or String args[] or String... args])

package "java.lang" is imported implicity in every java class.

java identifiers are used in classes, methods and variables and its rule is ([A-Za-z]|_|$)+(([A-Za-z]|[0-9]|_|$)*. Identifier cannot take keywords.

Java is pass-by-value, which means methods cannot change value from passed arguments, only the Object state.

A byte/short/int/long instance variable is always initialized with 0 value.

A float/double instance variable is always initialized with 0.0 value.

A char instance variable is always initialized with '' value.

A boolean instance variable is always initialized with false value.

a package import with "*" is not recursive, it means the import with * will import all classes from the specified package and not the subsequent package folders.

Inheritance is important due developers can minimize code duplicity.

All methods in java are pass-by-value which means that the value passed as argument on a method won't change its value. But an object atributes can be changed like arrays and Collections.

static member are related directly to the class and not to the instance, but it can be accessed from instance.

A static method cannot access instance variables, but instance methods can access static variables.

## Working With Java Data Types 

Primitives cannot be null.

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

Garbage Collection cannot be forced to run, althought it has the method "System.gc()", it cannot force JVM to do the Garbage Collection.

Objects are elegible for Garbage Collection when they have no reference to an object from heap.

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
5  |  "|"  |  Left to Right
4  |  &&  |  Left to Right
3  |  ||  |  Left to Right
2  |  ? :(ternary)  |  Right to Left
1  |  =, +=, -=, +=, /=, %=  |  Right to Left

Larger number means higher precedence.

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

For example "new int[3]" will set three ([0, 0, 0]) and "new String[3]" will set three null([null, null, null]).

array index begin in 0 and goes until its length - 1.

When trying to access an inexistence index, it will throw an "ArrayIndexOutOfBoundsException".

arrays in java are objects.

to print array structure you need "Arrays.toString()", otherwise will print a generic object String.

Arrays important methods:

* sort: Sorts the specified range of the specified array of objects/types into ascending order, according to the natural ordering of its elements
* binarySearch: Searches a key within an array, the array must be sorted before or be already sorted to return a valid index.
* asList: transforms an array into a List. Transformed List with asList cannot add new values to the list.

varargs are types defined with "..." after it, it's only usable as the last argument from a method.

varargs can be overriden or override an array, thought it throws a warning.

## Using Loop Constructs 

while structre: while(A) B, being A a boolean return condition, B will be ran only if condition A is true.

for structure: for(A;B;C) D, being A a initialization statement, ran before every statement.B is the conditional statement that needs a boolean return, ran after A. C is the update statement, but it's not ran before the first loop, it mean D runs before C. D is ran only if condition B is true.

do-while: do A while(B), being A the loop logic execution, it will run at least one time. B is the conditional statement that needs a boolean return, ran after B and validates if the execution will run again or not.

for-each: for (A) B, being A specific "for-each" statement that sets a non Collection or non array value to be treated in B execution, from a Collection or array value.

The conditionals within the loops, cannot be set to be constant true, it must have a way to break or at least make it unclear if the loop will be infinite or not.

## Working with Methods and Encapsulation 

modifiers(from most acess to least):

* public: any class has access to it.
* protected: any class within the same package and child class from the protected member class can access it.
* default or package-private: any class within the same package can access it.
* private: only the member owner can access it.

## Working with Inheritance 

A class that defines an instance variable with the same name as an instance variable from its parent class is referenced as "hidden".

A class that defines a static method with the same signature as a static method from its parent is referenced as "hidden".

Java does not support multiple inheritance for classes, only for interfaces.

Methods from interface are implicit "public".

"final", "static" and any other access modifier besides "public" cannot be declared on an abstract method.

if two different interfaces has the same static or default method(dispite de implementation), the class implementing both, must implement a new method default or static.

Concrete classes must implement all abstract classes from its parent.

Overloaded methods rules:

* methods must have the same name.
* methods must have different argument list.
* method can or cannot have different return types.
* method can or cannot have a different access modifier.
* method can or cannot have a different checked or unchecked exception.

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

## Handling Exceptions 

![Throwable structure](http://journals.ecs.soton.ac.uk/java/tutorial/java/exceptions/images/throwableHierarchy_trans.gif)

Error's should not be declared or catch.

Exception and its covariants(except for RuntimeException and its covariants) are checked exceptions, and must be declared to method and/or catch within a try-catch statement.

RuntimeException and its covariants are unchecked exception, and can or cannot be declared to method and/or catch within a try-catch statement.

Important checked exceptions: IOException, FileNotFoundException, SQLException, DataAccessException

Important unchecked exceptions: NullPointerException, ArrayIndexOutOfBound, IllegalArgumentException, IllegalStateException, ClassCastException, ArithmeticException, NumberFormatException

Important Error's: StackOverflowError, OutOfMemoryError

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

Two different instances of ArrayList are "equal" when its contents are similar.

lambda is important to define deferred executions for functional interfaces.

Source  | Data
------------- | -------------
Take Exam  | <https://education.oracle.com/java-se-8-programmer-i/pexam_1Z0-808>
Exam Simulation(pt-br)  | <https://www.udemy.com/metodologia-de-certificacao-java-8-oca-simulados/learn/v4/overview>