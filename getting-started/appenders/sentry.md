# Sentry

The Sentry appender acts as a bridge between cfScribe and the [Sentry Module](https://www.forgebox.io/view/sentry).&#x20;



**Configuration**

Configure the [Sentry Module](https://www.forgebox.io/view/sentry) according to the ReadMe in the module.



**Usage**

```
rules : { 
    "production" : {
      "fatal" : [ "Sentry" ]
    }
}
```

Note: The CFScribe appender is called "Sentry" while the appender from the Sentry Module itself is called "sentryAppender". The interfaces are different so sending cfScribe logs directly to the sentryAppender will result in an error.

**Tips and Recommendations**

Make sure the Sentry appender is under a "severity" rule, probably Error or Fatal. Otherwise every debug, info, and warn message will be sent to Sentry and possibly cause network errors, rate limits, or at the very least a very cluttered interface.&#x20;
