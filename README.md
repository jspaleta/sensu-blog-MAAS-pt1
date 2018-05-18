# sensu-blog-MAAS-pt1
Sensu Monitoring As A Service: Pt 1

This repository is a companion for the similarly entitled blog post. 
Within you'll find the Sensu Core 1.4 configuration for a proxy-client based monitoring service

## Provided Example Config
### test-client.json
Basic client config for running client. This client will run check requests on behalf of all proxy clients that meet proxy_requests requirements inside the example checks.

### http-proxy-request-simple.json
Basic example of how to use proxy-requests check attribute with proxy-clients. 

* Required client subscription: roundrobin:proxy-request

* Required proxy client attributes: url   
* Required proxy client subscription: http-proxy-client   

### http-proxy-request-full.json
More expressive proxy check using multiple optional proxy-client attributes

* Required client subscription: roundrobin:proxy-request

* Required proxy client attributes: url   
* Required proxy client subscription: http-proxy-client   

* Suggested proxy-client attribute: handler

### http-proxy-slack.json
configuration needed for http-proxy-slack_handler.json from sensu-plugins-slack

You will need to provide the correct webhook_url at a minimum. 
Please see the Slack API usage documentation for how to create a new incoming webhook_url.

### http-proxy-slack_handler.json
basic slack handler configuration using http-proxy-slack_handler.json from http-proxy-slack_handler.json

## Proxy Client Management Exampple

### Example Proxy Client Creation
```json
curl -s -i -X POST -H \
'Content-Type: application/json' \
-d '{"name":"proxy_sensu.io", "address":"unknown", "subscriptions":["http-proxy-request"], "environment":"development", "handler":"http-proxy-slack", "url":"https://sensu.io"}' \
http://127.0.0.1:4567/clients
```

### Example Proxy Client Deletion
```
curl -s -i -X DELETE http://127.0.0.1:4567/clients/proxy_sensu.io
```
