# Ember Addons Cheat Sheet

## [ember-cli-bootstrap3-forms](http://ember-data-bootstrap3-forms.cybertooth.io/)

### `twbs-errors-alert` ([docs](https://github.com/cybertoothca/ember-data-bootstrap3-forms#twbs-errors-alert))

{% highlight none%}
{% raw %}
    {{twbs-errors-alert class="alert-danger" model=model}}
{% endraw %}
{% endhighlight %}

### `twbs-form-group` ([docs](https://github.com/cybertoothca/ember-data-bootstrap3-forms#twbs-form-group))

{% raw %}
```
{{#twbs-form-group fieldErrors=model.errors.firstName}}
  ...
{{/twbs-form-group}}
```
{% endraw %}

## ember-cli-bootstrap3-grid

### `twbs-clearfix` ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-grid/blob/master/README.md#twbs-clearfix))

{% raw %}
    {{twbs-clearfix columnCount=3 index=index visible-sm=true visible-md=true visible-lg=true}}
{% endraw %}


{% raw %}
    {{twbs-clearfix columnCount=3 index=index visible-all=true}}
{% endraw %}

### `Viewport` Mixin ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-grid/blob/master/README.md#viewport))

    import Viewport from 'ember-cli-bootstrap3-grid/mixins/viewport';
    // ... then mix it into your component
    export default Ember.Component.extend(Viewport, { ... });
    
    // ... then in your component's hbs, use the helpers
    {{#if xs?}} Extra Small {{else}} SM/MD/LG {{/if}}
        
{% raw %}`{{twbs-errors-alert class="alert-danger" model=model}}`{% endraw %} ([docs]())

### [ember-cli-bootstrap3-carousel](http://ember-cli-bootstrap3-carousel.cybertooth.io)

### [ember-cli-bootstrap3-popover](http://ember-cli-bootstrap3-popover.cybertooth.io)

### [ember-cli-date-textbox](http://ember-cli-date-textbox.cybertooth.io)

### [ember-cli-bootstrap3-marked-down](http://ember-cli-bootstrap3-marked-down.cybertooth.io)

### [ember-cli-text-support-mixins](http://ember-cli-text-support-mixins.cybertooth.io)

### [ember-cli-textarea-autosize](http://ember-cli-textarea-autosize.cybertooth.io)

### [ember-data-bootstrap3-forms](http://ember-data-bootstrap3-forms.cybertooth.io)
