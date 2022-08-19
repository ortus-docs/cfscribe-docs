# ScreenAbort

The ScreenAbort appender is designed to use with remote access tools such as a [Postman](https://www.postman.com/). Its main purpose is to return dump() output to the client so the error message can be viewed as if the user was viewing the call from a browser.&#x20;



**Configuration**

The ScreenAbort appender is active by default and can be used with no properties.

**Note**: This WILL abort processing the page and immediately return the call. See tips below for recommendations  &#x20;

```
appenders : {
   "screenDump"  : { "class" : "scribe.models.screenDump" }
}
```

**Tips and Recommendations**

* Use in conjunction with an http header which is sent from your client. For example, create a header called "x\_DebugHeader and then in the [RuleDefinitions ](../rules-and-rule-definitions.md)include `["headerTrueFalse":"x-DebugHeader"]`. This will check for the presence of the http header and route any errors accordingly.&#x20;
* Only use for `Fatal` or `Error` level logging. Otherwise every info comment will abort your flow.&#x20;
* When used in a series of apenders, put this last on the list otherwise the other appenders will not run. See below for example

**Example Configuration**

```
"ruleDefinitions" : [
    "headerTrueFalse:X-Import-Debug",
    "severity:severity"
],
rules : { 
    "true" : {
      "fatal" : [ "console", "screenAbort" ],
      "error" : [ "console", "screenAbort" ],
      "warn"  : [ "console" ],
      "info"  : [ "console" ],
      "debug" : [ "console" ] 
    }
}
```
