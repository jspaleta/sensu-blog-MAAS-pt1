# sensu-blog-MAAS-pt1
Sensu Monitoring As A Service: Pt 1

This repository is a companion for the similarly entitled blog post. Within you'll find the sensu configuration for a proxy-client based monitoring service

## test-client.json
Basic client config for running client. This client will run check requests on behalf of all proxy-clients.

## http-proxy-request-simple.json
Basic example of how to use proxy-requests check attribute with proxy-clients. 

*Required proxy-client attributes: url   
*Required proxy-client subscription: http-proxy-client   
*Required proxu-client subscription: roundrobin:proxy-request

## http-proxy-request-full.json
More expressive proxy check using multiple optional proxy-client attributes

*Required proxy-client attributes: url   
*Required proxy-client subscription: http-proxy-client   
*Required proxy-client subscription: roundrobin:proxy-request

*Suggested proxy-client attribute: handler

## http-proxy-slack.json
configuration needed for http-proxy-slack_handler.json from sensu-plugins-slack

## http-proxy-slack_handler.json
basic slack handler configuration using http-proxy-slack_handler.json from http-proxy-slack_handler.json
