# Multisource Stream

A stream that accepts an arbitrary number of sources, which can start from any offset.

## Examples
```
var multi = new Multisource()
var source1 = multi.from(0)
var source2 = multi.from(6)
source2.write("World !")
multi.read() // => null
source1.write("Hello ")
multi.read().toString() // => "Hello World !"
```
```
var multi = new Multisource()
multi.from(0).write("foo")
multi.from(3).write("bar")
multi.read().toString() // => "foobar"
```

# Class: Multisource extends stream.Readable

## multisource.from(offset, [options])

* `offset` {Number}
* `options` {Object} Directly passed to the Source constructor
* return {Source} A stream.Duplex which writes to the multisource stream from an offset
