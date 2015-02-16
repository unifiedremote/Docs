
# GPIO
* [map](#gpio_map)
* [name](#gpio_name)
* [index](#gpio_index)
* [header](#gpio_header)
* [capture](#gpio_capture)
* [release](#gpio_release)
* [releaseall](#gpio_releaseall)
* [pin](#gpio_pin)
* [out](#gpio_out)
* [get](#gpio_get)
* [set](#gpio_set)
* [high](#gpio_high)
* [low](#gpio_low)



## GPIO
The GPIO library provides access to the General Purpose Input Output interface available in Linux. The pin mapping functionality is currently only available for Raspberry Pi. The "map" function sets up lookup tables for finding pins by name, index, or header. For Raspberry Pi, the index follows the same number as used by [WiringPi](https://projects.drogon.net/raspberry-pi/wiringpi/).

### gpio.map( name )
Sets the pin map that should be used. 

	--sets the map to the raspberry pi map
	gpio.map("ip");

### gpio.name( name )
Get a pin from the set map by the ``name``.

	pin = gpio.name("SDA");

### gpio.index( index )
Get a pin by the ``index`` of the pin.

	pin = gpio.index(5);

### gpio.header( header )
The ``header`` number of the pin.

	pin = gpio.header(5);

### gpio.capture( pin )
Capture pins when you like to control them give the method a ``pin`` to capture. No other application can use the pin. 

	pin = gpio.index(5);
	gpio.capture(pin);

### gpio.release( pin )
Release the ``pin`` back to the operatingsystem. 

	pin = gpio.index(5);
	gpio.release(pin);

### gpio.in( pin )
Set the direction of the ``pin`` to an input pin.

	pin = gpio.index(5);
	gpio.in(pin);

### gpio.out( pin )
Set the direction of the ``pin`` to an output pin.

	pin = gpio.index(5);
	gpio.out(pin);

### gpio.get( pin )
Check ``pin`` if it is high or low. Returns true if ``pin`` is high. 

	pin = gpio.index(5);
	res = gpio.get(pin);

### gpio.set( pin, value )
Set the ``pin`` to high or low. Set ``value`` to true if pin should be high. 

	pin = gpio.index(5);
	--pin set to high
	gpio.set(pin, true);
	--pin set to low
	gpio.set(pin, false);

### gpio.high( pin )
Set the ``pin`` to high.

	pin = gpio.index(5);
	--pin set to high
	gpio.high(pin);

### gpio.low( pin )
Set the ``pin`` to low.

	pin = gpio.index(5);
	--pin set to low
	gpio.low(pin);