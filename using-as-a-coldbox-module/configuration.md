# Configuration

**LogBox Appenders**

CFScribe can use LogBox modules as targets of its routing. These are configured the same way as you would for LogBox and require no special set up.&#x20;

**CFScribe Appenders**

There are several CFScribe Appenders which can be used which are not part of LogBox at this time. The easiest way to configure these is in the /confiog/Coldbox.cfc file in the ModuleSettings.

`moduleSettings:{`\
&#x20;   `"scribe": {`\
&#x20;       `"appenders":{`\
&#x20;       `}`\
&#x20;   `}`\
\
`}`
