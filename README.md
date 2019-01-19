# JAVA 8 OCA STUDY TIPS

Tips for OCA exam

## Java Basics

main structure: public static (final) void main([any String array declaration, like String[] args or String args[] or String... args])

Java is pass-by-value, which means methods cannot change value from passed arguments, only the Object state.

## Working With Java Data Types 

A byte/short/int/long instance variable is always initialized with 0 value.

A float/double instance variable is always initialized with 0.0 value.

A char instance variable is always initialized with '' value.

A boolean instance variable is always initialized with false value.

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

When trying to access an inexistence index, it will throw an "ArrayIndexOutOfBoundsException".

arrays in java are objects.

to print array structure you need "Arrays.toString()", otherwise will print a generic object String.

## Using Loop Constructs 

while structre: while(A) B, being A a boolean return condition, B will be ran only if condition A is true.

for structure: for(A;B;C) D, being A a initialization statement, ran before every statement.B is the conditional statement that needs a boolean return, ran after A. C is the update statement, but it's not ran before the first loop, it mean D runs before C. D is ran only if condition B is true.

do-while: do A while(B), being A the loop logic execution, it will run at least one time. B is the conditional statement that needs a boolean return, ran after B and validates if the execution will run again or not.

for-each: for (A) B, being A specific "for-each" statement that sets a non Collection or non array value to be treated in B execution, from a Collection or array value.

## Working with Methods and Encapsulation 

modifiers(from most acess to least):

* public: any class has access to it.
* protected: any class within the same package and child class from the protected member class can access it.
* default or package-private: any class within the same package can access it.
* private: only the member owner can access it.

All methods in java are pass-by-value which means that the value passed as argument on a method won't change its value. But an object atributes can be changed like arrays and Collections.

static member are related directly to the class and not to the instance, but it can be accessed from instance.

A static method cannot access instance variables, but instance methods can access static variables.

## Working with Inheritance 

Inheritance is important due developers can minimize code duplicity.

A class that defines an instance variable with the same name as an instance variable from its parent class is referenced as "hidden".

A class that defines a static method with the same signature as a static method from its parent is referenced as "hidden".

Methods from interface are implicit "public" except for "default" and "static" methods.

## Handling Exceptions 

![Throwable structure](http://journals.ecs.soton.ac.uk/java/tutorial/java/exceptions/images/throwableHierarchy_trans.gif)

The "catch" statements must always be orderer from least wide to most. 
Ex:
```
try {
} catch (Runtime re) {
} catch (Exception e) {
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

package java.time: LocalDate, LocalTime, LocalDateTime

java.time package Classes are imutable

Two different instances of ArrayList are "equal" when it's values are similar.

Source  | Data
------------- | -------------
Take Exam  | <https://education.oracle.com/java-se-8-programmer-i/pexam_1Z0-808>
Exam Simulation(pt-br)  | <https://www.udemy.com/metodologia-de-certificacao-java-8-oca-simulados/learn/v4/overview>