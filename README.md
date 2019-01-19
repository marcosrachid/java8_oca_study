# JAVA 8 OCA STUDY TIPS

Tips for OCA exam

## Java Basics

main structure: public static (final) void main([any String array declaration, like String[] args or String args[] or String... args])

## Working With Java Data Types 

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

## Using Loop Constructs 

## Working with Methods and Encapsulation 

All methods in java are pass-by-value which means that the value passed as argument on a method won't change its value. But an object atributes can be changed like arrays and Collections.

## Working with Inheritance 

A class that defines an instance variable with the same name as an instance variable from its parent class is referenced as "hidden".

A class that defines a static method with the same signature as a static method from its parent is referenced as "hidden".

Methods from interface are implicit "public" except for "default" and "static" methods.

## Handling Exceptions 

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