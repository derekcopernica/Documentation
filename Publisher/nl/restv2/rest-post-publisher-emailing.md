# REST API: POST emailing (Publisher)

Je kunt ook een mailing voor de Publisher versturen met onze 
REST API als je al een template en database voorbereid hebt. Door een HTTP 
POST verzoek te sturen naar het volgende adres kun je een mailing versturen:

`https://api.copernica.com/v2/publisher/emailing?access_token=xxxx`

## Beschikbare parameters

Er zijn drie (verplichte) parameters beschikbaar:

* **target**: De ID van de target van de mailing.
* **targettype**: Het type van de target (database, collectie, selectie, miniselectie, profiel of subprofiel)
* **document**: De ID van de template om te gebruiken.

Zorg ervoor dat je document volledig is voor je de mailing verstuurd. 
De mailing kan namelijk niet verstuurd worden zonder een onderwerp of 
afstuurder. Zorg er ook voor dat je [sender domain](../sender-domains) 
correct geconfigureerd is.

## PHP voorbeeld

Het onderstaande script laat zien hoe je deze API methode kunt gebruiken. 
Vergeet niet de parameters te vervangen door je eigen target en template.

```php
<?php

// vereiste scripts
require_once('copernica_rest_api.php');

// verander dit naar je access token
$api = new CopernicaRestAPI("your-access-token", 2);

// parameters om mee te geven aan de call
$parameters = array(
    'target'                  => $targetID,
    'targettype'              => $targetType,
    'template'                => $templateID,
);

// voer het verzoek uit
print_r($api->post("publisher/emailing", $parameters));

// het ID van het aangemaakte verzoek wordt teruggegeven bij een succesvol verzoek
```

Het bovenstaande voorbeeld vereist onze [REST API klasse](rest-php).

## Meer informatie

* [Overzicht van alle REST API calls](./rest-api)
* [Opvragen van alle Publisher mailings](./rest-get-publisher-emailings)
* [Aanmaken van een Marketing Suite mailing](./rest-post-ms-emailing)
