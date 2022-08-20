# ScreenDump

The ScreenDump appender is similar to the ScreenAbort appender except that it does not abort the flow. Instead it runs a cfFlush().

Note: Depending on the client and and architecture of your app, this might not display as expected on the screen including being replaced by views downstream from the screenDump.&#x20;

**Usage**

```
rules : { 
    "production" : [ "scribeConsole", "screenDump" ]
}
```
