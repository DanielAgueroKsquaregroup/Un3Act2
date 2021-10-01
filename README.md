# Un3Act2
JS course Unit 3 Activity 2 repository

##### 1. What is a closure?
We can say that a closure is a function which enclose other function(s) inside of its.

##### 2. Give me an example of closure.
When we specified a function what to do with two given numbers (which operation must be done).

![alt text](https://github.com/DanielAgueroKsquaregroup/Un3Act2/blob/main/img/closure_example.png "closure example")

##### 3. What is ()() in code? 
The ()() is how we access to enclosed functions without using global variables, the parenthesis is what execute the function, if a function enclosed inside another one have parameter we also can set the value of it parameter by the ()().

##### 4. Move the variable after the closure (the function inside the function) and explain what happens.
It still working because the variable is declared before any value is returned.

##### 5. Change var for let and explain why the logic is not affected
Because the inner function looks for the variable needed for a correct functionality and due to the variable is declared before this inner function returns any result, it works.

##### 6. Scope chain, an example of it, how many closures can we nest
The scope chain is what gives us the capability of access to variables that are not in the scope where we called it, as long as this variable comes from a scope created before the scope where we are calling this variable. We can nest as many closures as needed in the project.

EXAMPLE NOTE: In the next image we can see 3 nested closures.

![alt text](https://github.com/DanielAgueroKsquaregroup/Un3Act2/blob/main/img/closure_nested.png "closure nested example")

##### 7. Are there conflicts between the closure and the global scope?
We can access global variables into the closure scope, the problem comes when we try to access to closure scope variables in the global scope (there is no possibility).

##### 8. Advantages of closures.
..* We can stablish private functions for others functions and add more functionalities.
..* Denied access to sensitive data to other functions.
..* Creation of readable code.

##### 9. What is data hiding and encapsulation?
When we delimitate the scopes in which we can access to a data.

##### 10. Give me an example of privacy with closures.
When creating an app that save the user password, we can give access to this password only to a particular function through enclosure.

```javascript
var b = setPass(1);
b();

function setPass(e){
    const x = Math.random();
    
    return showPass;

    function showPass(){
        if(e === x) return console.log(`This is the password ${x}`);
        return console.log(`You still don't know the password `);
    }
}
```

##### 11. What happens if you create two counters with the same closure?
There will be 2 counters running at the same time. This mean that the function executes each time we call it.

##### 12.	How can we add more functions as a decrement counter? Give an example of it.
The next example use `setInterval()` as a plus.

```javascript
var x = counting();

x("back")();

function counting(){

    function timer(a){
        if(a === "back"){
            function backToTheFuture(){
                setInterval(() => {
                    console.log(--counter);
                }, 1000)
            }
            return backToTheFuture;
        }
        setInterval(() => {
            console.log(++counter);
        }, 1000);
    }
    let counter = 0;
    return timer;
}
```

##### 13. What are the disadvantages of closures?
If there is a scenario where we need access to closure scope variables in the global scope or somewhere else outside the closure scope. There will not be any possibilities for that.