
# Log
* [log](#log-1)
* [trace](#logtrace-message-)
* [info](#logstroke-message-)
* [warn](#logwarn-message-)
* [error](#logerror-message-)



## log
The ``log`` library can be used for diagnostics logging.

````lua
local log = require("log");
````



### log.trace( message )
Logs a trace level message (typically used for debugging).

````lua
log.trace("something happened");
````



### log.info( message )
Logs an information level message normal logging.

````lua
log.info("something really exciting happened! :D");
````



### log.warn( message )
Logs a warning level message (non-critical important problems).

````lua
log.warn("something bad happened, but we can recover :)");
````



### log.error( message )
Logs an error level message (critical problems).

````lua
log.error("something really bad happened! >.<");
````


