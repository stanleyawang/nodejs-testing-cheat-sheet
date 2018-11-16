# Sinon stub cheat sheet
cheat sheet for sinon

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
