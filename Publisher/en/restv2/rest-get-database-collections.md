# REST API: GET database collections

This method is used to request all collections in a database. It is an 
HTTP GET call to the following address:

`https://api.copernica.com/v2/database/$id/collections?access_token=xxxx`

In this, `$id` should be replaced by the numerical identifier or the 
name of the database of which you want to request the collections.

## Available parameters

The following parameters can be added to the URL as variables:

- **start**: the first collection to be requested
- **limit**: length of the requested batch
- **total**: whether or not the total number of collections should be counted

More information on the meaning of these parameters can be found [in the article on paging](rest-paging).

## Returned fields

The method returns a list of collections in the database. For each collection, the following properties are displayed:

- **name**: the name of the collection in the database
- **database**: ID of database of the collection
- **fields**: fields in the collection

## PHP example

The following PHP script demonstrates how to use the API method:

```php
// dependencies
require_once('copernica_rest_api.php');

// change this into your access token
$api = new CopernicaRestAPI("your-access-token", 2);

// parameters to pass to the call
$parameters = array(
   'limit'     =>  100
);
	
// do the call, and print result
print_r($api->get("database/{$databaseID}/collections", $parameters));
```

The example above requires the [CopernicaRestApi class](rest-php).

## More information

- [Overview of all API methods](rest-api)
- [POST database collections](rest-post-database-collections)
- [GET collection fields](rest-get-collection-fields)
- [POST collection fields](rest-post-collection-fields)
