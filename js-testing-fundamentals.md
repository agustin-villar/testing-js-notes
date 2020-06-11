# JS Testing Fundamentals

> What I really like about this course is that it teaches you how the actual testing framework "works" that really makes things more clear of why are you writing what you write when doing tests.

- Creating a custom testing library. During this lesson, I observed the functional programming pattern, the main function returns other functions in order to extend the scope and purpose of the function:

    ```
    function (actual) {
        return {
            toBe(expected) {
                if (actual !== expected) {
                    throw new Error(`${actual} is not equal to ${expected}`);
                }
            }
        }
    }
    ```

    To be used as:

    ```
    const result = sum(4, 2);
    const expected = 6;

    expect(result).toBe(expected);
    ```

- A testing framework's job is to help developers to identify bugs and where they exactly happen as quickly and meaningful as possible.

- Notice how encapsulation is used on the creation of the test framework on `lessons/testing-framework.js`.

    Encapsulation is used in other programming languages with access modifiers as in Java, with protected, public, private keywords, this helps to ensure data integrity, however in JavaScript it doesn't work in the same way, [here is an example of it's purpose and how can it be achieved in JavaScript](https://www.intertech.com/Blog/encapsulation-in-javascript/)

    In the framework's example it helps to keep the integrity of each one of the test cases, and also to keep the code [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself).

- What about the `async-await.js` in JavaScript there's the concept of `Promises`, promises are that exactly something that is supposed to happen after a function is executed, but that as in real life, might as well not happen, this goes by the hand with the concept of asynchronicity, is something that might not happen right away, but that's is developing itself in the background and will be resolved eventually, so, you have to be patient and wait for it, more about [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) and [asynchronous JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function).

- The global spotted on `setup-globals.js` is an object that always exists on the global scope, it's different depending on the context it is executed for example `Node` or a web browser. More about [this](https://developer.mozilla.org/en-US/docs/Glossary/Global_object) Since tests in here are executed using node the global object to target will be `global`.

- This how a custom test framework can be created in JavaScript, but the cours will use [Jest](https://jestjs.io/) as the testing library of choice.
