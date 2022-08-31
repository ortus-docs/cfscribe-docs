---
description: >-
  CFScribe is a logger very similar to Logbox but with the key difference of
  more complex routing and integrated Error Filtering.
---

# Features at a Glance

* **It can be used within Coldbox as a module**&#x20;
* **Multiple Appenders** - Multiple appenders can be assigned to a particular situation and run in a specific order.&#x20;
* **Complex Routing** - CfScribe allows an almost infinite level of routing based on a wide variety of criteria including environment, environment variables, severity (fatal, error, warn, info, debug), Coldbox Settings, Module Settings, presence or value of HTTP headers, UDF.&#x20;
* **Error Filtering** - This controls what information from the error is displayed when the error is output. This includes the keys from the error struct, the keys in the Tag Context section of the error, the number of lines in the TagContext and more.&#x20;
* **Interceptor** - Reads errors in the onException event from ColdBox and behaves routes error accordingly.&#x20;

