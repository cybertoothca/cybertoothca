# Cybertooth Ember Addons Cheat Sheet

## [ember-cli-bootstrap3-forms](http://ember-data-bootstrap3-forms.cybertooth.io/)

### `twbs-errors-alert` ([docs](https://github.com/cybertoothca/ember-data-bootstrap3-forms#twbs-errors-alert))

```hbs
{% raw %}
{{twbs-errors-alert class="alert-danger" model=model}}
{% endraw %}
```

### `twbs-form-group` ([docs](https://github.com/cybertoothca/ember-data-bootstrap3-forms#twbs-form-group))

```hbs
{% raw %}
{{#twbs-form-group fieldErrors=model.errors.firstName}}
  <label for="...">...</label>
  {{input class="form-control" type="..." value=model.firstName}}
  <p class="help-block">...</p>
{{/twbs-form-group}}
{% endraw %}
```

## [ember-cli-bootstrap3-grid](https://github.com/cybertoothca/ember-cli-bootstrap3-grid)

### `twbs-clearfix` ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-grid/blob/master/README.md#twbs-clearfix))

```hbs
{% raw %}
{{twbs-clearfix columnCount=3 index=index visible-sm=true visible-md=true visible-lg=true}}
{% endraw %}
```

```hbs
{% raw %}
{{twbs-clearfix columnCount=3 index=index visible-all=true}}
{% endraw %}
```

### `Viewport` Mixin ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-grid/blob/master/README.md#viewport))

```js
import Viewport from 'ember-cli-bootstrap3-grid/mixins/viewport';
// ... then mix it into your component
export default Ember.Component.extend(Viewport, { ... });
```

```hbs
{% raw %}
{{!-- then in your template use the computed functions --}}
{{#if xs?}} Extra Small {{else}} SM/MD/LG {{/if}}
{% endraw %}
```

## [ember-cli-bootstrap3-carousel](http://ember-cli-bootstrap3-carousel.cybertooth.io)

## [ember-cli-bootstrap3-popover](http://ember-cli-bootstrap3-popover.cybertooth.io)

### `twbs-popover` ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-popover#twbs-popover))

```hbs
{% raw %}
{{#twbs-popover content="Click again to hide." as |popover|}}
  {{#popover.trigger}}
    <a href="javascript:void(0)">Click this anchor.</a>
  {{/popover.trigger}}
{{/twbs-popover}}
{% endraw %}
```

## [ember-cli-date-textbox](http://ember-cli-date-textbox.cybertooth.io)

### `input-date` ([docs](https://github.com/cybertoothca/ember-cli-date-textbox#input-date))

```hbs
{% raw %}
{{input-date autofocus=true classNames="form-control" date=model.createdAt displayFormat="LLLL"}}
{% endraw %}
```

### `input-iso8601` ([docs](https://github.com/cybertoothca/ember-cli-date-textbox#input-iso8601))

```hbs
{% raw %}
{{input-iso8601 classNames="form-control" displayFormat="llll" iso8601="2017-07-01T00:00:00.000Z"}}
{% endraw %}
```

## [ember-cli-bootstrap3-marked-down](http://ember-cli-bootstrap3-marked-down.cybertooth.io)

### `marked-down` ([docs](https://github.com/cybertoothca/ember-cli-marked-down#marked-down-some-__markdown__-text))

```hbs
{% raw %}
{{marked-down "Some ~~struck~~ markdown text" strikethrough=true}}
{% endraw %}
```

## [ember-cli-text-support-mixins](http://ember-cli-text-support-mixins.cybertooth.io)

## [ember-cli-textarea-autosize](http://ember-cli-textarea-autosize.cybertooth.io)

## [ember-data-bootstrap3-forms](http://ember-data-bootstrap3-forms.cybertooth.io)
