#View Queries

The minimum information you need to execute a view query is the name of the **design document** and the **view** you wish you use.

```coldfusion
results = client.query( designDocumentName='beer', viewName='brewery_beers' );

for( var result in results ) {
	writeOutput( result.document.name );
	writeOutput( '<br>' );
}
```

Here are the arguments you can pass into the `query()` or `viewQuery()` methods.  For the latest and more in-depth information please visit our [API Docs](http://apidocs.ortussolutions.com/cfcouchbase/2.0.0).

| Argument | Type | Default | Description |
| -- | -- | -- | -- |
| designDocumentName | `string`   |       | The name of the design document in your Couchbase server |
| viewName           | `string`   |       | The name of the view to query from |
| options            | `any`      | {}    | The query options to use for this query. This can be a structure of name-value pairs or an actual Couchbase query options object usually using the `newViewQuery()` method. |
| deserialize        | `boolean`  | true  | If true, it will deserialize the documents if they are valid JSON, else they are ignored. |
| deserializeOptions | `struct`   |       | A struct of options to help control how the data is deserialized when populating an object. See ObjectPopulator.cfc for more info. |
| inflateTo          | `any`      |       | A path to a CFC or closure that produces an object to try to inflate the document results on NON-Reduced views only! |
| filter             | `function` |       | A closure or UDF that must return boolean to use to filter out results from the returning array of records, the closure receives a struct that has id, document, key, and value: function( row ). A true will add the row to the final results. |
| transform          | `function` |       | A closure or UDF to use to transform records from the returning array of records, the closure receives a struct that has id, document, key, and value: function( row ). Since the struct is by reference, you do not need to return anything. |
| returnType         | `any`      | array | The type of return for us to return to you. Available options: array, native, iterator  |
