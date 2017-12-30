# EmberJs Add-On Cheat Sheet

## Read This Blog

[Ember Addon Secrets](http://emberup.co/ember-addon-secrets/)

## Blueprints

The [Ember CLI API documentation for Blueprints](https://ember-cli.com/api/classes/Blueprint.html)
is here, but here are some usage examples for adding Ember
Add-Ons, NPM packages, and Bower packages:

### [addAddonsToProject](https://ember-cli.com/api/classes/Blueprint.html#method_addAddonsToProject)

When adding multiple Ember Addons use the `addAddonsToProject` function:

```javascript
// ...
afterInstall: function(/*options*/) {
  return this.addAddonsToProject({
    packages: [
      { name: 'ember-moment' },
      // ...
      { name: 'ember-route-action-helper' }
    ]
  });
}
// ...
```

### [addPackagesToProject](https://ember-cli.com/api/classes/Blueprint.html#method_addPackagesToProject)

When adding multiple NPM projects use the `addPackagesToProject` function, and
check out the [good example in the API docs](https://ember-cli.com/api/classes/Blueprint.html#method_addPackagesToProject).

### [addBowerPackagesToProject](https://ember-cli.com/api/classes/Blueprint.html#method_addBowerPackagesToProject)

Notice that using Bower is not ideal as the project is going to be phased out.

When adding multiple Bower packages use the `addBowerPackagesToProject`
function:

```javascript
// ...
afterInstall: function(/*options*/) {
  return this.addBowerPackagesToProject([
    { name: 'scrollreveal' },
    // ...
    { name: 'showdown' }
  ]);
}
// ...
```
