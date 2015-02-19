jsisie
======

A .NET parser for SIE files that can read files of version 1 to 4 (including 4i)

To read a file create an instance of SieDocument and call ReadDocument.

There are some bool properties in SieDocument that changes how the parsing works:

+ IgnoreMissingOMFATTNING: If true the parser will not flag a missing #OMFATTN as an error.
+ IgnoreBTRANS: If true #BTRANS (removed voucher rows) will be ignored.
+ IgnoreRTRANS: If true #RTRANS (added voucher rows) will be ignored.
+ StreamValues: If true don't store values internally. The user has to use the Callback class to get the values. Usefull for large files.
+ ThrowErrors: If false then cache all Exceptions in SieDocument.ValidationExceptions

**Not all features are implemented yet:**

+ #UNDERDIM: There are no instances of this in the published example files.
+ #FLAGGA: Since parser is only reading data it will not set #FLAGGA to 1 when it is done.
+ Writing SIE files is not implemented at all.


Even if you use this parser you should get familiar with the file specification.
I have not made any extensive efforts to validate the resulting data against the files so please do your validation and tell me if you find any errors.


To install this package via nuget write
	Install-Package jsisie
int the nuget console in Visual Studio 

Follow [this link](http://www.sie.se/?page_id=20) for swedish versions and [this link](http://www.sie.se/?page_id=250) for english versions
