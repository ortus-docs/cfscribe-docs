# Configuration

Nearly every aspect of CFScribe can be configured so errors and messages appear as you need them.&#x20;

**Definitions**

appenders - struct - Each CFScribe appender (i.e. not one configured in logbox already) needs to be listed here with the class and any properties it needs to operate.

rules - struct - This defines the routes that your logging can take. Each level in the struct indicates another rule definition being evaluated. It is a essentially a decision tree being represented as a struct. See the section on Rules and Rule Definitions for more details.&#x20;

ruleDefinitions - array - this is the order that the routing decisions are made.&#x20;

cleanErrors - boolean - determines whether or not the error / logging is passed though the ErrorFilter process which can filter out what keys are displayed and put limits on the number of rows displayed for keys like the tagContext.&#x20;

mandatoryKeys - struct - Some appenders, Sentry for example, have mandatory fields which will cause errors if they are not present. It is also possible that your logging policies might mandate that fields be present further downstream. This structure uses the name of the appender as the key and the value as a list of fields which need to be present when submitted to the appender.&#x20;





**Sample Configuration**

```
{ 
    "appenders"  : {
        "screen"  : { "class" : "scribe.models.screenDump" },
        "console" : { "class" : "scribe.models.systemOut" },
        "pusher"  : { 
            "class" : "scribe.models.pusher",
            "properties" : {} 
         },
         "sentry"  : { "class" : "scribe.models.sentry" } 
     }, 
     "rules"      : {
         "production" : "",
         "development" : [ "screen" ],
         "testing" : [ "screen" ] 
     },
     "ruleDefinitions" : [ "env:environment" ],
     "cleanErrors"  : true,    
     "mandatoryKeys" : { "sentry" : "message" }
   }
```
