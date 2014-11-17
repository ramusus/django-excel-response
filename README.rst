=====================
django-excel-response
=====================

This is UPGRADED VERSION OF http://djangosnippets.org/snippets/1151/ uploaded to pypi.
Author is Tarken.

A subclass of HttpResponse which will transform a QuerySet,
or sequence of sequences, into either an Excel spreadsheet or
CSV file formatted for Excel, depending on the amount of data.
All of this is done in-memory and on-the-fly, with no disk writes,
thanks to the StringIO library.

UPDATE from 7wonders:

I have added a simple regex check for float values and then replace the commas
which are added by django locale back to decimal points.
Fixes this problem I mention here -
http://stackoverflow.com/questions/24296730/django-python-and-isues-with-xlwt-locale-formatting
and should work with excel etc.

UPDATE from ramusus:

Change limit of allowed number of excel rows from 65536 to 1048576 according this
http://superuser.com/questions/366468/what-is-the-maximum-allowed-rows-in-a-microsoft-excel-xls-or-xlsx
Mostly because of problem with initial opening csv format files with utf-8 encoding described here
http://stackoverflow.com/questions/6002256/is-it-possible-to-force-excel-recognize-utf-8-csv-files-automatically/6488070#6488070


Installation
============

::

    pip install excel_response xlwt


Usage
=====

::

    from excel_response import ExcelResponse

    def excelview(request):
        objs = SomeModel.objects.all()
        return ExcelResponse(objs)


or::

    from excel_response import ExcelResponse

    def excelview(request):
        data = [
            ['Column 1', 'Column 2'],
            [1,2]
            [23,67]
        ]
        return ExcelResponse(data, 'my_data')
