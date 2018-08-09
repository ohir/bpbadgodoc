## Bitpeek copy

`import "noimport"`

### Overview

Use ohir/bitpeek

## This is repo set up to demonstrate bug in godoc.org (as of 09.08.20018)
Examples with utf8 characters in function name do not expand.

Every single input bit from 0 to 63 can print a label that show this bit state.
Arbitrary group of bits can be printed as decimal, octal or hex numbers and as
C32s, Ascii7b or UTF8 characters. Plus as an IPv4 address in dot-notation.
Package has no dependencies and is faster than fmt.Sprintf used for identical output.


Taste it:

``` go
var header uint64 = 0xAfdfDeadBeef4d0e

println(string(bitpeek.Snap(
  `'Type:'F 'EXT=.ACK= Id:0xFHH from IPv4.Address32@:D.16@\n`,header)))
	
// Output:
// Type:5 ext.ACK Id:0x7DF from 222.173.190.239:19726
	
//   Benchmark:   277 ns/op  64 B/op 1 allocs/op (Sprintf: 862 ns/op)
```

### Easy Format String

	    (excerpt)	
	? - bitlabel with digit 0 or 1
	> - bitlabel - only if bit is SET
	< - bitlabel - only if bit is UNSET
	= - bitlabel lowercased if bit is UNSET  
	D - Decimal number
	H - Hex digit: 0..F
	C - Character (utf8)
	I - IPv4 address


### Documentation

[Examples that won't expand](http://godoc.org/github.com/ohir/bpbadgodoc) is hosted at GoDoc project.


### Install

Do not install this one. Install bitpeek.

