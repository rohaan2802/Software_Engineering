# Wrapper Class in Java

## Wrapper Classes in Java

In Java, a wrapper class is a class that "wraps" a primitive data type inside an object.  
Why do we need wrapper classes?  
Java has primitive types like:  
int  
double  
char  
boolean  
Sometimes Java APIs (such as collections like ArrayList ) work only with objects, not  
primitive types. Wrapper classes solve this problem by converting primitives into objects.  
Primitive Type → Wrapper Class  
Primitive  
Wrapper Class  
int  
Integer  
double  
Double  
char  
Character  
boolean  
Boolean  
float  
Float  
long  
Long  
short  
Short  
byte  
Byte  
Example  
Unboxing  
Converting a wrapper object back to a primitive:  
Real-Life Analogy  
Think of a primitive value as a letter and a wrapper class as an envelope around that  
letter.  
Letter = actual data ( int , double , etc.)  
Envelope = object ( Integer , Double , etc.)  
The envelope allows the data to be used where Java expects an object.  
Common Interview Answer  
Example:  
Here, ArrayList cannot store int directly, so it uses Integer (the wrapper class for  
int ).  
In one line: Wrapper classes are object versions of Java's primitive data types.  
int age = 25;          // Primitive type  
Integer ageObj = age;  // Wrapper object (Autoboxing)  
System.out.println(ageObj);  
Integer ageObj = 25;  
int age = ageObj;   // Unboxing  
System.out.println(age);  
A wrapper class is a class that converts a primitive data type into an object and vice  
versa. It allows primitive values to be used where objects are required, such as in  
collections and utility methods.  
ArrayList<Integer> numbers = new ArrayList<>();  
numbers.add(10);  
numbers.add(20);  

## Why Wrapper Classes Are Used and Their Ranges

Why do we use Wrapper Classes?  
Wrapper classes are useful because they provide features that primitive types don't have.  

### 1. To store values in collections

Collections such as ArrayList , HashMap , and HashSet can only store objects.  
You cannot do:  

### 2. To use utility methods

Wrapper classes provide useful methods:  

### 3. To represent null

Primitive types always have a value, but wrapper objects can be null .  
This is useful when a value is optional or not yet known.  
Do Wrapper Classes Have a Range?  
Yes. Since wrapper classes internally store primitive values, their ranges are the same as the  
corresponding primitive types.  
Wrapper Class  
Primitive  
Range  
Byte  
byte  
- 128 to 127
Short  
short  
- 32,768 to 32,767
Integer  
int  
- 2,147,483,648 to 2,147,483,647
Long  
long  
- 9,223,372,036,854,775,808 to
9,223,372,036,854,775,807  
Float  
float  
~±3.4 × 10³⁸  
Double  
double  
~±1.7 × 10³⁰⁸  
Character  
char  
0 to 65,535 (Unicode values)  
Example  
Output:  
Interview Tip  
If asked "Why use Integer instead of int ?", a concise answer is:  
ArrayList<Integer> numbers = new ArrayList<>();  
numbers.add(10);  
ArrayList<int> numbers = new ArrayList<>(); // Error  
String str = "123";  
int num = Integer.parseInt(str);  
System.out.println(num + 1); // 124  
Integer age = null;  // Valid  
int age2 = null;     // Error  
System.out.println(Integer.MAX_VALUE); // 2147483647  
System.out.println(Integer.MIN_VALUE); // -2147483648  
2147483647  
- 2147483648
We use Integer when an object is required (e.g., collections), when we need utility  
methods like parseInt() , or when a value may be null . int is generally faster and  
uses less memory.  
