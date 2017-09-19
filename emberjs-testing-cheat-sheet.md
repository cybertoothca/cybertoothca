# EmberJS Testing Cheat Sheet

## Skipping Tests

```js
// ...
import { skip } from 'qunit';

// ...

// simply change `test` to `skip` after importing `skip` from qunit
skip('when some test needs to be skipped', function(assert) {

})
```

## Freezing Dates & Time

```js
// import the sinon module
import sinon from 'sinon';

// create a test class variable that will hold your frozen clock
let CLOCK = null;

module('...', {
  // after each test restore to the system clock
  afterEach: function() {
    if (CLOCK) {
      CLOCK.restore();
    }
  },
  beforeEach: function() {
    // you could make it so that all of your tests use a fixed date & time
    // CLOCK = sinon.useFakeTimers(new Date(2001, 8, 11).getTime());
  }
})

test('when testing a fixed date', function(assert) {
  // I prefer to define my frozen time in the test for readability
  CLOCK = sinon.useFakeTimers(new Date(2001, 8, 11).getTime());
  // ... write your time-sensitive test
  // the frozen clock will be restored to system time after each test
})

```
