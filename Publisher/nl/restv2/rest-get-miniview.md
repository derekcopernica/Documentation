# REST API: GET miniview

Een methode om alle metadata van een selectie binnen een collectie op 
te vragen. Deze methode ondersteunt geen parameters en wordt aangeroepen 
met een HTTP GET verzoek aan de volgende URL:

`https://api.copernica.com/v2/miniview/$id?access_token=xxxx`

De `$id` hier moet vervangen worden door de ID of de naam van de collectie 
waarvoor je de selecties op wil vragen.

## Ondersteunde parameters

Er zijn geen ondersteunde parameters voor deze methode.

## Teruggegeven velden

- **ID**: unieke numerieke identifier van de selectie
- **name**: naam van de selectie
- **description**: omschrijving van de selectie
- **parent-type**: bovenliggende structuur van de selectie; selectie of collectie
- **parent-id**: ID van de bovenliggende selectie/collectie
- **collection**: ID van de collectie waar deze miniselectie onder valt.

## Voorbeeld in PHP

Het volgende voorbeeld demonstreert hoe je deze methode kunt gebruiken:

```php
// vereiste scripts
require_once('copernica_rest_api.php');

// verander dit naar je access token
$api = new CopernicaRestAPI("your-access-token", 2);

// voer het verzoek uit en print het resultaat
print_r($api->get("view/{$viewID}"));
```

Dit voorbeeld vereist de [REST API klasse](rest-php).

## Meer informatie

- [Overzicht van alle API methodes](rest-api)
- [Opvragen selectie regels voor een collectie](./rest-get-miniview-rules)
