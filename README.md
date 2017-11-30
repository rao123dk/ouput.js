# ouput.js
:question: :question: :question:
#### ``` (()=>console.log("Guess Output!"))();```

 :arrow_right: 
 :question:
 ```
 const arr = [10, 12, 15, 21];
    for (var i = 0; i < arr.length; i++) {
        setTimeout(function() {
           console.log('Index: ' + i + ', element: ' + arr[i]);
        }, 3000);
    }

output:-
Index: 4, element: undefined(printed 4 times).
Reason:- 
The reason for this is because the setTimeout function creates a function (the closure) that has access to its outer scope, which is the loop that contains the index i. After 3 seconds go by, the function is executed and it prints out the value of i, which at the end of the loop is at 4 because it cycles through 0, 1, 2, 3, 4 and the loop finally stops at 4.arr[4] does not exist, which is why you get undefined.
 ```
 :end:
 
 :arrow_right: 
 :question:
 ```
const arr = [10, 12, 15, 21];
for (var i = 0; i < arr.length; i++) {
  // pass in the variable i so that each function 
  // has access to the correct index
  setTimeout(function(i_local) {
    return function() {
      console.log('The index of this number is: ' + i_local);
    }
  }(i), 3000);
}

output:-
The index of this number is: 0
The index of this number is: 1
The index of this number is: 2
The index of this number is: 3
 ```
 :end:
 
 :arrow_right: 
 :question:
 ```
console.log(+new Date());

Output:- Get Timestamp for now(i.e. equivalent to "new Date().getTime()")
 ```
 :end:
 
 :arrow_right: 
 :question:
 ```
console.log(true + true);

Output:- 2

console.log(true + false);

Output:- 1
 ```
 :end:
 
 :arrow_right: 
 :question:
 ```
function fun1() {
   return
   {
      name: 'foo'
   }
}
//
function fun2() {
   return {
      name: 'foo'
   }
}

output:- The first function return undefined and second method will return the object as expected. Parentheses play a major role so it should be handled with caution.
 ```
 :end:
 
 :arrow_right: 
 :question:
 ```
 var arr = [1, 2, 10, 55, 9];
 arr.length = 3;
 console.log(arr);
 Output:- [1, 2, 10] because its truncate the last 2 values of the array. i.e. it is similar to arr.splice(3); 
 ```
 :end:

 :arrow_right: 
 :question:
 ```
 console.log(0.1 + 0.2 == 0.3);
 
 Output:- false, because 0.1 + 0.2 = 0.30000000000000004.
Explanation:- 
This is where the problem starts. 0.1 is not really 0.1 but rather its binary equivalent, which is a near-ish (but not identical) value. In essence, as soon as you write the values, they are doomed to lose their precision. You might have just wanted two simple decimals, but what you get, as Chris Pine notes, is binary floating-point arithmetic. Sort of like wanting your text translated into Russian but getting Belorussian. Similar, but not the same.

More is going on here, but it’s beyond the scope of this article (not to mention the mathematical capabilities of this author).

Workarounds for this problem are a favorite on computer science and developer forums. Your choice, to a point, comes down to the sort of calculations you’re doing. The pros and cons of each are beyond the scope of this article, but the common choice is between the following:
var num1 = 0.1, num2 = 0.2, shouldEqual = 0.3;
console.log(num1 + num2 > shouldEqual - 0.001 && num1 + num2 < shouldEqual + 0.001); //true
 ```
 Source :- [smashingmagazine](https://www.smashingmagazine.com/2011/05/10-oddities-and-secrets-about-javascript/)
 :end:

 :arrow_right: 
 :question:
 ```
 alert(new Array() == false); // true
 Output:- true
 Explanation:- To understand what’s happening here, you need to understand the concepts of truthy and falsy. These are sort of true/false-lite, which will anger you somewhat if you majored in logic or philosophy.

I’ve read many explanations of what truthy and falsy are, and I feel the easiest one to understand is this: in JavaScript, every non-boolean value has a built-in boolean flag that is called on when the value is asked to behave like a boolean; like, for example, when you compare it to a boolean.

 ```
 Source :- [smashingmagazine](https://www.smashingmagazine.com/2011/05/10-oddities-and-secrets-about-javascript/#3-an-array-with-no-keys-false-about-truthy-and-falsy)
 :end:
 
 :arrow_right: 
 :question:
 ```
 console.log([1,2,3] === [1,2,3]);
 Output:- false
 Explanation:- The array [1,2,3] is not equal to [1,2,3] because it’s simply a reference type. That’s common for most languages.
 ```
 :end:
 
 
 :arrow_right: 
 :question:
 ```
 console.log(new Array(3) == ",,");
 Output:- true
 Explanation:- == operator convert into(i.e. new Array(3).toString() = ",,"). 
 so,
 console.log(new Array(3) === ",,");
 Output:- false
 
 ```
 :end:
 
 
 :arrow_right:
 :question:
 ```
 console.log( '' == '0');
 Output :- false
 
 console.log( 0 == '');
 Output :- true
 
 console.log( 0 == '0');
 Output :- true
 Explanation:- use === instead of ==
 ```
 :end:
 
 
 :arrow_right:
 :question:
 ```
 var info = {
  	"name" : "Dheeraj Kumar Rao",
    "twitter" : "@rao123dk"

			}
var lang = {
  	"first" : "C and C++",
  	__proto__ : info
  
}
console.log(lang.twitter);
 Output :- @rao123dk Becsuse, Inheritance by __proto__ . [Here](https://hackernoon.com/understand-nodejs-javascript-object-inheritance-proto-prototype-class-9bd951700b29)
 ```
 :end:
 
 
 
 :arrow_right:
 :question:
 ```
 What keys are considered equal?
 console.log(+0 == -0);
 Output :- true
 
 console.log(+0 === -0);
 Output :- true
 Explanation:- Because JavaScript’s numbers keep magnitude and sign separate, each nonnegative number has a negative, including 0. Please click below link for more.
 ```
 Source :- [Two Zeros](http://speakingjs.com/es5/ch11.html#two_zeros)
 Source :- [exploringjs, What keys are considered equal? ](http://exploringjs.com/es6/ch_maps-sets.html#_what-keys-are-considered-equal)
 
 :end:
 
:arrow_right:
 :question:
 ```
 What about 3rd arguments in setTimeout
 setTimeout(console.log, 1000, "I love JavaScript");
 Output:- I love JavaScript
 
 
 ```
 :end:
 
 :arrow_right:
 :question:
 ```
 
 
 ```
 :end:
