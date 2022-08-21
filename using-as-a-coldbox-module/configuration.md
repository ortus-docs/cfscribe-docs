# Configuration

**LogBox Appenders**

CFScribe can use LogBox modules as targets of its routing. These are configured the same way as you would for LogBox and require no special set up.&#x20;

**CFScribe Appenders**

There are several CFScribe Appenders which can be used which are not part of LogBox at this time. The easiest way to configure these is in the /config/Coldbox.cfc file in the ModuleSettings.

`moduleSettings:{`\
&#x20;   `"scribe": {`\
&#x20;       `"appenders":{`\
&#x20;       `"pusher": {`\
&#x20;           `"class" : "scribe.models.pusher",`\
&#x20;           `"properties": {`\
&#x20;                `"appid":"",`\
&#x20;                `"cluster":"",`\
&#x20;                `"apisecret":"",`\
&#x20;                `"key":""`\
&#x20;           `}`\
&#x20;       `},`\
&#x20;   `"cleanErrors": true,`\
&#x20;   `"mandatoryKeys":{`\
&#x20;       `"sentry":"message"`\
&#x20;   `},`\
&#x20;   `"rules" : {},`\
&#x20;   `"ruleDefinitions": [`\
&#x20;       `"env:environment"`\
&#x20;   `]`\
&#x20;   `}`\
`}`

``

``
