# CircleCI-1.0 Configuration Example (Ember-2.13+)
----

I've not enjoyed my experiences with TravisCI; false positives and
inconsistent build failures have plagued me. I moved over to CircleCI
and haven't really looked back.  However, to get there I
had to configure my Ember Add-ons to build efficiently in that environment.
I've created this simple gist of my CircleCI configuration to share with
any other interested parties.

## Using

* Ember-2.13+
* CircleCI-1.0

_It is worth noting, when my add-on was Ember-2.12 or lower, it would fail to build
on release (2.14), beta (2.15), and canary._

Enjoy.

{% gist dc20da37914a927463fc9dbec6ef5c85 %}
