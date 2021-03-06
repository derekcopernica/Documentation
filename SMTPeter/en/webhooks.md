# Webhooks

SMTPeter allows you to set up Webhooks, previously named Feedback Loops. 
These Webhooks can be 
used to receive realtime event notifications. Every time when something happens
on the SMTPeter servers (like an incoming bounce, a failed  delivery or 
when someone clicks on a link), SMTPeter makes a call to your server to 
notify you about this event.

The webhook is sent over the HTTP or HTTPS protocol using the HTTP POST
mechanism. When you [set up a webhook](webhook-setup), you register 
a web address and specify the type of events that you are interested in. 
Once your URL has been validated, SMTPeter starts making calls to it.

## Watch out!

Before you set up a webhook, please do make sure that your server
is capable of handling the load. Especially the webhook that is
called when someone [opens a mail](webhook-opens) receives huge
numbers of calls.

If you're not sure whether your server can handle the load, or when you do
not need realtime feedback, you better use the [REST API](rest-api) to 
periodically download [the latest log files](rest-logfiles). The REST API 
gives you access to exactly the same data as the webhooks, but you 
stay in control and you decide when to fetch the data.

## Security

To protect your endpoint from abuse and false information injection, SMTPeter 
[signs all requests](webhook-security) to your endpoint. 

## Type of events

The following webhooks can be used:

* [Webhooks for bounces](webhook-bounces)
* [Webhooks for failures](webhook-failures)
* [Webhooks for clicks](webhook-clicks)
* [Webhooks for opens](webhook-opens)
* [Webhooks for abuses](webhook-abuses)
