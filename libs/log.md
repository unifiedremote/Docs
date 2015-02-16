
# Log
* [trace](#log_trace)
* [info](#log_stroke)
* [warn](#log_warn)
* [error](#log_error)



## log
The ``log`` library can be used for diagnostics logging.

	local log = libs.log;



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




