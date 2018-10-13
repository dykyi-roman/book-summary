Name: Clean Code

Author: Robert Martin

Description: This is must read book

PDF: https://www.investigatii.md/uploads/resurse/Clean_Code.pdf
___

I want a describe some rule how a take your code clear and clean. Before we start write a rules we must understand what is a good code. 
In this regard, my point of view coincides with the authors of such books as Robert Martin, Bjarne Stroustrup's, Dave Thomas, Gradi Buch and other big mans.

This is code is easy read not only owner and other developer. 
This code when author make a good work for a write code.
This code understand after first read. 
This code not have a logic dublication.
This code easy cover a tests.
This code easy supports.

##### Content  
[Name](#Name)  
[Function](#Function)  
[Comments](#Comments)  
[Objects And Structure Data](#ObjectsAndStructureData)  
[Tests](#Tests)  
[Code Smell](#CodeSmell)   
___
# <a name="Name"><h1>Name of (Variable, Function, Class, Interface)</h1></a>

=> The name of variable must be a short and understand

=> The name must convey what it does doing

=> The name must be comfortable for a search in the code

=> The name must say easy

=> Hungarian notation is a old practic

=> The name should not include a common word like: Manager, Process, Data, Info

=> The variable name can include a domain word and pattern postfix

# <a name="Function"><h1>Function</h1></a>

=> The function must be short and do it only one operation. One operation its means one job on the one code layer

=> Not afraid a long function name. A function must say what function do it

=> Replace switch operator to Abstract factory. Switch is broken a SRP and OC principle

=> A perfect situation when you use zero arguments in the function. A meny argument give for you many test combination

=> If function a change input element, the result must be return. Not void function use for that

=> Not use a bool argumet in funtion, this is broken a SRP principle. The better create a two function

=> Avoid a side effect after call you function (SRP principle). 

=> Function must doing something or answer for a question. set() or get() not in one time.

=> Put a try..catch block in another function for separate a bussines logic from catcherrors. 

=> Do not use try..catch for a put logic. in the catch. A code not must move from low level to upper. Broken OCP.

# <a name="Comments"><h1>Comments</h1></a>

=> THe first and the most importent rules is not use a comments

=> Use a TODO marks for a temp part of code

=> Update comment togather with your code

# <a name="ObjectsAndStructureData"><h1>Objects and Structure data</h1></a>

=> Law of Demeter (LoD)

=> The Object is shown behaviors and hides a data. The structure data is otherwise. Avoid a mix.

=> Avoid null return, use a special case or null object or generate excaption

=> Avoid null parameter by default in the attribute of a function

=> High cohesion and Low coupling support for a small class with SRP

=> Separate create and using object. Use DI, Factory, Proxy, Adapter patterns for that 

=> Use enum in your code

# <a name="Tests"><h1>Tests</h1></a>

=> Write tests for outside package. The code must do it what you expect

=> Test code must be good writing like your code code

=> TDD is a good practice

=> Write positive and negative tests

=> Use a service who can help with analyze your code

# <a name="CodeSmell"><h1>Code Smell</h1></a>

=> Comments: old, bad, not information, very big, code with comments - should be removed

=> The test should be running one command or one button

=> Function: A low count of component, without flag argument (boolean), obviously behavior

=> One language in one result file

=> Do not turn off protected layer in your language and IDE

=> Code: in the right layer of abstraction, without duplication, Use PSR-2 standart

=> Definition of variable near the using place

=> Functionality dependence

=> Reduce a use a static function and switch opeartor

=> Write a small function with a good name

=> Have to Understanding algorithm what are you doing

=> Encapsulate (if)condition inside a class or use a specification pattern

=> Avoid a negative condition

=> Use a Factory for many function that must call one by one

=> Code and function should be write on the one abstract layer

=> Keep a const and configuration in the high abstract layer

=> Follow the law of Demetra

=> Use a long name for public namespace and short for a private

=> Define a side effect your function in it name. Exxample: CreateOrReturnExistObject 
