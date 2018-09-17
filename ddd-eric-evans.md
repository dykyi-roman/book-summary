
Name: Domain Driven Design

Author: Eric Evans

Description: This is must read book

PDF: [read](https://domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf)
___
##### Содержание  
[Unique language](#UniqueLanguage)  
[ - Refining knowledge](#RefiningKnowledge)  
[ - Build Model](#BuildModel)  
Domain modeling components:   
[ - Entity, VO, Services](#Service)  
[ - Module, Aggregate, Factory](#Module)  
[Shared kernel](#SharedKernel)  
[Bounded context](#BoundedContexts)  
[ - Core Domain](#CoreDomain)  
___
# <a name="UniqueLanguage"><h1>Unique language</h1></a>

The main idea use language in diagrams, dialog, negotiations, conferences. not only in code and documentation. Use a model as a base for build language.  

The component of effective buld model:
* create a relationship with model end realization
* use a language that a base on the model
* create a detail model schema
* experiments and use a brainstorm

## <a name="RefiningKnowledge"><h2>Refining knowledge</h2></a>
You need to be prepared for the fact that knowledge will change. And they are not afraid to work on the processing of knowledge. Add the new world and change exist world in the model and in the code too. You can upgrade language describe voice model that you build sit on the conference and write most uses words. 


## <a name="BuildModel"><h2>Build model</h2></a>

A developer who writes a code must understand why the model is so important. Otherwise, this model will not be usable. 
If developers do not understand that with a change a code must change a model - refactoring make worse model. The goal ideo of the model - this is help developers. DDD with the help of the model - resolve a tasks using a processing of the knowledge bases on the unique language.

# <h1>Domain modeling components</h1>

## <a name="Service"><h2>Service</h2></a>
We have to separate between services on the domain and application. Most services belong to the infrastructure layer. Domain Service can work with infrastructure service. Most services create and work using a Entity and VO. 
All the domain logic is implemented in domain objects. The service layer is thin and used only for third party services. 

## <a name="Aggregate"><h2>Aggregate</h2></a>
We need a group Vo and Entity in Aggregate and set a boundary betwen agreggate. Sesect main object and set a core object in aggregate. And continue speak with aggregate from core-object. All operation must doing from core-aggregate object. And save a link only for a core object. Factory and repository must work only with aggregate, and encapsulate internal work with the object and transform them in life cycle object.  

## <a name="Module"><h2>Module</h2></a>
Modules need to develop as well as project classes. They also need to be refactoring. The names for the modules must be from the model domain. Module separation is useful for developers. It makes it possible to work with the module-code as with the box without deep into details of the realisation

# <a name="SharedKernel"><h1>Shared Kernel</h1></a>

Shared kernel - this is general part of code in code. The first integration strategy is to use a Shared Kernel, where a part of the Domain Model is shared between different teams working on the same application. Offten the shared kernel can be a code doman in the model. The common target this is set to min a duplication in code but not remove all duplication like in the bounded context. And make easy integration between two team.
You can`t change a shared kernal so аften like a other part of the architecture. If you work on the product with othe team(group team) you can`t input a change without consultation with another team. If you inject a change inside a product bought team must run tests.


# <a name="BoundedContexts"><h1>Bounded contexts</h1></a>

Template conformist - this is opposite to shared kernel, using in situation where one team not cooperates with another team.
Offten in development yoi need integrate your product with other, a good practic use a anticorruption layer. In development for this solution use a facade and adapter pattern. If you integrate with your internal product - situatuion more simple and you can modificate buth progrem part for integration. Otherwise you need yuse facade and transformer. 

## <a name="CoreDomain"><h2Core Domain</h2></a>

How consider the main problem and not spend a time for a detail. Distillation - this is a process divide a component for a select a main (core domain). With each step of the deepening refactoring, we abstract some aspect of knowledge and priorities. Core domain can help as to better understand a architecture and relationships between components? set a way for refactoring, focus on the main detail in the projects, help with comunication. 
