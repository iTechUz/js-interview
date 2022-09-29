### 1. What is JSON? And how would you convert JSON strings into objects, or convert an object into a JSON string?
- [x] Answer: 
JSON, or JavaScript Object Notation, is used to send and convert plain text into JavaScript objects, and they are written in exactly the same way. JSON is often used to display data on a web page after being read from a web server.

It’s used to send data between computers, but can also be used by any programming language — it isn’t limited to JavaScript. The text-only format makes it easy to send between computers.

To convert a JSON string into a JavaScript object, use this function:
```js
JSON.parse()
```
To convert an object into a JSON string, use this function:
```js
JSON.stringify()
```