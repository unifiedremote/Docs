
# Timer
* [timer](#timer)
	* [timeout](#timertimeout-fn-time-)
	* [interval](#timerinterval-fn-time-)
	* [schedule](#timerschedule-fn-time-)
	* [cancel](#timercancel-id-)



## timer
The timer library provides timeouts, intervals, and schedules.

````lua
local tmr = require("timer");
````



### timer.timeout( fn, time )
Calls the function ``fn`` after the specified ``time`` in milliseconds. 
Returns a timer ID which can be used to ``cancel`` the timeout before it gets called.

````lua
tid = tmr.timeout(function ()
	print("3 seconds later");
end, 3000);
````

The function can either be inlined or a named function, which ever is most convenient.

````lua
function foobar()
	print("3 seconds later");
end

tmr.timeout(foobar, 3000);
````



### timer.interval( fn, time )
Calls the function ``fn`` every ``time`` milliseconds. 
Returns a timer ID which can be used to ``cancel`` the interval at a later point in time.

````lua
tid = tmr.interval(function ()
	print("tick");
end, 1000);
````



### timer.schedule( fn, time )
Calls the function ``fn`` at the specified [ISO 8601](http://en.wikipedia.org/wiki/ISO_8601) ``time``. 
Returns a timer ID which can be used to ``cancel`` the schedule before it gets called.

````lua
tmr.schedule(function ()
	print("good morning!");
end, "2014-05-06T08:00:00Z");
````



### timer.cancel( id )
All timer functions return a timer ID. This ID is used to cancel the timer events.

````lua
tid = tmr.timeout(...);
tmr.cancel(tid);
````

You should ensure that your timers are started and then canceled appropriately. For example:

````lua
local tid;

events.focus = function ()
	tid = timer.interval(function ()
		print("hello world!");
	end, 1000);
end

events.blur = function ()
	timer.cancel(tid);
end
````


