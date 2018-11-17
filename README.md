## Mocha cheat sheet
use done() if you want to test callbacks
```
it('should call someFunction', function(done) {
   someFunction = () => {
      // some expect statements
      done();
   }
   someFunction();
})
```

## Sinon stub cheat sheet
cheat sheet for sinon

### Return a Promise with a resolve value
```
sinon.stub(someModule, 'someFunction').returns(Promise.resolve(true));
```

### To trigger the callback of a stub
```
sinon.stub(someModule, 'someFunction').callsArgWith(1, null, 'kkk')
let cb = function(err, response) {
   console.log(response)
}
someModule.someFunction('abc', cb)
// should output kkk
```


### To get the parameters of the stub when it was called
```
someFunctionStub.getCall(0).args[0] // first parameter of the first time function was called
```


### To get the no. of times the stub was called

```
someFunctionStub.callCount
```

### To stub default exports

```
e.g. abc.js
export default {
   someFunction
}
```

In tests,
```
const tasks = require('./abc.js');
sinon.stub(tasks.default, 'someFunction')
```
