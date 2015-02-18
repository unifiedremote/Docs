
# Log
* [log](#log-1)
* [trace](#logtrace-message-)
* [info](#logstroke-message-)
* [warn](#logwarn-message-)
* [error](#logerror-message-)



## log
The ``log`` library can be used for diagnostics logging.

	local log = require("log");



### log.trace( message )
Logs a trace level message (typically used for debugging).

	log.trace("something happened");



### log.info( message )
Logs an information level message normal logging.

	log.trace("something really exciting happened! :D");



### log.warn( message )
Logs a warning level message (non-critical important problems).

	log.trace("something bad happened, but we can recover :)");



### log.error( message )
Logs an error level message (critical problems).

	log.trace("something really bad happened! >.<");




