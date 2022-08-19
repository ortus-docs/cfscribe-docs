---
description: >-
  CFScribe is a logger very similar to Logbox but with the key difference of
  more complex routing and integrated Error Filtering.
---

# Features at a Glance

* **Variety of deployment options**
  * It can be used either a standalone product,&#x20;
  * It can be used within Coldbox as a module&#x20;
  * It can be used as a part of Logbox directly. This is helpful when implementing cfScribe into an existing code base which already uses LogBox
* **Multiple Appenders**
* **Complex Routing** - cfScribe allows an almost infinite level of routing based on a wide variety of criteria including environment, environment variables, severity (fatal, error, warn, info, debug), Coldbox Settings, Module Settings, presence or value of HTTP headers, UDF.&#x20;
* Error Filtering - This controls what information from the error is displayed when the error is output. This includes the keys from the error struct, the keys in the Tag Context section of the error, the number of lines in the TagContext and more.&#x20;

