This is a fork of django-taggit-autocomplete, which can be found at:
https://github.com/Jaza/django-taggit-autocomplete

It's the same app with some fixes

*** Installation ***

   1. You need to have django-taggit already installed
   2. Download django-taggit-autocomplete and use setup.py to install it on your system:
        python setup.py install
   3. Paste the contents of jquery-autocomplete/ and put it in the folder specified in your project's MEDIA_URL setting.
        If you want to put it somewhere else add TAGGIT_AUTOCOMPLETE_JS_BASE_URL to your project settings.
   4. Add "taggit_autocomplete" to installed apps in your project's settings.
   5. Add the following line to your project's urls.py file:

      (r'^taggit_autocomplete/', include('taggit_autocomplete.urls')),

*** Usage ***
** Using the model field **

You can use TaggableManager to enable autocompletion right in your models.py file. In most cases this is the easiest solution. Example:

from django.db import models
from taggit_autocomplete.managers import TaggableManager

class SomeModel(models.Model):
        tags = TaggableManager()
