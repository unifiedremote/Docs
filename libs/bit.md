
# Bit
* [bit](#bit-1)
* [bnot](#bitbnot-x-)
* [band](#bitband-x-y-)
* [bor](#bitbor-x-y-)
* [bxor](#bitbxor-x-y-)
* [lshift](#bitlshift-x-n-)
* [rshift](#bitrshift-x-n-)
* [arshift](#bitarshift-x-n-)
* [rol](#bitrol-x-n-)
* [ror](#bitror-x-n-)
* [tohex](#bittohex-x-n-)
* [tobit](#bittobit-x-)
	


## bit
The ``bit`` library provides bitwise operations.

	local bit = require("bit");

Refer to the [official documentation from LuaJIT](http://bitop.luajit.org/api.html) for more details.



### bit.bnot( x )
Returns the bitwise **not** of ``x``.



### bit.band( x, y )
Returns the bitwise **and** of ``x`` and ``y``.



### bit.bor( x, y )
Returns the bitwise **or** of ``x`` and ``y``.



### bit.bxor( x, y )
Returns the bitwise **exclusive or** of ``x`` and ``y``.



### bit.lshift( x, n )
Returns the bitwise **logical left shift** of ``x`` of ``n`` steps.



### bit.rshift( x, n )
Returns the bitwise **logical right shift** of ``x`` of ``n`` steps.



### bit.arshift( x, n )
Returns the bitwise **arithmetic right shift** of ``x`` of ``n`` steps.



### bit.rol( x, n )
Returns the bitwise **left rotation** of ``x`` of ``n`` steps.



### bit.ror( x, n )
Returns the bitwise **right rotation** of ``x`` of ``n`` steps.



### bit.tohex( x [,n] )
Helper function to convert a number to a hex string.



### bit.tobit( x )
Helper function to normalize values


