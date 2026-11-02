# let vs var in JavaScript

## let vs var in JavaScript

In JavaScript, let and var are both used to declare variables, but they behave quite  
differently. The differences matter a lot in real code.  

### 1. Scope

var → function-scoped  
let → block-scoped  
if（true){  
var a = 10;  
let b = 20;  
var ignores blocks（{}）like if，for  
let respects block scope  

### 2. Hoisting

Both are hoisted, but behave differently.  
console.log(x); // undefined  
var x = 5;  
var is hoisted and initialized as undefined  
let is hoisted but not initialized (Temporal Dead Zone)  

### 3. Re-declaration

var x = 10;  
var x = 20; / /  
allowed  
var allows redeclaration  
let does not  

### 4. Re-assignment

Both var and let allow reassignment (unlike const )  

### 5. Global Object Behavior

var x = 10;  
let y = 20;  
var attaches to global object ( window in browser)  
let does not  

### 6. Use in Loops (important difference)

for (var i = ; i < 3; i++){  
setTimeout(() => console.log(i), 100);  
// output: 3, 3, 3  
for （let j = θ; j< 3; j++){  
setTimeout(() => console.log(j), 1oo);  
let creates a new variable per iteration  
var shares the same variable  
When to use what?  
Use let → default choice  
Avoid var → legacy, can cause bugs  
Use const when value shouldn't change  
Simple summary  
var = old, function-scoped, hoisted weirdly  
let = modern, block-scoped, safer  

## Hoisting

What is Hoisting?  
Hoisting means:  
JavaScript moves variable and function declarations to the top of their scope before  
running the code  
Think of it like this:  
Before executing your code, JavaScript does a quick "setup phase" where it:  
Finds variables (var, let, const)  
Finds functions  
Reserves memory for them  
Example with var  
What JavaScript internally does:  
var x;  
// hoisted (moved up)  
So:  
Declaration is hoisted  
Value assignment stays where it is  
Example with let and const  
Internally:  
//yishoistedbutNoTinitialized  
This creates something called:  
Temporal Dead Zone (TDZ)  
The time between:  
variable being hoisted  
and actually declared in code  
During TDZ -→ you cannot use the variable  
Functions are hoisted differently  
sayHello(); //  
works  
function sayHello() (  
Entire function is hoisted, not just the name.  
Function expressions (important!)  
sayHi(); / /  
error  
var sayHi = function() {  
console.log("Hi");  
Internally:  
var sayHi; // hoisted  
Easy Summary  
Type  
Hoisted?  
Initialized?  
Can use before line?  
Yes  
undefined  
var  
Yes (but undefined)  
X No  
Yes  
let  
X Error (TDZ)  
X No  
Yes  
const  
X Error (TDZ)  
function  
Yes  
Yes  
Yes  
One-line takeaway  
Hoisting = JavaScript moves declarations up, but not assignments  
understanding.  
Is this conversation helpful so far?  
