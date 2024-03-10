# Middlewares in Express JS

## Example from Chat GPT

Imagine you have a restaurant with a kitchen and a dining area. Customers come in and place their orders, and then the orders are prepared in the kitchen and served in the dining area. In this analogy:

1. **Express**: Express is like your restaurant, handling incoming requests and sending out responses.
2. **Middleware**: Middleware is like a waiter or a kitchen staff member who handles something specific before the order reaches the kitchen or after it leaves the kitchen but before it reaches the customer.

In Express, middleware functions are functions that have access to the request object (`req`), the response object (`res`), and the `next` function. They can perform tasks like logging requests, parsing data, authenticating users, handling errors, etc.

When a request is received by Express, it goes through a series of middleware functions before reaching the final route handler that sends the response back to the client.

## More thoughts

There are middlewares available to download like body parser and morgan from npm but you can create you own like this:

```js
// Example middleware function
function bandNameGenerator(req, res, next) {
  console.log(req.bodyParser);
  bandName = req.body["street"] + req.body["pet"];
  next(); // Pass control to the next middleware
}
// Using the middleware globally for all requests
app.use(bandNameGenerator);
```
