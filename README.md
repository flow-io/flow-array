flow-array
==========

Writable stream which transforms an array into a readable stream.


## Installation

``` bash
$ npm install flow-array
```


## Examples

``` javascript
var eventStream = require( 'event-stream' ),
	aStream = require( 'flow-array' );

// Create some data...
var data = new Array( 1000 );
for ( var i = 0; i < data.length; i++ ) {
	data[ i ] = Math.random();
}

// Create a new writable array stream:
var stream = aStream().stream();

// Create a pipeline:
stream.pipe( eventStream.map( function( d, clbk ) {
		clbk( null, d.toString() );
	}))
	.pipe( process.stdout );

// Write the data to the stream:
stream.write( data );
stream.end();
```

## Tests

Unit tests use the [Mocha](http://visionmedia.github.io/mocha) test framework with [Chai](http://chaijs.com) assertions.

Assuming you have installed Mocha, execute the following command in the top-level application directory to run the tests:

``` bash
$ mocha
```

All new feature development should have corresponding unit tests to validate correct functionality.


## License

[MIT license](http://opensource.org/licenses/MIT). 


---
## Copyright

Copyright &copy; 2014. Athan Reines.

