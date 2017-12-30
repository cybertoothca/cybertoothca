# `ember-cli-release` Cheat Sheet

Here is an example of how I use the `ember-cli-release` add-on.  

## Configuration

I turn on publish in my configuration because I want my add-ons pushed to
npmjs.org.

`config/release.js`

```javascript
/* eslint-env node */

module.exports = {
  publish: true
};
```

## Releasing

Assuming you start with a release version of `1.0.0`.  Executing the following
commands during your development and acceptance processes will save you from
executing multiple commands to do the exact same thing.

```bash
$ ember release --prerelease='rc' # 1.0.0 -> 1.0.1-rc.0
$ ember release --prerelease=true # 1.0.1-rc.0 -> 1.0.1-rc.1
$ ember release # 1.0.1-rc.1 -> 1.0.1
```

#### Short-Hand Form (same results as above)

```bash
$ ember release -e 'rc' # 1.0.0 -> 1.0.1-rc.0
$ ember release -e true # 1.0.1-rc.0 -> 1.0.1-rc.1
$ ember release # 1.0.1-rc.1 -> 1.0.1
```
