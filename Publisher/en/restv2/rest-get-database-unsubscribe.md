# REST API: GET database unsubscribe

Every database has the option to set unsubscribe behaviour. When 
Copernica’s servers receive an unsubscription, the unsubscribe behaviour 
determines what happens with the profile: should it be edited or removed?

You can request your settings using the following URL:

`https://api.copernica.com/v2/database/$id/unsubscribe?access_token=xxxx`

The `$id` should be replaced by the numerical identifier or the name of 
the database.

## Returned fields

- **behavior**: the setting itself
- **fields**: the new profile setting (only applicable if "behavior" 
is set to "update")

The field "behavior" has three possible values: "nothing", "remove" and 
"update". "nothing"  means unsubscriptions are simply ignored 
(which is very impolite), "remove" deletes unsubscribers from the 
databases completely and "update" alters the field for this profile so 
its data can be kept, but there is an indicator that no email should be 
sent to this profile.

## PHP example

The following example demonstrates how to use the API method:

```php
// dependencies
require_once('copernica_rest_api.php');

// change this into your access token
$api = new CopernicaRestAPI("your-access-token", 2);

// do the call, and print result
print_r($api->get("database/{$databaseID}/unsubscribe"));
```

The example above requires the [CopernicaRestApi class](rest-php).

## More information

- [Overview of all API calls](rest-api)
- [PUT database unsubscribe](rest-put-database-unsubscribe)
