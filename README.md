# Book summary

Here I will publish a short summary of books and article that I read.

1) [Domain-Driven Design in PHP](https://github.com/dykyi-roman/book-summary/blob/master/ddd-in-php.md)
2) [Patterns of Enterprise Application Architecture](https://github.com/dykyi-roman/book-summary/blob/master/arhitektura_korporativnyh_programmnyh_prilozhenij_fauler_m.md)
3) [Elegant Objects](https://github.com/dykyi-roman/book-summary/blob/master/elegant-objects.md)
4) [DDD Eric Evans](https://github.com/dykyi-roman/book-summary/blob/master/ddd-eric-evans.md)
5) [Clean Code](https://github.com/dykyi-roman/book-summary/blob/master/clean-code.md)
____
# Articles:

* 
____

My rules:
* Provide a SOLID principe in your code. This acronym make your code both legible and extensible.

* Do not create DTO for DTO, VO for VO, Service for Service... Any object should be created to solve a problem.

* Do not use go-to. http://david.tribble.com/text/goto.html#example-e-1

* Repeat code is - OK, repeat logig is NOT OK. Abstraction is reusible, code is not reusible (Marco Piveta)

* The code must be checked a SOLID principle after code-review (Uncle Bob). Code-review must be doing before manual test

* Object must be transfer for another layer using DTO (low coupling principle)

* Talk with a Domain layer using CommandBus and talk with a UI layer using Query Bus. Comand => Handler (SRP)

* All class is final. All properti and method private by default. Follow the immutable state in your class (no setters)

* Do not use a option dependencies, better put DI in controller. 

* Do not use a option swich param in function. Example: setActive($active = true)

* Do not use a Fluent Interfaces. Becouse its difficult to maintainability and add new method. better usa a decorators

* Do not use a Traits

* Write tests for outside package. The code must do it what you expect 

* Avoid use a pattern name and domain name in word postfix 




