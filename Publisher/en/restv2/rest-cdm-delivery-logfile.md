# REST API: Delivery Record Information

Every mail sent via Marketing Suite that is delivered is logged in the 
cdm-delivery log files. You can download the content of these files 
in CSV, JSON, and XML format using the [REST logfiles API](./rest-get-logfiles),
or the dashboard. These log files contain the following data in the
respective order:

| Data         | Description                                                                    |
| ------------ | ------------------------------------------------------------------------------ |
| id           | The ID of the message that was delivered                                       |
| time         | The time of the delivery                                                       |
| attempts     | The number of attempts needed before delivery was successful (starting from 0) |
| email        | The email address of the delivery                                              |
| tags         | The tags of the mail (semicolon separated)                                     |
| senderdomain | The sender domain name who sent the original mail                              |
| profile      | The ID of the profile                                                          |
| subprofile   | The ID of the subprofile                                                       |
| template     | The ID of the used template                                                    |

## Other logfile names

* [Marketing Suite general log](./rest-cdm-attempts-logfile)
* [Marketing Suite abuse log](./rest-cdm-abuse-logfile)
* [Marketing Suite click log](./rest-cdm-click-logfile)
* [Marketing Suite error log](./rest-cdm-error-logfile)
* [Marketing Suite impressions log](./rest-cdm-impression-logfile)
* [Marketing Suite retry log](./rest-cdm-retry-logfile)
* [Marketing Suite unsubscribe log](./rest-cdm-impression-logfile)
* [Publisher general log](./rest-pom-attempts-logfile)
* [Publisher abuse log](./rest-pom-abuses-logfile)
* [Publisher clicks log](./rest-pom-clicks-logfile)
* [Publisher delivery log](./rest-pom-deliveries-logfile)
* [Publisher error log](./rest-pom-errors-logfile)
* [Publisher impressions log](./rest-pom-impressions-logfile)
* [Publisher retry log](./rest-pom-retries-logfile)
* [Publisher unsubscribe log](./rest-pom-unsubscribes-logfile)

## More information on logfiles

* [List of all API calls](rest-api)
* [GET logfiles names](rest-get-logfiles-names)
* [GET logfiles JSON](./rest-get-logfiles-json.md)
* [GET logfiles CSV](./rest-get-logfiles-csv.md)
* [GET logfiles XML](./rest-get-logfiles-xml.md)
