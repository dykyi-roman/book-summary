Name: Clean Code

Author: Robert Martin

Description: This is must read book
___

I want a describe some rule how a take your code clear and clean. Before we start write a rules we must understand what is a good code. 
In this regard, my point of view coincides with the authors of such books as Robert Martin, Bjarne Stroustrup's, Dave Thomas, Gradi Buch and other big mans.

This is code is easy read not only owner and other developer. 
This code when author make a good work for a write code.
This code understand after first read. 
This code not have a logic dublication.
This code esy cover a tests.
This code esy supports.

##### Content  
[Name](#Name)  
[Function](#Function)  
[Comments](#Comments)  
[Objects And Structure Data](#ObjectsAndStructureData)  

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

=> Use a TODO marks for a temp part od code

=> Update comment togather with update your code

# <a name="ObjectsAndStructureData"><h1>Objects and Structure data</h1></a>

=> Law of Demeter (LoD)

=> The Object is shown behaviors and hides a data. The structure data is otherwise. Avoid a mix.

=> Avoid null return, use a special case or null object or generate excaption

=> Not use a null parameter by default int function attribute



