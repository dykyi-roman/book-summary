Name: Domain-Driven Design in PHP

Author: Carlos Buenosvinos, Christian Soronellas, and Keyvan Akbary

Description: In this book you can find a real examples written in PHP showcasing DDD Architectural Styles, Tactical Design, and Bounded Context Integration

Tactical patterns: Entities, Value Objects, Services, Domain Events, Aggregates, Factories, Repositories and Application Services; with real examples in PHP. Explore the advantages of Hexagonal Architecture and understand Strategic design with Bounded Contexts and their integration through REST and message queues.

Github: https://github.com/dddinphp

PDF: [read](http://xeroxmobileprint.net/DiscoveryTable/test/folder1/Domain-Driven_Design_in_PHP.pdf)
___
##### Содержание  
[What is DDD](#DDD)  
[What DDD giver for us](#DDD2)  
[Layered Architecture](#LayeredArchitecture)  
[ - User Interface Layer](#UserInterfaceLayer)  
[ - Application Layer](#ApplicationLayer)  
[ - Domain Layer](#DomainLayer)  
[ - Infrastructure Layer](#InfrastructureLayer)  
[DDD Conponents](#DDDConponents)  
[ - DTO](#DTO)  
[ - Value Objects (VO)](#VO)  
[ - Embedded Value](#EmbeddedValue)  
[ - Entity](#Entity)  
[    ⋅⋅⋅ Anemic Domain Model](#AnemicDomainModel)  
[    ⋅⋅⋅ Rich Domain Model](#RichDomainModel)  
[ - Aggregation](#Aggregation)  
[ - Repository](#Repository)  
[ - Services](#Services)  
[   ⋅⋅⋅ Application](#Application)  
[   ⋅⋅⋅ Domain](#Domain)  
[   ⋅⋅⋅ Infrastructure](#Infrastructure)  
[Specification Pattern](#SpecificationPattern)  
[Factory](#Factory)  
[Bounded Contexts](#BoundedContexts)  

___
# <a name="DDD"><h1>What is DDD</h1></a>

Object Oriented Design - is a set of principles and schemes for creating optimal systems of objects. The DDD can halp with this. 

DDD is not about developming, this is about developing knowledge around the business and using the technology to provide value. 
DDD is not about technology, is actually about providing value in the field you are working on, by focusing on model.
DDD is not a silver bullet for every problem in Software, and highly depends on the amount of complexity you are dealing with.
DDD is not a good desigin if you have only CRUD application. But If your product like a snowball, then DDD will be able to help you.
If your application has less than 30 use-cases, it might be simpler to use a framework like Symfony or Laravel to handle your business logic.

## <a name="DDD2"><h2>What DDD giver for us</h2></a>

1)Ubiquitous Language: Developers and domain experts team up to build the knowledge base by sharing the same language.

2) Strategic Design: Domain-Driven Design addresses the strategy behind the direction of the business, not just the technical aspects. It helps define the internal relationships and early warning feedback systems.

3) Tactical Design: Help for separate logic layer from code. And split the program into layers. The main units in DDD there is – Value Object, Entity, Repository, Service, Aggregation, Factory…

# <a name="LayeredArchitecture"><h1>Layered Architecture</h1></a>

From the code maintainability and reuse perspectives, the best way to make this code a bit easier to maintain would be splitting up concepts - creating layers for each different concern.

## <a name="UserInterfaceLayer"><h2>User Interface Layer</h2></a>
The Client Layer consumes Application Services and invokes business logic on these services. Every invocation is a new transaction.

## <a name="ApplicationLayer"><h2>Application Layer</h2></a>
The Application Layer takes commands from the User Interface Layer and translates these commands to use case invocations on the domain layer. The Application Layer also provides transaction control for business operations. 
Include:

• Controller 

• View

• Event

## <a name="DomainLayer"><h2>Domain Layer</h2></a>
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

## <a name="InfrastructureLayer"><h2>Infrastructure Layer</h2></a>
The Infrastructure Layer provides the infrastructure dependent parts for all other layers. This is up to you, as long the storage provides transaction control and guarantees consistency.  Include:

• DTO

• Repository

• Service

• Mailer


# <a name="DDDConponents"><h1>DDD Conponents</h1></a>

## <a name="DTO"><h2>DTO</h2></a>

DTO – object which nothing exist inside. No methods. No logics. Must do it only simple data type. One DTO for one Service becouse for Rest you need one data and for a UI you need orther.

Usually DTO write for each services because adaptation him for other service will be difficult. For example data for needed to a REST and UI its not the same data. 

Why create a DTO instead of giving an instance of the Model to the View layer? The main reason and the short answer is, again, Separation of Concerns.  Letting the view inspect and use a Model instance leads to tight coupling between the View layer and the Model layer. In fact, a change in the Model layer can potentially break all the views that make use of the changed Model instances.

## <a name="VO"><h2>Value Objects (VO)</h2></a>

Value Objects are a fundamental building block in Domain-Driven Design, used to model concepts of your Ubiquitous Language in code. They can be seen as small, simple objects such as money or a date range. 

Value Objects are immutable, so they cannot be modified, they cannot change their state. Every state changing method returns a new instance of the value Object.

Value objects can have methods, but the behavior of a method doesn’t ever change the object’s state. If a method needs to change a property, it will return a brand new instance of the value object instead of modifying the existing one.

Value Objects are easier to create, test, use and maintain.

Modelled as a Value Object if: 

• It measures, quantifies, or describes a thing in the domain

• It can be kept immutable

• It models a conceptual whole, by composing related attributes as an integral unit

• It is completely replaceable when the measurement or description changes

• It can be compared with others through value equality

• It supplies its collaborators with Side-Effect-Free behaviour

It is also good to point out that it is not recommended to hold references to entities in your Value Objects.

Must has a validation logic. Book good describe how make validate(LocationValidationHandler $validationHandler) method. 

Value Objects are not persisted on their own, they are typically persisted within an Aggregate.

Not recommended save a reference for another object.

For a comparison, a VO property must be a equals() method.

Value Objects should not be persisted as complete records, though it is an option in some cases. Instead it is best to use Embedded Value. As Value Objects are small, Embedded Value is usually the best choice to persis data to ORM. OR Doctrine Custom Types.

Another interesting detail about modeling your Domain concepts using Value Objects is about its security benefits.

## <a name="EmbeddedValue"><h2>Embedded Value</h2></a> 

Many small objects make sense in an OO system that don't make sense as tables in a database. Examples include currency-aware money objects and date ranges. Although the default thinking is to save an object as a table, no sane person would want a table of money values. An Embedded Value maps the values of an object to fields in the record of the object's owner.

## <a name="Entity"><h2>Entity</h2></a>  

Entity – this is value object with identity. For example: Order, Person. Can exist in self a Value Object.

Surrogate Identity - This is a situation when part of fields take from inheritance Entity class.

Entities are mutable, and as such this could lead to undesirable side-effects occurring in the Value Object.

Entire object validation: Extracting the validation to an external service is a good practice.

Object compositions: Complex object compositions could be validated through Domain Services. A good way of communicating this to the rest of the application is through Domain Events.

Use a validation inside an Entity is anti-pattern. Better use a VO or Validation service use inject Entity inside.

If the client cannot provide the identity generally the preferred way to handle the identity operation is to let the application generate the identities, usually through a UUID. The best recommended would be the one developed by Ben Ramsey at https://github.com/ramsey/uuid

### <a name="AnemicDomainModel"><h4>Anemic Domain Model</h4></a>  

Anemic Domain Model Breaks Encapsulation. Anemic Domain Model Brings a False Sense of Code Reuse. 

Anemic Domain Model - anti-patterns. Has only getters and setters. This is not have a logic inside and have a service that include logic. 

This is comes for us from procedure delelop style. This approach broken basic idea of Object Oriented Design, which consists in the combination of data and process (behavior). Often, these domain objects come with architectural rules not to place any domain logic in them.

### <a name="RichDomainModel"><h4>Rich Domain Model</h4></a>  

Rich Domain Model is a model with a state and behavior (business logic).

The logic that should be in the domain object is domain logic, for example: validation, calculations, or whatever you call "business rules". Many post logic in services forms(build) this service layer. But this is not a variant.

## <a name="Aggregation"><h2>Aggregation</h2></a>  

Aggregates are the basic element of transfer of data storage (Repository). An aggregate will have one of its component objects be the aggregate root. Example Car and car details. Also we can detect a rood Aggregate, usualy this is  aggregate with most Entity and VO.

Aggregates can only be associated with identifiers. They can not share any other data with each other. 

Aggregates is combined together Entity. One Entity can has a other VO.

## <a name="Repository"><h2>Repository</h2></a>   

Repository as the mechanism between the domain and data mapping layers, acting like an in-memory domain object collection.

Repository – this is storage for data(collection), but not a DAO. Data Access Objects are a common pattern for persisting domain objects into the database. The significant difference being that Repositories represent collections, whilst DAOs are closer to the database, often being far more table-centric. Typically a DAO would contain CRUD methods for a particular domain object, repository is more short. The main problem with DAOs is that their responsibilities are not clearly defined. DAOs are usually perceived as a gateway to the database.

From the collections point of view there is no need for a save method in the repository. But if you do not have a unit of work, keeping track of Aggregate changes is a difficult task you can add save method.

Repositories save and retrieve Entities or Aggregates to or from the underlying storage mechanism. Repositories can use DAOs(Data Access Objects) for retrieving data and to encapsulate database specific logic from the domain.

Good practic use RepositoryInterface and implement them for esy change Repository to (Redis, InMemory, Doctrine...).

Doctrine use a Data Mapper pattern and use Doctrine Query Language.

## <a name="Services"><h2>Services</h2></a>   

Service - this is entry point for a work with Domain. Do not write universal Service (SRP). Service must resurn a DTO. 
For create service layer in common using a Command Bus. 

If we generate excaption on the Service layer we must cathc this excaption on this layer to.

There are typically three different types of service which you will encounter, these are: Application, Domain, Infrastructure. 

### <a name="Application"><h4>Application</h4></a>  

Application services are the middleware between the outside world and the domain logic. The purpose of such a mechanism is to transform commands from the outside world into meaningful domain instructions.

In Domain-Driven Design, transactions are handled at the Application Service level.

First one is that Application Services should not include such business logic.

Example: Command Bus, Controller(MVC) or Transaction layer.

### <a name="Domain"><h4>Domain</h4></a>  

Throughout conversations with domain experts, you will come across concepts in the Ubiquitous Language that cannot be neatly represented as either an Entity or Value. A domain service can be defined as an operation that doing a domain task and we can not put into an Entity or a Value Object.

Domain services work with domain types.

Domain services don’t hold any kind of state by themselves.

### <a name="Infrastructure"><h4>Infrastructure</h4></a> 

Example: Mailler, Logger....

## <a name="SpecificationPattern"><h1>Specification Pattern</h1></a> 

A common implementation for the criterion object is the Specification Pattern. A specification is just a simple predicate that takes a domain object and returns a boolean. Given a domain object, it will return true if it specifies the specification and false otherwise.

The Specification object has a single public isSatisfiedBy() method that will return a boolean value

By using The Specification Pattern, you can use the Specification Object anywhere that is necessary in your application. Your application does not need to know how the business rule is enforced because it is internal to the Specification object. If the business rules is changed, you only have to change that single source of truth.

Using The Specification Pattern also makes having alternative, or multiple rules easier to work with. By encapsulating each rule as a Specification object you are free to use many instances together to satisfy the complex requirements of the organisation without getting bogged down in complex or unmaintainable code.

Not needed in Services.

Read more: https://www.culttt.com/2014/08/25/implementing-specification-pattern/

## <a name="Factory"><h1>Factory</h1></a>  

Factory – pattern from GOF. Defines an interface for creating an object.

## <a name="BoundedContexts"><h1>Bounded Contexts</h1></a>

A very important part of DDD is bounded contexts. The architecture of a Domain Driven Design project is comprised of three main areas. Each areas has it’s own unique role and responsibilities within the bigger context of the entire application. 


# Hexagonal Architecture
Port is a connector with a pluggable Adapter which transforms an outside input to something the inside application can understand. In terms of the DIP, the Port would be a high level module and an Adapter would be a low level module. Fu
