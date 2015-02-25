# each [![Circle CI][circleci-badge]][circleci-link]

Iterate over a collection, invoking a function for each element.

## Installation

Browser:

```
component install ndhoule/each
```

Node:

```sh
$ npm install each
```

## API

### each(iterator : Function, collection : Array|Object|string) => undefined

Iterate over an input collection, invoking an `iterator` function for each element in the collection, passing to the iterator three arguments: `(value, index, collection)`.

The `iterator` function can end iteration early by returning `false`.

```javascript
var log = console.log.bind(console);

each(log, ['a', 'b', 'c']);
//-> 'a', 0, ['a', 'b', 'c']
//-> 'b', 1, ['a', 'b', 'c']
//-> 'c', 2, ['a', 'b', 'c']
//=> undefined

each(log, 'tim');
//-> 't', 2, 'tim'
//-> 'i', 1, 'tim'
//-> 'm', 0, 'tim'
//=> undefined

// Note: Iteration order not guaranteed across environments
each(log, { name: 'tim', occupation: 'enchanter' });
//-> 'tim', 'name', { name: 'tim', occupation: 'enchanter' }
//-> 'enchanter', 'occupation', { name: 'tim', occupation: 'enchanter' }
//=> undefined
```

## License

Released under the [MIT license](LICENSE.md).

[circleci-link]: https://circleci.com/gh/ndhoule/values
[circleci-badge]: https://circleci.com/gh/ndhoule/values.svg?style=svg&circle-token=4d65820fbf012e2c1c6649d9ba9319cdbfc0e549
