
# Timer
* [timeout](#timer_timeout)
* [interval](#timer_interval)
* [schedule](#timer_schedule)
* [cancel](#timer_cancel)
* [Examples](#Examples)
	* [Updating Controls](#Updating_Controls)



## timer
The timer library provides timeouts, intervals, and schedules.

	local tmr = libs.timer;



### timer.timeout( fn, time )
Calls the function ``fn`` after the specified ``time`` in milliseconds. 
Returns a timer ID which can be used to ``cancel`` the timeout before it gets called.

	tid = tmr.timeout(function ()
		print("3 seconds later");
	end, 3000);

The function can either be inlined or a named function, which ever is most convenient.

	function foobar()
		print("3 seconds later");
	end

	tmr.timeout(foobar, 3000);


### timer.interval( fn, time )
Calls the function ``fn`` every ``time`` milliseconds. 
Returns a timer ID which can be used to ``cancel`` the interval at a later point in time.

	tid = tmr.interval(function ()
		print("tick");
	end, 3000);


### timer.schedule( fn, time )
Calls the function ``fn`` at the specified [ISO 8601](http://en.wikipedia.org/wiki/ISO_8601) ``time``. 
Returns a timer ID which can be used to ``cancel`` the schedule before it gets called.

	tmr.schedule(function ()
		print("good morning!");
	end, "2014-05-06T08:00:00Z");


### timer.cancel( id )
All timer functions return a timer ID. This ID is used to cancel the timer events.

	tid = tmr.timeout(...);
	tmr.cancel(tid);

You should ensure that your timers are canceled appropriately. For example:


## Examples

### Updating Controls
Intervals are useful for updating controls at regular intervals.

	local tmr = libs.timer;
	local tid = -1;

	events.focus = function ()
		tid = tmr.interval(update, 1000);
	end

	events.blur = function ()
		tmr.cancel(tid);
	end

	function update ()
		print("updating...");
	end


