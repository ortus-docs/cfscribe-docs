# Using LogBox Appenders

CFScribe can use any of the LogBox appenders to log.&#x20;

**Configuration**

You will need to configure the appenders you wish to use according to the [LogBox documents](https://logbox.ortusbooks.com/configuration/configuring-logbox). Examples include:



```
logbox : {
    appenders : {
        "coldboxTracer" : { class : "coldbox.system.logging.appenders.ConsoleAppender" },
        "cfAppender": {class: "CFAppender"},
        "consoleAppender": {class: "ConsoleAppender"},
        "dbAppender" : {class: "DBAppender",properties:{dsn:"",table:""}
    }
}
```

The names of LogBox Appenders can be found in the /coldbox/system/logging/appenders folder and correspond to the file names. Documentation can be found at [https://logbox.ortusbooks.com/usage/appender-properties](https://logbox.ortusbooks.com/usage/appender-properties)

**Usage**

You can reference the appenders the same way you would any others.&#x20;

```
rules : {
   "production"  : "",
   "development" : [ "dbAppender" ],
   "testing"     : [ "EmailAppender" ],
   "blarg"       : [ "FileAppender" ]
}
```

\
\


