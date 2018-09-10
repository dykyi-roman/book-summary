
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
[ - Module, Agregate, Factory](#Module)  

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

## <a name="Module"><h2>Module</h2></a>
Modules need to develop as well as project classes. They also need to be refactoring. The names for the modules must be from the model domain. Module separation is useful for developers. It makes it possible to work with the module-code as with the box without deep into details of the realisation


