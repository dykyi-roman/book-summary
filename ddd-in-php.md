Name: Domain-Driven Design in PHP

Author: Carlos Buenosvinos, Christian Soronellas, and Keyvan Akbary

Description: In this book you can find a real examples written in PHP showcasing DDD Architectural Styles, Tactical Design, and Bounded Context Integration

Tactical patterns: Entities, Value Objects, Services, Domain Events, Aggregates, Factories, Repositories and Application Services; with real examples in PHP. Explore the advantages of Hexagonal Architecture and understand Strategic design with Bounded Contexts and their integration through REST and message queues.

Github: https://github.com/dddinphp

PDF: [read](http://xeroxmobileprint.net/DiscoveryTable/test/folder1/Domain-Driven_Design_in_PHP.pdf)
___
# What is DDD

DDD is not about developming, this is about developing knowledge around the business and using the technology to provide value. 
DDD is not about technology, is actually about providing value in the field you are working on, by focusing on model.
DDD is not a silver bullet for every problem in Software, and highly depends on the amount of complexity you are dealing with.
DDD is not a good desigin if you have only CRUD application. But If your product like a snowball, then DDD will be able to help you.
If your application has less than 30 use-cases, it might be simpler to use a framework like Symfony or Laravel to handle your business logic.

## What DDD giver for us

1)Ubiquitous Language: Developers and domain experts team up to build the knowledge base by sharing the same language.

2) Strategic Design: Domain-Driven Design addresses the strategy behind the direction of the business, not just the technical aspects. It helps define the internal relationships and early warning feedback systems.

3) Tactical Design: Help for separate logic layer from code. And split the program into layers. The main units in DDD there is – Value Object, Entity, Repository, Service, Aggregation, Factory…

# Layered Architecture

From the code maintainability and reuse perspectives, the best way to make this code a bit easier to maintain would be splitting up concepts - creating layers for each different concern.

## User Interface Layer
The Client Layer consumes Application Services and invokes business logic on these services. Every invocation is a new transaction.

## Application Layer
The Application Layer takes commands from the User Interface Layer and translates these commands to use case invocations on the domain layer. The Application Layer also provides transaction control for business operations. 
Include:

• Controller 

• View

• Event


## Domain Layer
The Domain Layer contains the real business logic, but does not contain any infrastructure specific code. The infrastructure specific implementation is provided by the Infrastructure Layer. Include:

• Aggregate

• Entity

• Domain Event

• Message	(Bus)

• Repository Interface

• ValueObject


So far we’ve covered the following sections of the Domain layer:

•	Encapsulating your application’s business rules

•	Implementing The Specification Pattern

•	The User Entity and The Ubiquitous Language

•	What are the benefits of using Repositories?

•	Defining the building blocks of Domain Driven Design

•	Implementing Domain Events

•	Creating Domain Services

•	Creating a User Registration Domain Service

•	Building a Password Reminder Domain Service

•	Creating your own Domain Event Dispatcher


## Infrastructure Layer
The Infrastructure Layer provides the infrastructure dependent parts for all other layers. This is up to you, as long the storage provides transaction control and guarantees consistency.  Include:

• DTO

• Repository

• Service

• Mailer


# DDD conponents

## DTO

DTO – object which nothing exist inside. No methods. No logics. Must do it only simple data type.

Usually DTO write for each services because adaptation him for other service will be difficult. For example data for needed to a REST and UI its not the same data. 

Why create a DTO instead of giving an instance of the Model to the View layer? The main reason and the short answer is, again, Separation of Concerns.  Letting the view inspect and use a Model instance leads to tight coupling between the View layer and the Model layer. In fact, a change in the Model layer can potentially break all the views that make use of the changed Model instances.

## Value Objects (VO) 



### Bounded contexts

A very important part of DDD is bounded contexts. The architecture of a Domain Driven Design project is comprised of three main areas. Each areas has it’s own unique role and responsibilities within the bigger context of the entire application. 



# Hexagonal Architecture
Port is a connector with a pluggable Adapter which transforms an outside input to something the inside application can understand. In terms of the DIP, the Port would be a high level module and an Adapter would be a low level module. Fu
