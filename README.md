nbpy
====

A Python interface to NationBuilder API

This is very much a work in progress, so only parts of the API are supported (mainly the People endpoints). As it is a work in progress, expect major changes in the library in the not-too-distant future. So if you do build something on top of this library now, it may or may not work in the next version. 

Some of the features simply do not work (e.g. `set_page_slug()` ), but this seems to be on the NationBuilder end, not a problem with the library.

It relies on [http://code.google.com/httplib2](httplib2) and [https://code.google.com/p/google-api-python-client/wiki/OAuth2Client](oauth2client). These are used because the original use of this was running on GAE. 

It also uses the builtin (I think) `json`, `urllib2` and `logging` modules. 

Example Usage: 

```python
import nationbuilder
import json

site = nationbuilder.NationBuilder('foo', 'FFAACC1123344556677889900')
content = site.get_person(123)
person = json.loads(content)
print "First Name: %s" % person['person']['first_name']
```

