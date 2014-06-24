django-excel-response
=====================

This is a fork of https://pypi.python.org/pypi/django-excel-response which was originally http://djangosnippets.org/snippets/1151/

I have added a simple regex check for float values and then setting the locale to the default locale and applying atof to the float. Fixes this problem I mention here - http://stackoverflow.com/questions/24296730/django-python-and-isues-with-xlwt-locale-formatting
