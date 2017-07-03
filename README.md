# Ember Addons Cheat Sheet

## [ember-cli-bootstrap3-forms](http://ember-data-bootstrap3-forms.cybertooth.io/)

### `twbs-errors-alert` ([docs](https://github.com/cybertoothca/ember-data-bootstrap3-forms#twbs-errors-alert))

{% highlight none%}
{% raw %}
{{twbs-errors-alert class="alert-danger" model=model}}
{% endraw %}
{% endhighlight %}

### `twbs-form-group` ([docs](https://github.com/cybertoothca/ember-data-bootstrap3-forms#twbs-form-group))

{% highlight none%}
{% raw %}
{{#twbs-form-group fieldErrors=model.errors.firstName}}
  <label for="...">...</label>
  {{input class="form-control" type="..." value=model.firstName}}
  <p class="help-block">...</p>
{{/twbs-form-group}}
{% endraw %}
{% endhighlight %}

## [ember-cli-bootstrap3-grid](https://github.com/cybertoothca/ember-cli-bootstrap3-grid)

### `twbs-clearfix` ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-grid/blob/master/README.md#twbs-clearfix))

{% highlight none%}
{% raw %}
{{twbs-clearfix columnCount=3 index=index visible-sm=true visible-md=true visible-lg=true}}
{% endraw %}
{% endhighlight %}

{% highlight none%}
{% raw %}
{{twbs-clearfix columnCount=3 index=index visible-all=true}}
{% endraw %}
{% endhighlight %}

### `Viewport` Mixin ([docs](https://github.com/cybertoothca/ember-cli-bootstrap3-grid/blob/master/README.md#viewport))

{% highlight none%}
{% raw %}
import Viewport from 'ember-cli-bootstrap3-grid/mixins/viewport';
// ... then mix it into your component
export default Ember.Component.extend(Viewport, { ... });

// ... then in your component's hbs, use the helpers
{{#if xs?}} Extra Small {{else}} SM/MD/LG {{/if}}
{% endraw %}
{% endhighlight %}

### [ember-cli-bootstrap3-carousel](http://ember-cli-bootstrap3-carousel.cybertooth.io)

### [ember-cli-bootstrap3-popover](http://ember-cli-bootstrap3-popover.cybertooth.io)

### [ember-cli-date-textbox](http://ember-cli-date-textbox.cybertooth.io)

### [ember-cli-bootstrap3-marked-down](http://ember-cli-bootstrap3-marked-down.cybertooth.io)

### [ember-cli-text-support-mixins](http://ember-cli-text-support-mixins.cybertooth.io)

### [ember-cli-textarea-autosize](http://ember-cli-textarea-autosize.cybertooth.io)

### [ember-data-bootstrap3-forms](http://ember-data-bootstrap3-forms.cybertooth.io)
