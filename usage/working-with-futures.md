# Working With Futures

You have probably noticed that all the asyncronous operations in the SDK return a Java [OperationFuture](http://www.couchbase.com/autodocs/spymemcached-2.8.1/net/spy/memcached/internal/OperationFuture.html) object. This allows control of your application to return immediately to your code without waiting for the remote calls to complete. The future object gives you a window into whats going on and you can elect to monitor the progress on your terms-- deciding how long you're willing to wait-- or ignore it entirely in order to complete the request as quickly as possible.

The most common method is `get()`. Calling this will instruct your code to wait until th eoperation is complete before continuing. Calling `future.get()` essentially makes an _ansynchronou call syncronous_.

```javascript
future = client.asyncGet( ID = 'brad' );
person = future.get();
```

`OperationFutures` are parameterized which means they can each return a different data type from their `get()`. Check the [API Docs](http://apidocs.ortussolutions.com/cfcouchbase/current/) to see what each asynchronous future returns.

> **Info** Operations are always subject to the timeouts configured for the client regardless of how you interact with the future.

Here are some other methods you can call on a future to handle the response on your terms:

* `cancel()` - Cancel this operation, if possible.
* `getStatus()` - Get the current status of this operation.
* `isDone()` - Whether or not the Operation is done and result can be retrieved with get\(\).
* `get(duration, units)` - Get the results of the given operation, but specify how long you're willing to wait.
* More information on Futures is available here in the Java Docs: [OperationFuture](http://www.couchbase.com/autodocs/spymemcached-2.8.1/net/spy/memcached/internal/OperationFuture.html)

