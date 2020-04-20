JavaScript(JS)
==============
It is a light weight,interpreted, object oriented languages with first class functions.
It is commonly used as a scripting language for webpages.
but it is used in many non browser environments as well.

light weight - easy to implement,small memory footprint
interpreted - No compilation instructions executed directly.
object oriented - modeled around objects
first class functions - functions as values.
scripting language - where instructions are written for runtime environment.

In the Javascript the common runtime environment is web browser

How browser interprets the incoming webpage.
Browser will make a request to the server to give a particular webpage. the webpage will have the html content with so many tags like html,body,div,p here browser will create an object for each tag and creates a DOM(Document Object Model) tree(eg: if div tag has p tag then browser will create p object as child element to div object).
and this DOM tree will be reflected in the view.
If you load the same html content same DOM tree will be constructed and reflected in the view, but incase of Javascript with html there is an oppurtunity to change the DOM tree like adddition or deletion of nodes based on the user actions and the resultant DOM tree will be reflected on the browser.

Advantanges of JavaScript
=========================
using javascript we can write client side web development.
client side Javascripts are
1. Native Javascript(pure javascript)
2. jquery(framework for JS)
3. Angular JS,React,Ember(framework for JS)

we can also write server side development.
1. Node JS
2. Express

Most of the browser extensions in chrome and mozilla are built using Javascript
used to build mobile applications,desktop applications and IOT applications.

History
=======
JavaScript was designed by Brendan Eich at Netscape.
Motives behind Design
=====================
Easy to use(which will not alert if we do wrong things and makes assumptions for those wrong things).
created to complement Java(Server side language) for client side language

Javascript has specification standard called ECMAScript.
Latest version of ECMAScript is 6.0

Variable Declaration
====================

    var variable = 24;
Here in JS there is not type that we have to mention and it dynamic typed variables.
in the next line we can write 
    var variable="Hello World";

another way of declaring a variable
    var variable;
    variable=24;
    
Primitive types in Java
=======================
1. Number
2. String
3. Boolean
4. Undefined
5. null
6. Symbol(introduced in ECMAScript 6) - which is similar to enum which will have bunch of values and has one value at runtime.

1. Number is a double precision 64 bit value(there is no      Integers )
    var a=0.4;
2. String is a sequence of unicode characters(16 bit).
There is no character type, A character is a string of length 1.
3. Boolean type is of true or false value.
Javascript has only the above three types which is very simple.

Javascript is a dynamic typed or loose typed or weak typed language because at any point of time we can't whether a variable will hold a Number type or string type or boolean type.

eg: var a =10;
    var b=20;
    var c=a+b;
    var d="Hello";
    var e =true;
    a="Hello Javascript"; Here this is accepted because JS is dynamic typed language
    
There is one more type in addition to the above types
"Undefined"
    var value;  -> declaration
    value=25;   -> definition

What is the value that is assigned between variable declaration and variable definition?
In Java default values are assigned between these two states(declaration and definition) i.e., 0 for integers null for objects etc. but in case of JS undefined value is assigned to a variable between when the variable is declared.
Undefined is a value of type Undefined
i.e., in undefined type there is only one value undefined like two values in boolean type.

null is a value of type Null.
In Null type only one value is there that is null

When we need to use Undefined v/s null
======================================
if a variable is defined but not declared browser will automatically allocates a value undefined to indicate a non value.

During the program execution if we want a variable to be non value then we need to explicitly assgin a value null, indicating that the value is a non value(not applicable in that context).
eg: Middle name for a person
some persons will not have middle name then in that context we need to explicitly assign null value to indicate a non value instead undefined.

Key points of variables and types
==============================
1. No need to declare variable type.
2. same variable can be assigned different types.
3. No scoping information in variable declaration.
4. variables and values can be interrogated.
    meaning in Javascript we are not sure of type of a variable at a particular point since it is a dynamic typed language.so there is a "typeof" operator which will return the type of a variable at that instant.This typeof operator can be used with values as well.
    Syntax:
        typeof <value>
            (or)
        typeof <variable>
        
eg:

var a;
console.log(typeof(a)); -> undefined
a=10;
console.log(typeof(a)); -> number
a="Hello";
console.log(typeof(a)); -> string
a=true;
console.log(typeof(a)); -> boolean
a=null;
console.log(typeof(a)); -> object(this should ideally return null type but it will return object instead which is a bug in javascript which cannot be corrected by javascript developers due to code break issues).

console.log(typeof("Hello")); -> string

Type Coersion
==============
Some times the interpretor will convert variable of one type to another type inorder to make the statement valid.This is called type coersion.

    123+"4" -> This is valid and the interpretor will convert the 123 number to string so the result will be "1234"
    
"==" & "===" operator
=====================
var a=10;
var b=10;
if(a==b) {
  console.log("values are equal");
}else {
  console.log("values are NOT equal");
}
Here obviously it will print values are equal

var a=10;
var b="10";
if(a==b) {
  console.log("values are equal");
}else {
  console.log("values are NOT equal");
}

Here the output is values are equal.
but when var b="10" ->string type
the above code will print values are equal.
Reason:Since Javascript is made easy to use what the interpretor will do is the user has done some mistake so it will make assumptions and see if it can do type coersion the value of number to string and compare the result.hence the above program for var b="10" will result in values are equal.
If we want interpretor not to take any assumptions then we have to use === operator

var a=10;
var b="10";
if(a===b) {
  console.log("values are equal");
}else {
  console.log("values are NOT equal");
}

Here the output is values are NOT equal.

This conversion is not there in JAVA. 

Type coersion summary
=====================
Javascript is flexible with typing(means the interpretor will typecast if possible).
Always use === for precise checking(It will check both value and type)
Values of all types have an associated boolean value.
For Integer all Nonzero values means true 
                Zero value means false.
For String any string with atleast one character is true.
                Empty string is false.
Boolean true is true and false is false.
Undefined value is always false.
null value is always false.

var a=10;
if(a) {
  console.log("a is true");
}else {
  console.log("a is false");
}
output : a is true

var a=-10;
if(a) {
  console.log("a is true");
}else {
  console.log("a is false");
}
output : a is true

var a=0;
if(a) {
  console.log("a is true");
}else {
  console.log("a is false");
}
output : a is false

var a="Hello";
if(a) {
  console.log("a is true");
}else {
  console.log("a is false");
}
output : a is true

var a="";
if(a) {
  console.log("a is true");
}else {
  console.log("a is false");
}
output : a is false

var a=undefined;
if(a) {
  console.log("a is true");
}else {
  console.log("a is false");
}
output : a is false

var a=null;
if(a) {
  console.log("a is true");
}else {
  console.log("a is false");
}
output : a is false

If statement can accept a variable which will have associated boolean value this is not the case in JAVA language.

OBJECTS
=======
JavaScript is an Object Oriented Language which is NOT class based unlike java.
In javascript objects are free formed because JavaScript doesn't have classes which will have a template on what the object should contain, so during runtime we can add properties(member variables) or remove properties,add methods and remove methods.

Object Intializaiton:
    var myObj={};
    
    
var myObj={}; -> empty object
console.log(myObj);
myObj.prop1="hello"; -> adding string property
myObj.prop2=123; -> adding number property
console.log(myObj);
console.log("The Number property :"+myObj.prop2);

output:
=======
Object {  }
Object { prop1: "hello", prop2: 123 }
The Number property :123

Another way of defining object upfront:

var myObj={
  prop1:"hello",
  prop2:123,
  prop3:true
};

console.log(myObj);

output
======
Object { prop1: "hello", prop2: 123, prop3: true }

if we try to access a property that is not there in the object we will not get any error as the object is is free form and compilation step is not there to check this error instead it will give undefined.
console.log("Properyt which doesn't exist:"+myObj.prop4);
The above line output is undefined

Here the property doesn't have any access modifiers like private,public,protected and all these properties are accessible.
  
Objects Summary
===============
1. Objects are free formed - not bound to class
2. New properties can be added directly on the object.
3. object properties can be accessed directly.
4. Objects can have methods.
5. we can use object literal notation({}) to create objects.

[] operator and when to use
===========================
 we have to use this [] operator 
    when we have a reserved words.
    when property name starts with number.
    when property name that we are going access is Dynamic.
    
If there is a chance to use . notation instead of [] notation use . notation because if we use [] notation the javascript engine maynot opportunity to optomize.

. and [] notation are interchangable.

eg:
var myObj={
  prop1:"hello",
  1:"one"
};

console.log(myObj);
console.log(myObj.1); -> here we will get error
so we have to use [] notation
console.log(myObj["1"]);

when we property name is dynamic
var propertyName="prop1";
console.log(myObj[propertyName]);

Nesed Objects
=============
var outerObj = {
  prop1:"hello",
  prop2:1,
  innerObj:{
    innerprop1:"world",
    innerprop2:2
  }
}

console.log(outerObj);

=== operator for objects
-------------------------
If both objects are pointing to the same locatin in the heap(browser memory) then both objects are equal.

var obj={
  prop:"hello"
}

var obj2=obj;
console.log(obj2.prop); -> hello
console.log(obj===obj2); -> true

How to delete a property from an object
=======================================
By using "delete" keyword.

delete obj.propertyName;

var obj={
  prop:"hello",
  age:25
}

console.log(obj); -> Object { prop: "hello", age: 25 }
delete obj.age;
console.log(obj); -> Object { prop: "hello" }

Arrays
======
Array Intialization
var myArray=["Hello","world","JS"];
console.log(myArray[0]); -> Hello
console.log(myArray[1]); -> world
console.log(myArray[2]); -> JS
console.log(myArray[3]); -> undefined

how to add element to an array?
myArray[4]="new element";


we can access array lenght by using length field.
myArray.length
This concludes that array is a object under the hoods where lenght is a parameter which will store the lenth of the array.

var myArray=["Hello","world","JS"];
myArray[10]="new value";
console.log(myArray);

the array representation for this one is 
0:"Hello"
1:"world"
2:"JS"
10:"new value"
length:11

Here lenght will store the value "max index value +1" instead of number of elements.

why this statement is working if array is an object under the hoods.
myArray[10]="new value"
instead of
myArray["10"]="new value"
Here JS interpretor was doing type coersion from number to string.

so accessing a value in a array which is not defined will result in undefined(because array is an object)
so myArray[100] -> undefined

Wrapper Objects
===============
Each primitive value will have a corresponding wrapper class.
number will have Number wrapper class.
string will have String wrapper class.
boolean will have Boolean wrapper class.
symbol will have Symbol wrapper class.

var myString="Hello World";
console.log(myString.length);
if myString is a string type then how myString.lenght worked because at line number 409 myString will be converted into String wrapper object for executing that piece of line.
if we do typeof of myString we will get as string only
because it will be converted into string wrapper object only at line number 409 implicitly inorder to execute that line.

Functions
=========
we can define functions in JS by using "function" keyword.
eg:
function display() {
  console.log("Hello");
}

display();

functions with parameters:

function display(name) {
  console.log("Hello :"+name);
}

display("Leela");

Here the argument doesn't have datatype because in JS every variable is declared with var. so we no need to specify explicitly as "var name".

functions with multiple parameters:

function display(name,middleName) {
  console.log("Hello :"+name+" Middle Name :"+middleName);
}

display("Leela","prasad");

what happens if we didn't pass the second argument(middleName) it will show an error instead the value of the second variable becomes undefined. which is not the case with other languages like Java(Strict language).

what happens if we pass extra parameters like
dispaly("Leela,"prasad","jagu");
JS will simply ignore the extra parameters.

This will lead to a conclusion that JS will not have "method overloading" feature.

Functions with return value
============================
functions will return value using "return" keyword

function display(name,middleName) {
  return "Hello :"+name+" Middle Name :"+middleName;
}

var returnValue = display("Leela","prasad","jagu");
console.log(returnValue);

function with no return value
=============================
function display(name,middleName) {
  console.log("Hello :"+name+" Middle Name :"+middleName);
}

var returnValue = display("Leela","prasad","jagu");
console.log(returnValue);

here the value of returnValue variable is undefined.

we can return no values using simple return statement.

function display(name,middleName) {
  console.log("Hello :"+name+" Middle Name :"+middleName);
  return;
}

var returnValue = display("Leela","prasad","jagu");
console.log(returnValue);

Function Expressions
====================
In Javascript functions are first class values means functions can be assigned as values to a variable.
var f=function foo() {
  console.log("Inside function");
}; 

f();
Here foo function is assigned to variable f
and function will be executed only when this statement is executed f();

Anonymous Function Expressions
==============================
A function without name. because it is not needed to explicitly mention function name to execute a function.

var f=function () {
  console.log("Inside function");
};

f();

Function as arguments
=====================
var f=function(name) {
  console.log("Hello "+name);
};

var executor=function(name) {
  f(name);
};

executor("Leela");

Functions inside objects
========================
var myObj= {
  prop:"Hello"
};

myObj.myMethod=function() {
  console.log("Function inside object");
}

myObj.myMethod();

this keyword
=============
this(self object reference)
used to refer current object instance.

var myObj= {
  firstName:"Leela",
  lastName:"Jagu",
  fullName:function() {
    return this.firstName + " " + this.lastName
  }
};

console.log(myObj.fullName());

eg:
var myObj= {
  firstName:"Leela",
  lastName:"Jagu",
  fullName:function() {
    return this.firstName + " " + this.lastName
  },
  address: {
   street:"Brahmin Street",
   city:"Vijayawada",
  state:"AP"
  },
  isFromState:function(state) {
   return this.address.state===state;
  }
};

console.log(myObj.fullName());

console.log(myObj.isFromState("AP"));


Default Arguments for functions
===============================
1. arguments
2. this

arguments variable is avaiable to every funciton declared in JS.
in c or java if we have n number of arguments we will use varargs concept to hold those values,here in javascript we don't need to declare this varargs explicitly but available for all the functions in JS.
Here arguments is an object but not an array eventhough it will store the input arguments with 0,1,2,3,4... indexes and having lenght property.

var f=function() {
  console.log(arguments);
}

f(1,5,2,8,4,0,7);

output:
Arguments { 0: 1, 1: 5, 2: 2, 3: 8, 4: 4, 5: 0, 6: 7, 2 more… }

Adding input values:

var f=function() {
  var i,sum=0;
  
  for(i=0;i<arguments.length;++i) {
    sum+=arguments[i];
  }
  return sum;
}

console.log(f(1,5,2,8,4,0,7));


Functions Summary
=================
1. Funtions can be written in literal form.
2. function is a value that can be assign to a variabel.
3. functions can be passed as arguments.
4. functions are objects under the hood.
5. No function overloading
6. default arguments(arguments & this)

Normal Function Declaration
Function Expression
Anonmyous Function Expression
function as object property


Array functions
===============
1. push(""); inserts element at the lastindex+1 position
2. pop(); removes last element.
3. shift(); removes first element.
4. unshift(""); adds elements at 0 index

forEach() method in arrays
==========================
Arrays forEach has a powerful functionality of accepting functions as an argument(because in JS functions are functions are first class values).

var myArray=[5,6,4,1];

console.log(myArray);
var f=function(item,index) {
  console.log("executing in for each loop);
}

myArray.forEach(f);

output:
executing in for each loop -> 4 times

Implicitly forEach method passes these arguments by default
1. value of the array.
2. current index.
3. array itself.

var myArray=[5,6,4,1];

console.log(myArray);
var f=function(item,index,array) {
  console.log("executing in for each loop "+item+" index :"+index + "array :"+array);
}

myArray.forEach(f);


output:
executing in for each loop 5 index :0array :5,6,4,1 
executing in for each loop 6 index :1array :5,6,4,1 
executing in for each loop 4 index :2array :5,6,4,1 
executing in for each loop 1 index :3array :5,6,4,1


Need to study about math object and date object

* Javascript is actually single threaded so it lead to idea of asyncronous javascript which will lead to responsive program(using callbacks and promises). 


Scopes
======
Every language will have two types of scopes.
1. local scope.
2. global scope.

In most of programming languages local scope will be creted by blocks like 
 
 {
 
 }
 
 if(...) {
 
 }
 
But in case of Javascript blocks will not provide local scope. to get this local scope we need to go for "funciton" scoping i.e., we need to wrap that inside a function.

eg:

var name="leela";

if(name==="leela") {
  var department="Engineering";
}

console.log(name);
console.log(department);

output:
leela
Engineering

Here the department is declared in if statement but it is accessible outside of if statement because in JS local scope will not provided by blocks.

var name="leela";

function assignDepartment() {
   if(name==="leela") {
    var department="Engineering";
  }  
}

console.log(name);  -> this statement is valid
console.log(department);    -> here we will get error because interpretor will not able to find variable department.

var inner=50;

function foo() {
  var inner=20;
  console.log(inner);   -> 20
}

foo();
console.log(inner); ->50

In Javascript declaring variables in Global scope is not recommended because...

var a=10;
var b=20;
console.log(a+b);

Here our program creates variable a,b in global scope suppose if some other javascript file or library file also creates same variable a in global scope then we will lose the value of a which will update by some other file a. hence interference problems will come, so creating variables in global scope is not recommended and always wrap variables in function scope like...

function foo() {
    var a=10;
    var b=20;
    console.log(a+b);
}

foo();


var name="leela";

function foo(name) {
  console.log("Hello "+name);
}

foo("prasad");

output: Hello prasad

creating a funciton like this also will create problems...

function foo() {
    var a=10;
    var b=20;
    console.log(a+b);
}

foo();

meaning if some other javascript file or other library file which is having same function name "foo" then we will loose funciton foo which may be updated by our local or other JS copy, so creating anonymous functions are always recommended in Javascript and most of th JS files will have anonymous functions.

function() {
    var a=10;
    var b=20;
    console.log(a+b);    
}

then how to execute the above function?
for this we will pass function as a argument to the code which needs that function and it will be executed there itself, this type of funcitons are called IIFA(Immediately Invoked  Function Expression)

(function() {
    var a=10;
    var b=20;
    console.log(a+b); 
})();

Read and Write operations in JS
===============================
var a=10;
here we are assinging value to a means we are "a" is in write mode

console.log(a);
here we are printing value and here "a" is in read mode.

In JS we can do read and write operations if we declare a variable.

var a;
console.log(a) -> undefined

-----

var a=10; -> valid


But if we don't declare a variable we can do write operation but we CANNOT do READ operation.

foo=10; -> accepted

---

console.log(foo) -> interpretor will throw error


Global Object(window)
=====================
window is a global object that is available on all browsers.
when we create global variables, then these variables are added to the member variables of window object.
when we create global functions then these functions will be added to teh member variables of window object.
so when we create global variables or functions it will go as member variable of window global object.

if we create global variables and functions like below
var a=10;
function foo() {
    console.log("foo function");
}

window object:
--------------
DATABASE_NAME:"abouthome"
a:10
.
.
foo:foo()
focus:focus()
.
.


Javascript is not purely interpreted language.
we have both compilation and interpretation step that will happen.
compilation step will execution in a fraction of second before the interpretation step executes. that's why we will think that there is no compilation step in Javascript.

In compilation step what will happen it will indentify all the variables and place it in corresponding scope block.

In Interpretation step what will happen it will take the variable from the current scope, if it doesn't find the variable in the current scope then it will go one level up and check the variable in that scope this will happen till it hit the global scope.

compilation step examples
=========================
eg1:
var a=10;
var b=20;
console.log(a+b);

scopes:

Global
------
a
b

eg2:

var a=10;
function myFunc() {
    var b=20;
    var c=b;
    console.log(a+b);
}

myFunc();

Global
------
a
myFunc

myFunc
-------
b
c

eg3:

var myName="leela";
function greet(name) {
    console.log("Hello "+name);
}
greet(myName);

Global
-------
myName
greet

greet
-----
name

Intrepretation step examples:
=============================
var myName="leela";
function greet(name) {
    console.log("Hello "+name);
}
greet(myName);

Global
-------
myName
greet

greet
-----
name

In compilation step variables will be indentified and places in the corresponding scope.

now at line885 it will assign "leela" to myName since it is in global scope it will check the global scope namescape and asks for the variable myName since it exist in global scope it will return and the interpretor will assign "leela" to that variable.

then it will come to line889 and ask for greet in global scope the global scope will give and interpretor will execute greet method

now greet method will ask for "name" in greet scope here it will give the name variable because it is there in that scope, if this variable is not there in the greet scope then it will go one level up and check it in global scope.
then name variable is assigned with leela and console.log statement will be executed.

Automatic creation of variables in Global scope during interpretation step
=======================================================

var a=10;

function myFn() {
    var b=a;
    console.log(b);
    c=100;
}
myFn();

Global
------
a
myFn
c

myFn
----
b

during interpretation when it come to this line
c=100;
it will search for this variable in myFn scope it will not find it will go one level up and searches in global scope it will not find, since it is a write operation interpretor will think that the developer want this variable and creates that variable in global scope. If it is a read operation then it will thrown error.
Creating variable in global scope is not recommended and should be avoided, so atleast we have to declare all the variables with var to avoid this situation.

examples

var a=10;

function outer() {
    var b=a;
    console.log(b);
    function inner() {
        var b=20;
        var c=b;
        console.log(c)
    }
    inner();
}

outer();

Global
------
a
outer

outer
-----
b
inner

inner
-----
b
c


var a=10;

function outer() {
    var b=a;
    console.log(b); -> 10 
    function inner() {
        var c=b;
        console.log(c); -> undefined
        var b=20;
    }
    inner();
}

outer();

Global
------
a
outer

outer
-----
b
inner

inner
-----
c
b

output:
10
undefined


console.log(a);
var a=10;
here output is undefined
this type is called hoisting.

Hoisting
========
In JS during interpretation step all the variables declared with the var and functions are defined in the respective global scope. This is called Hoisting. This is required in some cases.

a=10;
console.log(b);
c++;
var a;
var b;
var c;

the above code is valid and during interpretation step all the variables are decalred in global scope it looks as if all the variables are declared at starting point.

myFn();

function myFn() {

}

valid because myFn() will be registered in global scope during compilation step.

function fnA() {

    fnB();
}

function fnB() {

    fnA();
}

valid because fnA() and fnB() will be registered in global scope during compilation step.

fnA();

var fnA=function() {

}

It will thrown exception during interpretation because during compilation step var fnA will be created and function is not assigned to fnA because it is responsibility of interpretor to assign. so fnA here is a normal variable.
here interpretor will execute fnA(); since at this point fnA is a normal variable it will thrown an error.

fnA();
function fnA() {

}

It is valid because function name fnA()  will be registered in global scope during compilation step.

Moving the variable decalartion up during compilation step is called Hoisting.

Problem:Javascript will create a new variable in global namespace whenever we didn't declare a variable and use that variable for write operation.
To avoid this situation like creation of variable when it is not declared we have to use JS in "strict mode".

usage : "use strict";


eg:

var myName="";

myname="leela";
for this code what JS will do is it will create two variables myName and myname in global name space and that is bad because the programmer made a typo mistake in using the variable name. so it is always recommended to use JS in strict mode which will remove all these undesired behaviours.

"use strict";
var myName="";
myname="leela"; -> here JS will thrown an error that myname variable is not declared.

most of the times library functions will not execute in strict mode.so how to solve this, well we can use strict to parts of the code like we can use strict mode in function block also

function myCode() {
"use strict";
var myName="";
myname="leela";
}

Closures
========
A function which remembers its scope is called Closure.

var a=10;

function outer() {
  var b=20;
  var inner = function() {
    console.log(a);
    console.log(b);
  }
  return inner;
}

innerFn=outer();
innerFn();

output:
10
20

Here we are returning inner function to execute somewhere else or completely in different file, then how it will have access to "a" and "b". This is because of Closures.
In JS when a function is defined it remembers the scope of the variables(means it have the pointer of a and b). so whenever it access the variables it will get the values from that pointer.

var a=10;

function outer() {
  var b=20;
  var inner = function() {
    console.log(a);
    console.log(b);
  }
  return inner;
}

innerFn=outer();
a=-1
innerFn();

output:
-1
20

Module Pattern
==============
var myObj = {
    firstName:"leela",
    lastName:"Jagu",
    getFirstName:function() {
      return this.firstName;
    },
    getLastName:function() {
      return this.lastName;
    }
}

console.log(myObj.getFirstName());
console.log(myObj.getLastName());
console.log(myObj.firstName);

Here we are able to access the firstname and lastname by using myObj.

---

person = function() {
  var firstName="leela";
  var lastName="Jagu";
  var myObj = {
    getFirstName:function() {
      return firstName;
    },
    getLastName:function() {
      return lastName;
    },
    setFirstName:function(name) {
      firstName=name; 
    },
    setLastName:function(name) {
        lastName=name;
    }
  }
  return myObj;
}

myNewObj=person();
console.log(myNewObj.getFirstName());
console.log(myNewObj.getLastName());
myNewObj.setFirstName("firstname");
myNewObj.setLastName("lastname");
console.log(myNewObj.getFirstName());
console.log(myNewObj.getLastName());
//console.log(myNewObj.firstName);

Here what we have done is moved the firstName and lastName outside the object and moved to function scope, so that outside world cannot directly access those variables instead they have to access through getters and setters.
getters and setters will remember these variables because functions will remember the scope and this concept is closure.
This type of creation is called as "Module pattern"


Closures in async callbacks
===========================
for(i=0;i<10;++i) {
  console.log(i);
}

Here the output will be
0
1
2
3
4
5
6
7
8
9

---

var i;

print=function() {
  console.log(i);
}

for(i=0;i<10;++i) {
  setTimeout(print,1000);
}
Here the output will print 10 for 10 times
Reason: 
whensetTimeout function is called it waits for 1sec before printing it to console meanwhile for loop will execute for next iteration and i will become 1 now another setTimeout function will be called and it waits for 1 sec before printing it to console meanwhile for loop will execute for next iteration and it continues like this and for loop execution will be over.after this async calls will be executed at this point of time i will be pointed to 10 
so it will print all 10 async calls with 10 for 10 times.


for(var i=0;i<10;++i) {
  
  (function() {
    var currentValueOfI=i;
    setTimeout(function() {
      console.log(currentValueOfI);
    },1000);  
  })();
  
}

Objects
=======
one way to crete object:
  var employee = {};
  employee.firstName="leela";
  employee.lastName="jagu";
  employee.gender="M";
  employee.designation="Analyst";
  
Generally we will make of functions to create an object so that we don't write all the lines of code that are shown above every time.  

object creation using functon
=============================
function createEmployeeObject(firstName,lastName,gender,designation) {
  var employee = {};
  employee.firstName=firstName;
  employee.lastName=lastName;
  employee.gender=gender;
  employee.designation=designation;
  return employee;
}

emp1 = createEmployeeObject("leela","jagu","M","Analyst");
console.log(emp1);

when we want to create an object in languages like java or c we will use constructors to create. In JS also we can create objects using JS constructors which is some what different from java/c constructors.
In JS functionname will become the constructor name when we use new keyword while calling that funciton name whereas in java/c the constructor name is class naem.
new keyword makes the function as a constructor.
In the above code the first line intializing an empty object and last line returning an object are redundent and is required for all the constructor, so JS will provide these two lines out of the box and here the objectname will be "this".

object creation using constructor
=================================
function createEmployeeObject(firstName,lastName,gender,designation) {
  //var this = {};
  this.firstName=firstName;
  this.lastName=lastName;
  this.gender=gender;
  this.designation=designation;
  //return this;
}

emp1 = new createEmployeeObject("leela","jagu","M","Analyst");
console.log(emp1);

the new keyword makes the createEmployeeObject as constructor.

new keyword makes the function to call in constructor mode. 

Creating Objects in different ways
==================================
var bicycle1 ={
  cadence:50,
  speed:20,
  gear:3
};
    
function createBicycle(cadence,speed,gear) {
  var newBicycle={};
  newBicycle.cadence=cadence;
  newBicycle.speed=speed;
  newBicycle.gear=gear;
  return newBicycle;
}

var bicycle2=createBicycle(30,15,2);

function Bicycle(cadence,speed,gear) {
  //var this={};
  this.cadence=cadence;
  this.speed=speed;
  this.gear=gear;
  //return this;
}

var bicycle3=new Bicycle(20,10,1);

console.log(bicycle1);
console.log(bicycle2);
console.log(bicycle3);

what happens if we switch the modes in calling a function
=========================================================
1. calling a normal funcitona as a constructor function.
2. calling a constructor funciton as a normal function.

1. calling a normal funcitona as a constructor function.

function createBicycle(cadence,speed,gear) {
  var newBicycle={};
  newBicycle.cadence=cadence;
  newBicycle.speed=speed;
  newBicycle.gear=gear;
  return newBicycle;
}

var bicycle = new createBicycle(50,30,3);

here we are calling a normal function in constructor mode by using new keyword. since it called in constructor mode constructor will add extra lines of code at tbe begining and end of the funciton like.

function createBicycle(cadence,speed,gear) {
  //var this={};
  var newBicycle={};
  newBicycle.cadence=cadence;
  newBicycle.speed=speed;
  newBicycle.gear=gear;
  return newBicycle;
  //return this;
}

Here this object is created but it is not used so it is wasted and return this will not be executed as we have another return statement above that line which returns object that we constructed. So calling a normal function in constructor mode will not cause any issue.

2. calling a constructor funciton as a normal function.

function Bicycle(cadence,speed,gear) {
  //var this={};
  this.cadence=cadence;
  this.speed=speed;
  this.gear=gear;
  //return this;
}

var bicycle = Bicycle(50,30,3);

since we are not calling Bicycle in constructor mode using new keyword the line at the begining and end will not be added and the function will look like.

function Bicycle(cadence,speed,gear) {
  this.cadence=cadence;
  this.speed=speed;
  this.gear=gear;
}

so this function will not return any value so the variable bicycle will have undefined.
so calling a constructor function in normal mode will not work and it not recommended to mix these things.

4 Ways to call function in JS
============================
For Every funciton JS will provide 2 implicit objects.
1. arguments 2. this

1. calling as a normal function.

function foo() {
  console.log("Hello");
  console.log(this);
}

//Method #1
foo();

In this case this will point to the global object.
If JS is running in a browser then global object will be window(the tab where it is running), incase of NodeJS global object will be global.

output:
Hello
Window → about:home

2. calling a function as a parameter of object

var myObj={};
myObj.foo=function() {
  console.log("Hello");
  console.log(this);
}

//Method #2
myObj.foo();

In this case the this will be the object on which the function is called.

output:
Hello
Object { prop: "value", foo: myObj.foo() }

3. calling funciton in constructor mode

function foo() {
    console.log("Hello");
    console.log(this);
}

//Mehtod #3
new foo();

In this case compiler will create a empty this value at the begining of the function and return that this variable at the end of the function. since in the above function we are not assigning any value to this the return value will be empty.

output:
Hello 
Object {  }


*this reference can be different for different functions in case nested funcitons.

function Bicycle(cadence,speed,gear,tirePressure) {
  this.cadence=cadence;
  this.speed=speed;
  this.gear=gear;
  this.tirePressure=tirePressure;
  this.inflateTires=function() {
    this.tirePressure +=3;
  }
}

var bicycle1 = new Bicycle(50,30,3,2);
bicycle1.inflateTires();

Here function Bycycle this reference means an empty object.
funciton inflateTires this reference will be an object on which it is called.

function Bicycle(cadence,speed,gear,tirePressure) {
  this.cadence=cadence;
  this.speed=speed;
  this.gear=gear;
  this.tirePressure=tirePressure;
  this.inflateTires=function() {
    this.tirePressure +=3;
  }
}

var bicycle1 = new Bicycle(50,30,3,20);
bicycle1.inflateTires();

function Mechanic(name) {
  this.name=name;
}

var mike = new Mechanic("Mike");
mike.inflateTires=bicycle1.inflateTires;
mike.inflateTires();

In the above example Mechanic(mike) want to inflate any bicycle but what is happening is mike is passed as this for function inflateTires(Method #3). 
this.tirePressure is not a property of mike object 
so undefined = undefined + 3 which a NaN
so the mike object will become.
Object { name: "Mike", inflateTires: Bicycle/this.inflateTires(), tirePressure: NaN }

so inorder to customize the value of this variable to the function we will use Method #4. i.e., call attribute.

call attribute is available for all functions out of the box and this will accept a value which is this reference.

mike.inflateTires.call(bicycle1);

now the inflateTires method this reference will be bicycle1 object instead of mike.

mike.inflateTires.call(bicycle2);

function Bicycle(cadence,speed,gear,tirePressure) {
  this.cadence=cadence;
  this.speed=speed;
  this.gear=gear;
  this.tirePressure=tirePressure;
  this.inflateTires=function() {
    this.tirePressure +=3;
  }
}

var bicycle1 = new Bicycle(50,30,3,20);
bicycle1.inflateTires();

function Mechanic(name) {
  this.name=name;
}

var mike = new Mechanic("Mike");
mike.inflateTires=bicycle1.inflateTires;
mike.inflateTires.call(bicycle1);

output:
bicycle1
Object { cadence: 50, speed: 30, gear: 3, tirePressure: 26, inflateTires: Bicycle/this.inflateTires() }
mike
Object { name: "Mike", inflateTires: Bicycle/this.inflateTires() }

Prototypes
==========
Every Function is an object.
Whenever we create a function it will create a object with function name as well as it will create a prototype object.

so function foo() {} will create foo object and prototype object.

whenever we are creating an object for a function by calling it in constructor mode then we will have that object which will have a extra attribute __proto__. This __proto__ attribute will point to the prototype object that was created when function object is created.

function foo() {}
foo object and prototype object are created.

var newFooObj=new Foo();
newFooObj will have the empty object with one extra property __proto__.
this __proto__ is pointed to foo function prototype object.

foo.prototype.baseprop="10";
newFooObj.__proto__.baseprop; answer will be 10 because __proto__ will be pointed to foo prototype object
foo.prototype===newFooObj.__proto__ -> true.

newFooObj.baseprop will also print 10 because JS engine first will check whether baseprop property is there in newFooObj in this case it is not there so it will ask the prototype object(__proto__) whether it is having since it is having it will return 10.


suppose newFooObj.baseprop="20";
now this will print 
newFooObj.baseprop; -> 20 
and this will print
newFooObj.__proto__.baseprop; -> 10

because newFooObj is also having baseprop property.

so the value coming from newFooObj.baseprop we are not sure whether it is having that property or it is coming from prototype.

what is advantage of defining functions or propeties in prototype instead declaring as another property varibles
=========================================================
functions or properties defined in prototype will be created only once for every object that are created from Function in constructor mode whereas if we declare these common properties as other properties then these things get replicated for all the objects that are created by functions in constructor mode.


eg:

function Employee(name) {
  this.name=name;
}

Employee.prototype.playPranks=function() {
  console.log("Played Pranks!");
}
emp1=new Employee("Jim");
emp2=new Employee("Pat");
emp1.playPranks();
emp2.playPranks();
Employee.prototype.getName=function(){return this.name};
Employee.prototype.getName=function(){return this.name};
console.log(emp1.getName());

output:
Played Pranks!
Played Pranks!
Jim

this prototype model is different from the class based model where we can define behaviour in prototype during runtime also whereas in case of class based model we have to define this behaviour upfront.


Every function will have prototype object which is used to define common behaviour for all the objects created by using this function in constructor mode.

Every object created from function in a constructor mode will have __proto__ which will point to prototype object of function.

This __proto__ is called Dunder prototype.

This Dunder prototype have a property "constructor" which will return the function from which it is created.

eg:

function foo() {}

var a = new foo();
var b = new foo();

a and b will have Dunder prototype which will point to foo prototype object.
Suppose in the middle of the program we forgot from which function "a" is created so we can use Dunder prototype property constructor to find this

a.__proto__.constructor -> it will give function foo()
b.__proto__.constructor -> it will give function foo()

we can also create an object by using this constructor property but it is not recommended.

var c = new a.__proto__.constructor();
now c.__proto__.constructor -> will give funciton foo()

actually these protoype and constructor are just references we can also change that if we want during the middle of the program but it is not recommended.

a.__proto__.constructor=function bar();

so now all the variables will point to bar function.
a.__proto__.constructor -> it will give function bar()
b.__proto__.constructor -> it will give function bar()
c.__proto__.constructor -> it will give function bar()


Object function
===============
There exist a global function which is called Object.
since every function is an object in JS. so it is Object function object.

so we can create an object like this.

var obj=new Object();

we can create a object like this also.

var simple={};

what is the difference between above two approaches in object creation well both are same.

obj.__proto__ === simple.__proto__ -> true
Object.prototype === simple.__proto__ -> true

Hence above two methods of creation of objects are same.

Prototype Object
================
Prototype is a object that gets created automatically when we create an object. 
so who is creating that prototype object well, that automatic prototype is created from Object Function.

function Employee() {}

var emp1 = new Employee();

emp1.__proto__ === Employee.prototype -> true
Employee.prototype.__proto__ === Object.prototype --> true
Object.prototype__proto__ -> null

So If a property is not available in emp1 object then it will search in Employee.prototype object if there also not available then it will search in Object.prototype if there also not available then it returns undefined.

Object.prototype.prop="Grand Parent Prototype";

now if we give emp1.prop it will return "Grand Parent Prototype".

Employee.prototype.prop="Parent Property";

now if we give emp1.prop it will return "Parent Property".

emp1.prop="property";

now if we give emp1.prop it will return "Property".

declaring common methods or variables in Object prototype is NOT recommended.


Inheritance
===========

function Employee(name) {
  this.name=name;
}

Employee.prototype.getName=function(){return this.name};
var emp = new Employee("Jim");


function Manager(name,dept) {
  this.name=name;
  this.dept=dept;
}

Manager.prototype.getDept=function(){return this.dept};
var mag = new Manager("Pat","Sales Manager");

This line will make the manager prototype dunder proto to point to Employee prototype so that common methods in Employee prototype will be accessible to manager as well
Manager.prototype.__proto__=Employee.prototype

emp.getName();
mag.getName();
mag.getDept();

output:
Jim
Pat
Sales Manager
