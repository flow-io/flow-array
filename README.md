flow-array
==========

Writable stream which transforms an array into a readable stream.


## Examples

``` javascript
var // Flow array stream generator:
	aStream = require( 'flow-array' );

var data = new Array( 1000 ),
	stream;

// Create some data...
for ( var i = 0; i < 1000; i++ ) {
	data[ i ] = Math.random();
}

// Create a new stream:
stream = aStream().stream();

// Add a listener:
stream.on( 'data', function( data ) {
	console.log( data );
});

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

