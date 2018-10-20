Name: Domain Driven Design

Author: Vaughn Vernon

Description: This is must read book
___
##### Content  
[Intro](#Intro)   
[Bounded Сontext](#BoundedСontext)

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
From you depend on how will be communicated your context, it can be rest or queue (if few contexts in one module it can be aggregate root).
