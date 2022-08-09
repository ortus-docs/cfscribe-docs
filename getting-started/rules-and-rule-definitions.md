---
description: Creating HOW and WHERE cfScribe sends the log
---

# Rules and Rule Definitions

Rules and Rule Definitions work together to determine the routing of a log. Both are set as part of the cfScribe configuration and both need to be present to make the system work.&#x20;

_**Rules**_ are contained in a struct and describe where the routing should go.&#x20;

_**Rule Definitions** _ are contained in an array and tell cfScribe what the criteria are for logging and in what order to apply them.&#x20;

For example, if our Rule Definitions are as follows:&#x20;

```
// [ "env:environment"]
```

that would indicate that first cfScribe would evaluate the environmental variable "environment", which would be set in the .env file, and use that to extract nodes from the rules structure. If the environment is "production" and the corresponding Rules structure is:&#x20;

```
// { 
    "production" : [ "console", "sentry" ],
    "development" : [ "screen" ], 
    "testing" : [ "screen" ] 
}
```

cfScribe would send the log to the "console" and "sentry" appenders.

CFScribe will continue to evaluate the definitions and rules until it gets to the end of the rule definitions with a few key points:

* If it comes to an array in the rules structure, it will assume that the contents are appenders and send the log to those end points and then continue to evaluate the rule definitions.&#x20;
* If there is no node for a given rule definition, it will be ignored. This means that there is no need to create "empty" nodes in order to prevent an error. See the example below

Rule Definitions:

```
// [
  "headerTrueFalse: myHeader",
  "env:environment",
]
```

Rules:

```
// { 
    "true": ["screen" ],
    "false" : {
        "production" : [ "console" ],
        "development" : [ "screen" ],
        "testing" : ["screen"]
    }
  }
```

&#x20;In this scenario, cfScribe first checks for the existence of the header "myHeader" then then what the environment is. If the header is present, it will send the error to the screen no matter what. If the header is not present, it will then route according to the environment.
