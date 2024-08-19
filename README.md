This ESLint error suggests that you're directly calling the hasOwnProperty method on an object, which can be problematic in certain situations.

Instead of using:

`object.hasOwnProperty(key)`

Use one of these safer alternatives:
1. Use `Object.prototype.hasOwnProperty.call():`
2. Use Object.hasOwn() (introduced in ES2022):
3. Use the in operator (but be aware this checks the prototype chain as well):

The first two methods are preferred as they're more explicit and safer. The Object.hasOwn() method is the most modern and recommended approach if you're working in an environment that supports ES2022.
Here's a brief explanation of why this error occurs:

An object might have overwritten the hasOwnProperty method.
The object might not inherit from Object.prototype.
The object might be null or undefined.

By using one of the suggested alternatives, you ensure that you're always using the correct hasOwnProperty check, regardless of the object's prototype chain or any potential overwrites.
