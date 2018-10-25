Name: Domain Driven Design

Author: Vaughn Vernon

Description: This is must read book
___
##### Content  
[Intro](#Intro)   
[Bounded Сontext](#BoundedСontext)   
[Architecture](#Architecture)  
[VO](#VO)  

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
