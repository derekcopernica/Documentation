# REST API: GET unsubscribes (Publisher)

Er worden statistieken bijgehouden over elke mailing die verstuurd wordt met 
Copernica om je meer inzicht te geven in de prestatie hiervan. Unsubscribes zijn 
een van de statistieken die voor een mailing worden bijgehouden. 
Je kan deze opvragen met een HTTP GET call naar de volgende URL:

`https://api.copernica.com/v2/publisher/unsubscribes?access_token=xxxx`

Hier moet `$id` vervangen worden door de ID van de mailing destination. Deze methode 
ondersteunt ook het gebruik van de [fields parameter](./rest-fields-parameter) 
voor het **timestamp** veld.

## Teruggegeven velden

Deze methode geeft een JSON object terug met unsubscribes. Voor elke unsubscribe 
is de volgende informatie beschikbaar:

* **ID**: De ID van de unsubscribe. 
* **timestamp**: De tijdstempel van de unsubscribe.
* **source**: De source van de unsubscribe: van een link of een email.
* **success**: Boolean die aangeeft of de unsubscribe succesvol was.
* **emailing**: De ID van de emailing.
* **destination**: De ID van de destination.
* **profile**: De ID van de profile.
* **subprofile**: De ID van de subprofile (als deze beschikbaar is).

## PHP voorbeeld

Dit script demonstreert hoe je de API methode kunt gebruiken:

```php
// vereiste scripts
require_once('copernica_rest_api.php');

// verander dit naar je access token 
$api = new CopernicaRestAPI("your-access-token", 2);

// voer het verzoek uit
print_r($api->get("publisher/unsubscribes/"));
```

Dit voorbeeld vereist de [REST API klasse](./rest-php).

## Meer informatie

* [Overzicht van alle REST API calls](./rest-api)
* [Opvragen van abuses voor Publisher](./rest-get-publisher-abuses)
* [Opvragen van clicks voor Publisher](./rest-get-publisher-clicks)
* [Opvragen van deliveries voor Publisher](./rest-get-publisher-deliveries)
* [Opvragen van errors voor Publisher](./rest-get-publisher-errors)
* [Opvragen van impressions voor Publisher](./rest-get-publisher-impressions)
