# ouput.js
#### ``` (()=>console.log("Guess Output!"))();```

 :arrow_right: ???
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
 
 :arrow_right: ???
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
 
 :arrow_right: ???
 ```
console.log(+new Date());

Output:- Get Timestamp for now(i.e. equivalent to "new Date().getTime()")
 ```
 :end:
 
 :arrow_right: ???
 ```
console.log(true + true);

Output:- 2

console.log(true + false);

Output:- 1
 ```
 :end:
 
 :arrow_right: ???
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
 
 :arrow_right: ???
 ```
 var arr = [1, 2, 10, 55, 9];
 arr.length = 3;
 console.log(arr);
 Output:- [1, 2, 10] because its truncate the last 2 values of the array. i.e. it is similar to arr.splice(3); 
 ```
 :end:
