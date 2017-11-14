# cybertooth.io EmberJs Add-Ons
----

## [ember-cli-bootstrap3-carousel](http://ember-cli-bootstrap3-carousel.cybertooth.io)

### `twbs-carousel` Component ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-carousel#components))

```hbs {% raw %}
{{#twbs-carousel as |carousel|}}
  {{#carousel.slide classNames="active" as |slide|}}
    {{slide.img src="https://dummyimage.com/1600x900/f7d3a0/333.jpg&text=Slide+1" alt="A slide image."}}
  {{/carousel.slide}}
  {{#carousel.slide as |slide|}}
    {{slide.img lazy="https://dummyimage.com/1600x900/f7d3a0/333.jpg&text=Slide+2" alt="A slide image."}}
  {{/carousel.slide}}
  ...
  {{#carousel.slide as |slide|}}
    {{slide.img lazy="https://dummyimage.com/1600x900/f7d3a0/333.jpg&text=Slide+5" alt="A slide image."}}
  {{/carousel.slide}}
{{/twbs-carousel}}
{% endraw %} ```

## [ember-cli-bootstrap3-grid](https://github.com/cybertoothca/ember-cli-bootstrap3-grid)

### `twbs-clearfix` Component ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-grid/blob/master/README.md#twbs-clearfix))

```hbs {% raw %}
{{twbs-clearfix columnCount=3 index=index visible-sm=true visible-md=true visible-lg=true}}
{% endraw %} ```

```hbs {% raw %}
{{twbs-clearfix columnCount=3 index=index visible-all=true}}
{% endraw %} ```

### `Viewport` Mixin ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-grid/blob/master/README.md#viewport))

```js
import Viewport from 'ember-cli-bootstrap3-grid/mixins/viewport';
// ... then mix it into your component
export default Ember.Component.extend(Viewport, { ... });
```

```hbs {% raw %}
{{!-- then in your template use the computed functions --}}
{{#if xs?}} Extra Small {{else}} SM/MD/LG {{/if}}
{% endraw %} ```

## [ember-cli-bootstrap3-popover](http://ember-cli-bootstrap3-popover.cybertooth.io) ![GitHub version](http://badge.fury.io/gh/cybertoothca%2Fember-cli-bootstrap3-popover.svg)

### `twbs-popover` Component ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-popover#twbs-popover))

```hbs {% raw %}
{{#twbs-popover content="Click again to hide." as |popover|}}
  {{#popover.trigger}}
    <a href="javascript:void(0)">Click this anchor.</a>
  {{/popover.trigger}}
{{/twbs-popover}}
{% endraw %} ```

## [ember-cli-bootstrap3-tooltip](http://ember-cli-bootstrap3-tooltip.cybertooth.io) ![GitHub version](http://badge.fury.io/gh/cybertoothca%2Fember-cli-bootstrap3-tooltip.svg)

### `twbs-abbr` Component ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-tooltip#twbs-abbr-titlesome-tooltip-value))

```hbs {% raw %}
{{#twbs-abbr title="Best Friends, Forever"}}BFF{{/twbs-abbr}}
{% endraw %} ```

### `twbs-button` Component ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-tooltip#twbs-button-classbtn-default-titlesome-tooltip-value))

```hbs {% raw %}
{{#twbs-button class="btn-default" title="Some Tooltip"}}Some Button{{/twbs-button}}
{% endraw %} ```

### `twbs-cite` Component ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-tooltip#twbs-cite-titlesome-tooltip-value))

```hbs {% raw %}
<blockquote>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer>Someone famous in {{#twbs-cite title="Source Title"}}Source Title{{/twbs-cite}}</footer>
</blockquote>
{% endraw %} ```

### `twbs-i` Component ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-tooltip#twbs-i-titlesome-tooltip-value))

```hbs {% raw %}
{{twbs-i class="fa fa-github"
  html?=true placement="right"
  title="Github Icon:<br/><code>fa fa-github</code>"}}
{% endraw %} ```

### `twbs-span` Component ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-tooltip#twbs-span-titlesome-tooltip-value))

```hbs {% raw %}
{{#twbs-span title="Some sort of tooltip in a span"}}Hover Over This{{/twbs-span}}
{% endraw %} ```

### `twbs-time` Component ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-tooltip#twbs-time-datetime2001-09-11t040000000z-titlesome-tooltip-value))

```hbs {% raw %}
{{#twbs-time
  datetime="2001-09-11T04:00:00.000Z" title="Some sort of time..."
}}
  Hover Over This
{{/twbs-time}}
{% endraw %} ```

## [ember-cli-date-textbox](http://ember-cli-date-textbox.cybertooth.io) ![GitHub version](http://badge.fury.io/gh/cybertoothca%2Fember-cli-date-textbox.svg)

### `input-date` Component ([docs](https://github.com/cybertoothca/ember-cli-date-textbox#input-date))

```hbs {% raw %}
{{input-date autofocus=true classNames="form-control" date=model.createdAt displayFormat="LLLL"}}
{% endraw %} ```

### `input-iso8601` Component ([docs](https://github.com/cybertoothca/ember-cli-date-textbox#input-iso8601))

```hbs {% raw %}
{{input-iso8601 classNames="form-control" displayFormat="llll" iso8601="2017-07-01T00:00:00.000Z"}}
{% endraw %} ```

## [ember-cli-marked-down](https://github.com/cybertoothca/ember-cli-marked-down) ![GitHub version](http://badge.fury.io/gh/cybertoothca%2Fember-cli-marked-down.svg)

### `marked-down` Helper ([docs](https://github.com/cybertoothca/ember-cli-marked-down#marked-down-some-__markdown__-text))

```hbs {% raw %}
{{marked-down "Some ~~struck~~ markdown text" strikethrough=true}}
{% endraw %} ```

### `set-links-target` Component ([docs](https://github.com/cybertoothca/ember-cli-marked-down#set-links-target))

```hbs {% raw %}
{{#set-links-target excludeSelfLinks?=true targetValue="_blank"}}
  ...
{{/set-links-target}}
{% endraw %} ```

## [ember-cli-text-support-mixins](http://ember-cli-text-support-mixins.cybertooth.io) ![GitHub version](http://badge.fury.io/gh/cybertoothca%2Fember-cli-text-field-mixins.svg)

### `input-text` Component ([docs](https://github.com/cybertoothca/ember-cli-text-support-mixins#input-text))

```hbs {% raw %}
{{input-text autofocus=true class="form-control" escapeKeyClears?=true focusSelectsText?=true value=model.firstName}}
{% endraw %} ```

### `text-area` Component ([docs](https://github.com/cybertoothca/ember-cli-text-support-mixins#text-area))

```hbs {% raw %}
{{text-area class="form-control" escapeKeyClears?=true focusSelectsText?=true ctrlEnterSubmitsForm?=true value=model.notes}}
{% endraw %} ```

## [ember-cli-textarea-autosize](http://ember-cli-textarea-autosize.cybertooth.io) ![GitHub version](http://badge.fury.io/gh/cybertoothca%2Fember-cli-textarea-autosize.svg)

### `textarea-autosize` Component ([docs](https://github.com/cybertoothca/ember-cli-textarea-autosize#usage))

```hbs {% raw %}
{{textarea-autosize classNames="form-control" rows=4}}
{% endraw %} ```

## [ember-data-bootstrap3-forms](http://ember-data-bootstrap3-forms.cybertooth.io/) ![GitHub version](http://badge.fury.io/gh/cybertoothca%2Fember-data-bootstrap3-forms.svg)

### `twbs-errors-alert` Component ([docs](https://github.com/cybertoothca/ember-data-bootstrap3-forms#twbs-errors-alert))

```hbs {% raw %}
{{twbs-errors-alert class="alert-danger" model=model}}
{% endraw %} ```

### `twbs-form` Component ([docs](https://github.com/cybertoothca/ember-data-bootstrap3-forms#twbs-form))

```hbs {% raw %}
{{#twbs-form
    submit=(route-action "saveModel" model)
    reset=(route-action "rollbackModel" model)
}}
  {{!-- your form-groups and inputs go here --}}
  <div class="form-group text-right">
    <button class="btn btn-primary" type="submit">
      Clicking This SUBMIT Button Triggers Form's Submit Action
    </button>
    <button class="btn btn-default" type="reset">
      Clicking This RESET Button Triggers Form's Reset Action
    </button>
  </div>
{{/twbs-form}}
{% endraw %} ```

### `twbs-form-group` Component ([docs](https://github.com/cybertoothca/ember-data-bootstrap3-forms#twbs-form-group))

```hbs {% raw %}
{{#twbs-form-group fieldErrors=model.errors.firstName}}
  <label for="...">...</label>
  {{input class="form-control" id="..." type="..." value=model.firstName}}
  <p class="help-block">...</p>
{{/twbs-form-group}}
{% endraw %} ```
