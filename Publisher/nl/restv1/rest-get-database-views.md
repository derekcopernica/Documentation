# REST API: GET database views

Waarschuwing: Je bekijkt nu het overzicht voor de oude versie van onze 
API. Wij raden aan om [versie 2](../restv2/rest-api.md) van de API te gebruiken.

Je kunt bekijken welke selecties beschikbaar zijn door een HTTP GET request te 
sturen naar de volgende URL:

`https://api.copernica.com/v1/database/$id/views?access_token=xxxx`

De **$id** moet je vervangen door de numerieke identifier of de naam van de 
database waar je de selecties van wilt opvragen.


## Beschikbare parameters

De volgende parameters kunnen aan de URL als variabelen worden toegevoegd:

* start: 		eerste database die wordt opgevraagd;
* limit: 		lengte van de batch die wordt opgevraagd;
* total: 		toon wel/niet het totaal aantal databases in de output.

Meer informatie over de betekenis van deze parameters vind je in het
[artikel over paging](rest-paging).


## Geretourneerde velden

De methode retourneert een lijst van selecties. Voor elke selectie
worden de volgende eigenschappen teruggegeven:

* id: 				numeriek id van de selectie;
* name: 			naam van de selectie;
* description: 		omschrijving van de selectie;
* parent-type: 		mogelijke waardes: "database" of "view", gebruikt om aan te geven of 
dit een selectie direct onder een database is, of een geneste selectie onder een andere selectie;
* parent-id: 		id van de database of selectie waar deze selectie onder valt;
* has-children: 	boolean waarde; heeft deze selectie geneste selecties onder zich?
* has-referred: 	boolean waarde; zijn er andere selectie die verwijzen naar deze selectie?
* has-rules: 		boolean waarde; zijn er selectie-regels voor deze selectie ingesteld?
* database:			id van de database waar deze selectie onder valt
* lastbuilt:        tijdstip wanneer de selectie voor het laatst is opgebouwd

## Voorbeeld in PHP

Het volgende PHP script demonstreert hoe je de API methode kunt aanroepen:

```php
// vereiste scripts
require_once('copernica_rest_api.php');

// verander dit naar je access token
$api = new CopernicaRestApi("your-access-token");

// parameters voor de methode
$parameters = array(
    'limit'     =>  100
);

// voer de methode uit en print het resultaat
print_r($api->get("database/1234/views", $parameters));
```

Dit voorbeeld vereist de [REST API class](rest-php).


## Meer informatie

* [Overzicht van alle API calls](rest-api)
* [Selectie toevoegen aan database](rest-post-view)
* [Opvragen geneste selecties](rest-get-view-views)
* [Selectieregels opvragen](rest-get-view-rules)
