django-excel-response
=====================

This is a fork of https://pypi.python.org/pypi/django-excel-response which was originally http://djangosnippets.org/snippets/1151/

I have added a simple regex check for float values and then replace the commas which are added by django locale back to decimal points. Fixes this problem I mention here - http://stackoverflow.com/questions/24296730/django-python-and-isues-with-xlwt-locale-formatting and should work with excel etc.
