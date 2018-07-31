# book-summary

Here I will publish a short summary of books and article that I read.

1) [Domain-Driven Design in PHP](https://github.com/dykyi-roman/book-summary/blob/master/ddd-in-php.md)
2) [Patterns of Enterprise Application Architecture](https://github.com/dykyi-roman/book-summary/blob/master/arhitektura_korporativnyh_programmnyh_prilozhenij_fauler_m.md)
3) [Elegant Objects](https://github.com/dykyi-roman/book-summary/blob/master/elegant-objects.md)

____
My rules:

* Do not create DTO for DTO, VO for VO, Service for Service... Any object should be created to solve a problem.

* Do not use go-to. http://david.tribble.com/text/goto.html#example-e-1

* Repeat code is - OK, repeat logig is NOT ok.

* The code must be checked a SOLID principle after code-review (Uncle Bob)

* Code-review must be doing before manual test

* Object must be transfer for another layer using DTO (low coupling principle)

* Talk with a Domain layer using CommandBus and talk with a UI layer using Query Bus. Comand => Handler (SRP)
