# Book summary

Here I will publish a short summary of books and article that I read.

1) [Domain-Driven Design in PHP](https://github.com/dykyi-roman/book-summary/blob/master/ddd-in-php.md)
2) [Patterns of Enterprise Application Architecture](https://github.com/dykyi-roman/book-summary/blob/master/arhitektura_korporativnyh_programmnyh_prilozhenij_fauler_m.md)
3) [Elegant Objects](https://github.com/dykyi-roman/book-summary/blob/master/elegant-objects.md)
4) [DDD Eric Evans](https://github.com/dykyi-roman/book-summary/blob/master/ddd-eric-evans.md)
5) [Clean Code](https://github.com/dykyi-roman/book-summary/blob/master/clean-code.md)
6) [DDD Vernon](https://github.com/dykyi-roman/book-summary/blob/master/ddd-vernon.md)
7) [Refactoring](https://github.com/dykyi-roman/book-summary/blob/master/refactoring.md)
____

My rules:
* DRY is not a silver bullet. Imagine that you have a class (A) and class (B) with the same logic in code. And you create a class (C) and move this code here. All looks fine you do not have duplication in your code, but when you something changes in the logic - changing the logic in 2 classes. So, the good design is to have a control for you abstraction use SRP for you class in Shared Kernel area (DDD)

* Will always be broken some principle, the goal is still to always choose the minimum of evil and skillfully maneuver in this shit

* Service locator as anti-pattern Use DI https://sarvendev.com/en/2017/11/service-locator-vs-dependency-injection-en/

* Provide a SOLID principe in your code. This acronym make your code both legible and extensible

* After the finish of work with function, to make sure that this is a best your code. Stop, and make refactoring

* Do not create DTO for DTO, VO for VO, Service for Service... Any object should be created to solve a problem

* Do not use go-to. http://david.tribble.com/text/goto.html#example-e-1

* Repeat code is - OK, repeat logig is NOT OK. Abstraction is reusible, code is not reusible (Marco Piveta)

* The code must be checked a SOLID principle after code-review (Uncle Bob). Code-review must be doing before manual test

* Low coupling must be folow between methods too. Example: using one variable in both methods create a lot of coupling

* Object must be transfer for another layer using DTO (low coupling principle)

* Talk with a Domain layer using CommandBus and talk with a UI layer using Query Bus. Comand => Handler (SRP)

* All class is final. All properti and method private by default. Follow the immutable state in your class (no setters)

* Do not use a option dependencies, better put DI in controller

* Do not use a option swich param in function. Example: setActive($active = true)

* Do not use a Fluent Interfaces. Becouse its difficult to maintainability and add new method. better usa a decorators

* Do not use a Traits https://codereview.stackexchange.com/questions/74077/trait-accessing-variables-of-classes-using-it

* Write tests for outside package. The code must do it what you expect 

* Use a pattern name and domain name in class name postfix 

* Avoid situation when method uses the functionality of another. It`s better to put this code inside the object


