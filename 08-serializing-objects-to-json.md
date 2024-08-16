# Serializing objects to JSON

In the previous step, we learned how to parameterize our API tests to make it easier to run the same test for different combinations of input and expected output values. We saw how we can use features that are built into pretty much every test runner out there to define our data source and then 'feed' that data to our tests, enabling us to run the same test for different test data combinations without code duplication.

In this step, we'll explore another important and powerful feature that is supported by most API testing libraries: object serialization.

### Creating API request payloads in our tests

In many tests, we will have to not only retrieve data from a provider using GET requests, but we will also have to send data, for example using POST, PUT or PATCH operations. In a typical API, that data is sent in the request body, often in JSON or (sometimes) XML format. This means we'll need to create that request body as part of our test.

Now, there are a couple of different ways to do that.

Let's say you want to create a new user account, and to do so you'll need to POST a JSON request body that looks like this:

```json
{
    "customerId": 123,
    "type": "savings"
}
```

You _could_ create the JSON payload 'by hand' by creating a new, empty JSON object, then add the `customerId` and `type` child elements, and finally call a method like `toString()` to create your JSON request body.

Or even more straightforward, you could just create the JSON string yourself and store it as a constant for later use.

For a small JSON payload like this, that works just fine. However, if you need to do this often, and if the JSON request payloads you need to send contain more items, it becomes a tedious and error-prone process.

And if you hard-coded the JSON string, there's zero flexibility. If you want to create another account for a different customer, you'll need to create another JSON string. This approach doesn't scale very well.

There is a third way, though, and that's using _object serialization_, and it's supported by most API testing libraries.

### How does object serialization work?

With object serialization, you create an object yourself, initialize its properties with the values you need to send, and then let a dedicated serialization library take care of the hard and boring work of transforming that object into JSON (or XML).

So, instead of creating a JSON string like the one above, we can for example create a class `Account` with properties `customerId` and `type`, create an instance of that class in our test and then have the API testing library we use serialize that to JSON.

The object to create can take different shapes, depending on the programming language and library you use. Here are some examples:

| Language | API testing library | Serialization built-in | Supported object types |
| -------- | ------------------- | ---------------------- | ---------------------- |
| Java | REST Assured | No, but supported by adding popular serialization library to your project classpath | Strongly typed objects, `HashMap` |
| C# | RestAssured.Net | Yes | Strongly typed objects, `Dictionary`, anonymous objects |
| Python | requests | Yes | Dictionaries |

### Applying object serialization to our test

In [a previous step](06-working-with-an-api-testing-library.md), we created a POST request with a hard-coded JSON request body. Now that we have learned a little more about serialization, let's improve this test by creating an object that represents the payload and then let the API testing library take care of serializing that object to an actual JSON payload.

### What about deserialization?

Deserialization is same process, the other way around, and you typically apply it to response bodies. As in: you ask the API testing library to transform the JSON (or XML) response body into an object. Personally, I don't use this as often as I do use serialization, but there are definitely situations where deserialization is useful, for example when you want to do more complex verifications on your response bodies in an efficient way, so I encourage you to read up on and practice deserialization, too.

If you managed to complete the serialization task, you should have everything you need to do deserialization, too, as this is typically handled by the same libraries, in much the same way.

### Adding our new test to the pipeline

As in the previous step, this should now be very straightforward. All we need to do is to commit our changes to version control, and trigger a new build to see if our new test, including serializing a request body, works as expected.

### That's it!

You have now:

* Learned how to apply serialization to create API request bodies in a more efficient and flexible way
* Applied serialization to a test and made that test part of the CI pipeline

This concludes our work on API testing, for now. In the next step, we are going to learn another very important and popular type of test automation: full stack / end-to-end / DOM-to-database [testing of our applications through the Graphical User Interface](09-adding-a-first-ui-test.md).