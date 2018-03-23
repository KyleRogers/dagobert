Dagobert is intented to be an extensible library providing access to multiple bank accounts and financial services mainly through using HBCI. Dagobert was inspired by [HBCI4Java](https://github.com/hbci4j/hbci4java/). The library is intented to be used in server environments and web-applications.

## The name 'Dagobert'
Is taken from the German name of the comic figure *Scrooge McDuck* created by [Carl barks](https://de.wikipedia.org/wiki/Carl_Barks). Like Dagobert/Scrooge McDuck the Dagobert library will count your money and help you master your expenses and income.
 
## Why don't you use HBCI4Java?
 
### Lack of abstraction
Although the project claims to abstract away the details of HBCI that is not fully true in my opinion.
Of course: On a technical level they are right: One has not to cope with the details and nitty gritty details implied by
different versions of HBCI and a developer does not need to understand the full format /output that will be sent over the wire.

BUT: The projected does not abstract away HBCI and it's details on a domain/information basis.
Which "Geschäftsfälle" (use cases) exist? Which do I need to accomplish my goal/retrieve the information necessary?
What data do I get and what does it mean (see also [Lack of Documentation](#lack-of-documentation))

In the end I DO need to know HBCI: I might not need to know the technical details of the protocol but I need to know the Geschäftsfälle (use cases) and their data structure to work with the library.


### Lack of developer guidance through API
There is no guidance for developers. 
All classes have setters and getters that can be freely manipulated.
There are no checks for parameters in place.
If I forget one line of the example code I'll get a non-explaining NPE or ISE when executing.
It's really hard to debug and find out WHY I need to set some parameters and what parameters and settings correlate.
  
 
### Lack of Documentation
The project has no good documentation that helps getting started. 
Of Course: There is a sample project to get the basics right but that's all.
There is no documentation how to do different things and how to use HBCI.

The project introduces a business view on domain objects like accounts, IBAN, journals  etc. but does not explain parameters nor information and data that can be retrieved.
For example: What is a 'Unterkontomerkmal' aka 'subnumber' of an account? What does that mean? What can I do with it? What are valid values?
 
Although the project claims to abstract HBCI away you need to understand the HBCI details to work with the API but there is no documentation for that.


### Lack of multi user and server support
The implementation is not targeted on server environments and multi user or multi account usage.
HBCI4Java uses static methods and fields all over the place making multi-threaded usage a nightmare.
The implementation comes with it's own static logging and in addition I had problems supporting multiple bank connections in parallel (even single threaded/single user).
 
 
 ## Why don't you use FinTecs APIs like [BanksAPI](https://banksapi.de/) or [finAPI](https://www.finapi.io/)?
 -- TODO
