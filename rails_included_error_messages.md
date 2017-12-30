# Rails Errors Cheat Sheet

Rails ships with a couple of locale resource files that can be
used for most of your custom error messages needs.  Here's the
flattened english variations:

_From ActiveModel (see: [https://github.com/rails/rails/blob/master/activemodel/lib/active_model/locale/en.yml](https://github.com/rails/rails/blob/master/activemodel/lib/active_model/locale/en.yml))_

```yaml
errors.messages.model_invalid: "Validation failed: %{errors}"
errors.messages.inclusion: "is not included in the list"
errors.messages.exclusion: "is reserved"
errors.messages.invalid: "is invalid"
errors.messages.confirmation: "doesn't match %{attribute}"
errors.messages.accepted: "must be accepted"
errors.messages.empty: "can't be empty"
errors.messages.blank: "can't be blank"
errors.messages.present: "must be blank"
errors.messages.too_long.one: "is too long (maximum is 1 character)"
errors.messages.too_long.other: "is too long (maximum is %{count} characters)"
errors.messages.too_short.one: "is too short (minimum is 1 character)"
errors.messages.too_short.other: "is too short (minimum is %{count} characters)"
errors.messages.wrong_length.one: "is the wrong length (should be 1 character)"
errors.messages.wrong_length.other: "is the wrong length (should be %{count} characters)"
errors.messages.not_a_number: "is not a number"
errors.messages.not_an_integer: "must be an integer"
errors.messages.greater_than: "must be greater than %{count}"
errors.messages.greater_than_or_equal_to: "must be greater than or equal to %{count}"
errors.messages.equal_to: "must be equal to %{count}"
errors.messages.less_than: "must be less than %{count}"
errors.messages.less_than_or_equal_to: "must be less than or equal to %{count}"
errors.messages.other_than: "must be other than %{count}"
errors.messages.odd: "must be odd"
errors.messages.even: "must be even"
```

...and then use it in your Model's custom validations; for example:

```ruby
# Admittedly a stupid example of checking if the email was blank
def validate_email
  return unless email.blank?
  errors.add(:email, I18n.t('errors.messages.blank'))
end
```


There is also an ActiveRecord bundle of keys that you can use too:
[https://github.com/rails/rails/blob/master/activerecord/lib/active_record/locale/en.yml](https://github.com/rails/rails/blob/master/activerecord/lib/active_record/locale/en.yml)
