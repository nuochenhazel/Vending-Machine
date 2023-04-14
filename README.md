# Vending Machine

## Overview

**What will the application do?**

As the name of the application indicates, 
the application will be functioning in a vending machine. 
What is more, it is mainly designed for a special vending machine 
that stores dog food for street dogs. 
Therefore, not only this application can be served for the customers to purchase merchandise 
and worker to restock certain products in the vending machine, 
but the vending machine will also automatically pour the dog food into a container at the bottom 
whenever there is a purchase.


**Who will use it?**

The application can be used by both the customers and the workers according to their specific needs.

**Why is this project of interest to you?**

This application intends to make one feel the happiness of helping as strongly as possible. 
As we all know, humans have powerful empathy, a spontaneous ability think and understand what others feel. 
That is the reason why we feel pleasant after helping others. 
However, we can feel the empathy toward one suffered being, 
but we cannot experience a hundred times the same empathy when facing a hundred suffered beings. 
As mentioned earlier, the vending machine is specifically designed to help the street dogs 
without us putting in explicit efforts. 
Triggering the dog food to come out as soon as one purchases the product from the vending machine
can make us feel more connected with the surrounding animals.
Seeing the impact of the behaviour directly makes our everyday behaviour more meaningful to us.

## User Story

As a consumer, I want to:
- add funds to the vending machine
- choose the merchandise I want to buy

As an employee, I want to:
- restock the existing products
- create and stock new products
- save all the information (productName, productPrice) of the products automatically that have been stocked
- load all the information of the products automatically 
everytime I want to stock a product that has its information stored already

## Phase 4: Task 2

Activities:[
<br>Mon Mar 28 16:04:32 PDT 2022: Restock Completed:  10 chocolates on slot 101,
<br>Mon Mar 28 16:04:48 PDT 2022: Restock Completed:  10 cookies on slot 102,
<br>Mon Mar 28 16:05:06 PDT 2022: Restock Completed:  5 waters on slot 103,
<br>Mon Mar 28 16:05:21 PDT 2022: Purchase Completed: 1 cookie on slot 102,
<br>Mon Mar 28 16:05:29 PDT 2022: Purchase Completed: 1 chocolate on slot 101,
<br>Mon Mar 28 16:05:40 PDT 2022: Restock Completed:  1 cookie on slot 102]


## Phase 4: Task 3
If I had more time to work on the project, the model package and the ui package
can both be improved. In the model package, the relationship is simpler. First thing
that can be changed is to remove the relationship between Product and VendingMachine,
since there is no implementation based on this relationship and the VendingMachine can always
access the product through the slots if needed. Also, a design pattern can be useful to
restructure the hierarchy. Since the vending and restocking both process in the VendingMachine class,
the VendingMachine can extend the Java's Observable, the Slot and Product class can implement Java's Observer.
Thus, whenever there is a purchase or restock, the corresponding slot and product will be notified and updated at the
same time.

<br>In the ui package, I think it is necessary to introduce a hierarchy to restructure most of the classes,
since even though each class has their own distinct function, there still exist a number of similarities 
among them. For example, since there are three ways to restock a product depending on whether the product
already exists on the slot and whether its information (name, price) has been saved previously. In the program, 
the processes of all three ways acts independently, but they all share several similar actions. 
Thus, both RestockConsole and RestockProductNotInSlotConsole can extend a restocking console 
abstract class that extracts all the similar functions. What's more, it is noticeable that a VendingMachine has been 
passed as a parameter between most of the classes in the ui package, which seems a bit redundant and not elegant 
indeed. Thus, introduce a new super class or interface that possess one VendingMachine field should be enough. 
Last but not least, verifyPasswordConsole only has limited functionality thus it can be turned into a 
pop-up window instead of being a single frame that only verifies a series of numbers.# Vending-Machine
