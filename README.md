Area Codes
========

Get the city and state of all (as far as we know) U.S. and Canada area codes and North American Toll-Free Numbers. Look them up one phone number at a time, or dump the entire DB object.

Area code data is relatively small, so this library stores the data internally, and loads it into memory. No web service calls or anything like that. It's fast baby.

Memory impact should be < 100KB.

Usage
========

Pull by phone number (include country code or not, but only 1, United States/Canada, is supported). Also, many phone number formats
are supported:

```txt
+1-###-###-####
1-###-###-####
###-###-####
+1 (###) ###-####
1 (###) ###-####
(###) ###-####
+1.###.###.####
1.###.###.####
###.###.####
+1##########
1##########
##########
etc.
```

Basically, if there are 10-11 digits (first digit being 1 if 11) in the format, it should parse fine.

```javascript
let AreaCodes = require( 'areacode-city-states' );

let areaCodes = new AreaCodes();

areaCodes.get( '+1-303-123-4567', function( err, data ) {
	console.error( 'city/state/GPS', data );
} );

/** output:
{
  "type": "local", 
  "city": "Aurora",
  "state": "Colorado",
  "stateCode": "CO",
  "country": "US",
}
*/

```

Get entire DB:

```
let AreaCodes = require( 'areacode-city-states' );

let areaCodes = new AreaCodes();

areaCodes.getAll( function( err, data ) {
	console.error( 'all area codes', data );
} );
```

Contribute
========

If you want to help contribute to the library, this is how development goes. In all cases, make sure that you only add
new test cases to the test suite in the test directory. The only time we should consider deleting/editing old test cases
is if we are doing a non-backward compatible change. 

Make sure your pull-requests go to the develop branch only. 

## Just editing lib/areacode-city-states.js

If you are just changing the code for how the in-memory database is loaded and accessed, you are only going to need to 
edit the lib/areacode-city-states.js file. And, you will only need to run `npm test` to verify your changes. 


License
========

(The MIT License)

Copyright (c) 2019 BlueRival Software <support@bluerival.com>

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the 'Software'), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
