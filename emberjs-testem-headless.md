# EmberJs Test In Headless (Chrome/Firefox)

Headless Chrome and Firefox now are available on most sane platforms.  
You can take advantage of headless testing in your Ember-2x application
in an effort to get rid of PhantomJs.

I'm expect this technique works for Ember-1.13.x
too, but I'm not going to boast that without someone testing it; and I am
certainly not going back there to do that.

Check out the gist below.  Basically this testem.js configuration
always runs in _headless_ mode unless we specify the `-s` flag
to our `ember t ...` command.

This has been working for me in my Ember-2.9 and Ember-2.12 applications.

### testem.js

{% gist eba344704af8fa88a138c7a079d1d1f5 %}
