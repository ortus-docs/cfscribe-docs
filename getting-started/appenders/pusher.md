# Pusher

The Pusher appender connects cfScribe to the [Pusher ](https://pusher.com/)service. it requires a pusher account.&#x20;



**Configuration**

1. In the /modules/scribe/libs is the pusher-http-java-1.2.0.jar file. This needs to be copied to either the /lib folder in your ColdBox installation or to another folder and the key&#x20;

```
"app":{    "libdirs":"jars"}
```

&#x20;   added to the server.json file in your server root. For more information about the server.json file check the CommandBox documents. \


2\. The Pusher appender requires 4 env properties in the .env file. These are

&#x20;   PUSHER\_APPID

&#x20;   PUSHER\_CLUSTER

&#x20;   PUSHER\_APISECRET

&#x20;   PUSHER\_KEY

&#x20;   If these are not set, the appender will throw an error when it is created. To get started if you do     not have an account yet, put dummy values in the .env file.&#x20;

**Sample Configuration**

```
appenders : {
   "pusher" : { "class" : "scribe.models.pusher", "properties" : {} }
},
"rules" : {
    "production" : ["pusher"]
}
```
