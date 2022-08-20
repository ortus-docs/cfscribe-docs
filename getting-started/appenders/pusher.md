# Pusher

The Pusher appender connects cfScribe to the [Pusher ](https://pusher.com/)service. it requires a pusher account.&#x20;



**Configuration**

The Pusher appender requires 4 env properties in the .env file. These are

&#x20;PUSHER\_APPID

PUSHER\_CLUSTER

PUSHER\_APISECRET

PUSHER\_KEY

If these are not set, the appender will throw an error when it is created. To get started if you do not have an account yet, put dummy values in the .env file.&#x20;

**Sample Configuration**

```
appenders : {
   "pusher" : { "class" : "scribe.models.pusher", "properties" : {} }
},
"rules" : {
    "production" : ["pusher"]
}
```
