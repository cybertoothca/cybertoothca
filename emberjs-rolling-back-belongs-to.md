# EmberJs Rolling Back Belongs To

<div class="alert alert-info">
  <p>
    I've been doing this with Ember-Data-2.13 that is interacting
    with a Rails JSONAPI-Resources backend.
  </p>
</div>

Ember Data's `rollbackAttributes()` on a model does a great job
of rolling back any attributes that were modified.

The `belongs-to` relationships however, these require some extra
love.  Here's what I've done; it's pretty simple:

1. Override the model's `rollbackAttributes()` to also call
a new function named `rollbackBelongsTo()`.
1. Also on your model, author a function named `preserveBelongsTo()`.  
This function manually caches the instances assigned to the `belongs-to`
relationship.
1. Finally on your model, author the `rollbackBelongsTo()` mentioned
first.

Here's a simple example of a very basic _user_ model:

```javascript
// app/models/user.js

export default DS.Model.extend({
  /* ---------------------------------------------------------- ROLLBACK HACK */

  /**
   * Call this function from your component/route immediately
   * prior to editing.
   */
  preserveBelongsTo() {
    this.set('preserved', Ember.Object.create({
      telCountryCode: this.get('telCountryCode.content')
    }));
  },
  /**
   * Override the basic rollbackAttribute(); in addition call the
   * `rollbackBelongsTo()` function.
   * @override
   */
  rollbackAttributes() {
    this._super(...arguments);
    this.rollbackBelongsTo();
  },
  /**
   * Rollback the `belongs-to` relationships.
   */
  rollbackBelongsTo() {
    if (Ember.isPresent(this.get('preserved'))) {
      this.set('telCountryCode', this.get('preserved.telCountryCode'));
    }
  },

  /* ------------------------------------------------------------- PROPERTIES */

  email: DS.attr('string'),
  familyName: DS.attr('string'),
  givenName: DS.attr('string'),
  telNational: DS.attr('string'),

  /* ---------------------------------------------------------- RELATIONSHIPS */

  telCountryCode: DS.belongsTo('phone-country-code')
})
```

## WhyTF Questions...
----

#### Why aren't you using Ember-Data's `Model` events (e.g. `rolledBack`)?

It would be great to bind to the Model's `rolledBack` event
in an effort to trigger the rolling back of the belongs-to
relationships.

In addition, using the Model's `didLoad` and `didUpdate` events to
cache the belongs-to relationship values would make life so easy.

Alas, there are too many bugs in Ember-Data for this to work
perfectly.  For example, I cannot even get the `rolledBack` event
to fire in regular circumstances.

#### Why not use the Model's `relationships` computed property to dynamically cache the belongs-to relationships?

I'm thinking doing just that.

#### Why don't you use the `ember-rollback-relationships` add-on?
