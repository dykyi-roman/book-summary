Name: Domain Driven Design

Author: Vaughn Vernon

Description: This is must read book
___
##### Content  
[Intro](#Intro)   
[Bounded Сontext](#BoundedСontext)   
[Architecture](#Architecture)  
[VO](#VO)  
[DTO & DPO](#TDOTPO)  
[ - Data Transformer](#TD)  
[ - Presentation Model](#PM)  
[Module](#Module)  
[Aggregate](#Aggregate)  
[Repository](#Repository)  

# <a name="Intro"><h1>Intro</h1></a>

This book is written in order to reduce our time for the development of the DDD approach. 
Stickers that you stick on the dashboard or application work schema this is a not diagram project - this is a code shown in the diagram.
Ubiquitous language can exist only with bounded context.

A domain expert not only business analytics - it can be human who know maximum information about business.

Anemic model this is a way to build architecture named a transaction script. avoid her using

# <a name="BoundedСontext"><h1>Bounded context</h1></a>

Bounded context - consists of domain and subdomain. Most often the domain can be any large modules or functionals. One Bounded context can include one or more domain. Example: User and role = access context. 

The word book in two context means the diferent. Example in marketing the book this is a set of attributes(author, title, page count). In typography  the book this is a set of attributes(author, title, count, price...). A good way use a DTO for move object from one context to the second. If books use in both context - this is a bad architecture, but if this is not a shared kernel.

Start build your context map from the one big context. Then write names what you know inside this map, then grouping this names for a thema. Write a context line. After that describe a relation between context. In all context create inside VO, Entity, Aggregate, Events...
From you depend on how will be communicated your context, it can be rest or queue (if few contexts in one module it can be aggregate root). Example: supervisor call a worker => worker call a service => service call adapter => adapter call http facade => adapter take data => transform data => send response

# <a name="Architecture"><h1>Architecture</h1></a>

A lot of people thinks that many layers architecture - has a parent for all architectures. That contain with user interface, domain, application, infrastructure. One module does not know about existing another module. 
Up layer can contact only with a down layer and use only low relation. Example use patern mediator (command bus) or observer (events).

DDD aprouch good come in all architecture style:
- layered architecture
- hexagonal architecture 
- Events orientation (chanel and filters & Long processing)
- CQRS
- Event sourcing:
  save event + snapshot. First find object in snaphot table the  run all event FROM snapshot make time TO now 
- Data factory:
  Idea in save serialize object instead events and save in key(id) - value(bin object) data. The powerfull in replication and return agregate to client.


# <a name="VO"><h1>VO</h1></a>
VO:

* describe simple elements of the system

* is immutable, not change an object state 

* set attribute value only from a constructor or if you want to to use e setter - that must return a new vo object

* without side effect

* simple create, use, tests, support, update...

If one of the attributes from your object will be changing during a time object life - think about change object method.
In some case when you do not want use a STATE pattern you can take a VO + ENUM. 

Good practice has extended(return) VO from service. Example: CurrencyServive => return CurrencyType VO.
Another way is create factory, static create immutable VO for standart type. 

Writing the tests we need protect object from motification!

Some time we need save VO in DB. the data writing in DB need have an id for saving. We add attribute ID in VO. When its happens read 319 page and think about need transform VO to Entity or not. Anothr way use a parent primary key for save VO in another table 

# <a name="DTODPO"><h1>DTO & DPO</h1></a>

TDO - Domain Transfer Object - use for a transfer data between remove layers. Use for a display data in UI. Always Immutable. DTO create on the domain layer, serealize, and send be a network and deserealise on the presentation layer. If you not have a remote service TDO is not needed for you.

DPO - Domain Payload Object - alike a DTO case usage but using for application with one virtual machine. This object include a link for an objects and not exist fields with object properties. You can move this obhect between logic layer like a simle container object. DPO simle create. Thay spend a small memory because you not load all object for read property.But this way hava a minus becouse you have access for all object methods.

# <a name="TD"><h2>Data Transformer</h2></a>

Data Transfer Object - this object use like a param and inject from DI in constructor class. The service who use a transform object must doit a double dispatch.

# <a name="PM"><h2>Presentation Model</h2></a>

Presentation Model - this is a facade for work with a service method(logic) from UI. Work like adapter and hide a detail and give for presentation (function and property) with presentation orientation. The second his role - if some class not have a get() method thay can write a wrapper for each function without a getter. Instead of adding a field to the model that does not belong to it, you can use a Presentation Model. Can have a service by DI in the constructor and use only for DELEGATION operation from layer AND NO MORE. Exanmple: page 612(BacklogItemPresentationModel)

# <a name="Module"><h1>Module</h1></a>

Module this is a tool for related components with the same area together. When you think and operate domain components, you need follow simple rules:

1) Module can include 1-3 aggregate 

2) Choose the name in a domain area

3) Do not create module automatic. Do not creat folder service, entity ... and put all service in one folder and all enity in other

4) Follow a low coupling between module

In layer or hexagonal architecture common folder structure next: domain, infrastructure, user interface.

# <a name="Aggregate"><h1>Aggregate</h1></a>

Aggregate this is object that have inside Entity and VO. One Aggregate can be change in one transaction. One context have only one aggregate - this is a main rule. Use a AggregateId for set a link to other aggregate, do not use an object href.

# <a name="Repository"><h1>Repository</h1></a>

Realisation repository only for aggregate. Exist a two type repository: oriented by collection and persistence. Using collection you can not add twice the same aggregate. Collection save data not obviously and have a method save(). Repository can return VO or Aggregate.
Transaction better put in the Factory. DAO - for CRUD. No logic in repository.
