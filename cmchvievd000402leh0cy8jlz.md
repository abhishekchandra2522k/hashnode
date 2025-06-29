---
title: "How Data Stays Organized: The Magic of Relational Databases"
seoTitle: "How Data Stays Organized: The Magic of Relational Databases"
seoDescription: "This article focuses only on Relational Databases and how it came into existence. Please follow the DBMS series to understand the Databases and Management ."
datePublished: Sun Jun 29 2025 16:17:30 GMT+0000 (Coordinated Universal Time)
cuid: cmchvievd000402leh0cy8jlz
slug: how-data-stays-organized-the-magic-of-relational-databases
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1750575440897/7feff960-97ff-49ae-9d0e-047b29464676.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1750611356282/8f0a8e35-ad75-4a85-abab-e66e7ffd9ea0.png
tags: databases, sql, dbms, relational-database

---

Disclaimer: This article focuses only on Relational Databases and how it came into existence. Please follow the DBMS series to understand the Databases and Management Systems completely.

## Why Relational Database Model (HISTORY)?

To understand why relational database model came into picture, first we need to understand two historical models - **Hierarchical** and **Network Model**.

### Hierarchical Model

This is a fairly old model. It was primarily used by IBM in 60s and 70s and it is not seen much now due to its inefficiencies. So, let’s look at how does the data gets organized in a Hierarchical Model? As the name suggests - there is a hierarchy. It decides to store and organize the data in a tree like structure, and it has this concept of parent-child relationship.

In the below image, we can see that the parent *AUTHOR* has two children, *Abhishek* and *Amish*, and *Abhishek* and *Amish* have two children as well *Book1* and *Book2* (two books that they wrote). Please note every child can only have a single root (parent). This means we don’t have the ability to say that *Abhishek* and *Amish* both co-authored *Book2*, there is no linking of one’s child node to someone else’s child.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1749888104500/a7a39ce8-1506-4715-a2b9-af918e75e704.png align="center")

With this tree like structure, we have already put a constraint “one-to-many relationship” - Every **parent** can have multiple children, but every **child** can have only one parent.

To emulate this model or to see how the data was stored in a Hierarchical model, we can see an XML example:

```xml
<!-- ONLY FOR REPRESENTATION, BACK IN THE DAY - DATA WAS NOT STORED LIKE THIS IN A HIERARCHICAL MODEL -->
<Author> 
    <Abhishek>
        <Name>Abhishek Chandra</Name>
        <Country>India</Country>
        <Book1>
            <Released>06/04/1961</Released>
        </Book1>
        <Book2>
            <Released>01/12/1967</Released>
        </Book2>
    </Abhishek>
    <Amish>
        <Name>Amish</Name>
        <Country>India</Country>
        <Book1>
            <Released>06/04/1961</Released>
        </Book1>
        <Book2>
            <Released>10/01/1962</Released>
        </Book2>
    </Amish>
</Author>
```

Drawback: If I delete one of the parent node from the above structure, all the child node information will be deleted - POOF! So, the child data is ***tightly coupled*** here because it’s directly related to the parent node.

Again, these models are rarely used today due to their inefficiencies.

### Networking Model

The Networking Model expanded on the Hierarchical Model - allowing many-to-many relationships. Networking Model allows co-authoring, *Abhishek* can now help *Amish* on *Book1*.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1750261280222/8700e0c6-1109-4d95-a908-82991359eb30.png align="center")

As this model expanded on the Hierarchical Model and allowed many-to-many relationships, it became a bit more complex to manage your data. If we took our XML example from Hierarchical Model, it would look something like below for Networking Model:

```xml
<!-- ONLY FOR REPRESENTATION, BACK IN THE DAY - DATA WAS NOT STORED LIKE THIS IN A NETWORKING MODEL -->
<Author> 
    <Abhishek>
        <Name>Abhishek Chandra</Name>
        <Country>India</Country>
        <Book1 author="Amish" relation="co-author" />
        <Book2>
            <Released>01/12/1967</Released>
        </Book2>
    </Abhishek>
    <Amish>
        <Name>Amish</Name>
        <Country>India</Country>
        <Book1>
            <Released>06/04/1961</Released> <!-- This ONE -->
        </Book1>
        <Book2>
            <Released>10/01/1962</Released>
        </Book2>
    </Amish>
</Author>
```

If you see, *Book1* is authored by *Abhishek* and co-authored by *Amish*. Now, If *Amish* deleted *Book1* from his entries, the software would go and check all of the other data and see if there is a book that links to the Author *Amish*, so that it can manage the deletion. This method became more complex for the software to look at relationships and warrant the relationship between data.

So, this was the very basic overview of how hierarchical model and networking model worked back in the day, where one-to-many and many-to-many relationships came into picture. After a while, people started thinking that this tree like structure isn’t really working for us. So, in comes the **RELATIONAL MODEL**!

Let’s take a closer look at that.

## RELATIONAL MODEL

Most of the historical models we saw, they are informal, there isn’t any specific set of rules in place for the hierarchical model nor the network model. There was only an idea and there were some theoretical papers on those models but there weren’t any hard set of rules in place to follow (No Standardization).

So, came the Relational Model, which had the formalized set of rules, the **first model** with formalized set of rules to be exact.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1750609221091/bb157e8e-361c-4e61-86c7-015d3f995d68.png align="center")

If we see the above model (image), it doesn’t follow a parent-child structure anymore. It shows a completely different route. It follows a **TABLE** structure also called relations (in context of databases). Think of an excel sheet having columns and rows, and we store some data in those columns and rows and we can give the sheet a name, that’s very closely related to what tables are.

A table has the name AUTHOR and a table has the name BOOK.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1750685432010/2f89146b-409e-4999-bef3-5438e93bc1b6.png align="center")

When we look at the first table \[AUTHOR\], we see that the columns are not named as A,B,C as in an excel sheet, rather these are *authorId, firstName, lastName.* So, we are specifically saying what is going to go in the columns. We choose something that can uniquely identify each and every piece of the data, and the same goes for the \[BOOK\] table.

We don’t have a parent-child structure anymore, we have a table structure. Now, instead of having an author as a parent, each and every author is an individual piece of data with a **unique identifier (*authorId*)** and each and every book is also an individual piece of data with a unique identifier ***(bookId)***. Now, you maybe thinking, you see these tables as completely separate data, so how do we link them together? Well, in the Relational Model, we have a bunch of concepts that we will get into later on how to draw relationships between data. The image shows one way of doing it, via a third table (middle) where we map the *authorId* and the *bookId* from the \[AUTHOR\] and \[BOOK\] tables respectively. For example, *authorId (10,11)* are mapped to *bookId (100),* meaning that *Abhishek and Amish* both wrote *book1.* From the middle table, we can say that a specific author and book are related. We can now draw relationships in a much simpler way.

OK! OK! There has to be some kind of logic/automation that manages the links between the data - this system is managed by a **Database Management Software.**

### DBMS REVISITED

Refer - [Understanding Databases: Backbone of Modern Technology](https://abhishekchandra.hashnode.dev/understanding-databases-backbone-of-modern-technology)

**WHAT does a DBMS do?**

We saw each model has some formal or informal set of rules like *authorId, bookId* needs to be unique in case of Relational Model. We can’t have more than one parent mapped to a child node in case Hierarchical Model, and in the Network Model, if a child has two parents, and if we update anything we need to make the change at both places manually. All of these rules needs to be managed and we’re not gonna manage these, because these needs to be managed automatically. We don’t want to do manual data entry. So there is always a software in place to do such tasks. As the models grew, we went into the database oriented approach, meaning there is one piece of software that is going to manage the model and that is a **DATABASE MANAGEMENT SOFTWARE**. DBMS is a key player in making sure that when we do implement a table structured model, all of the relationships, all of the management of our data, the safety/security, and where it is going to be saved, DBMS is going to manage all this. You will get to understand more on DBMS as we progress in this series.

Let’s get back to the Relational Model’s terminologies:

### What is a Table in a Relational Model?

We have seen how to break down data, and each time, we’ve done so by identifying distinct entities or objects - like *author, book, users, etc.* A table represents one of these objects. In the below image, the object is “user”, and we create a table to represent it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1750864246078/c60dce8a-f715-40fe-947d-e2a472f470fc.png align="center")

We can see that at the top we have things as *id, firstName, lastName, sex, dob* \- these are called columns and each column represents a specific data type (*incrementing* *numbers, string, string, char, date)*. Next to the columns we have rows of data, and each and every row is a singular piece of data. (A table is a collections of rows and columns).

The relationship between an excel sheet and the relational model is very close, except in the relational model, a table has much more nuance. There’s a lot more detail here, we are very-very specific on what we want to store and how we want to store our data. Now, let’s take a closure look at the terminologies of a relational table.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1751185129491/90e2397e-cda5-4c4c-aaa8-602536eb088b.png align="center")

Note: It is important to know the meaning of each terminologies as the below terminologies can be used interchangeably in real world scenarios.

### Column

Each column represents a specific type of data which is also known as constraint.

### Attributes

Another way of talking about columns is saying, my table has these attributes (*id, firstName, lastName, sex, dob)* with these constraints (*incrementing* *numbers, string, string, char, date)*.

### Degree

Collection of all the columns/attributes is called the ‘Degree’. We can call it the ‘Degree of the relation/table’.

### Domain / Constraint

This represents what a column can store (data type). For example, in the *dob* column, we can only store date, in the *sex* column, we can only put ‘M’ or ‘F’ or ‘otherwise’.

### Row

Each row represents a single piece of data from the whole table.

### Tuple

Tuple is used interchangeably with rows. Each tuple has to follow the column constraints.

### Cardinality

Collection of rows/tuple is known as the Cardinality of the table.

### What’s so special about Relational Model?

We have seen so much about the relational model, but what makes relational model special? It's the ability to make a link (relationship) between different types of data. Let’s see about the primary key and foreign key to understand how the relationships are established b/w tables:

#### Relation Keys - PRIMARY KEY and FOREIGN KEY

Primary Key in a essence is a key which uniquely identifies our data. We can see that the *id* column uniquely identifies a row in the table with incrementing number *1,2,3…* but why is this important?

Well, uniquely identifying each and every piece of data means that we can now know for certain that the person with *id=1* is *Abhishek Chandra* and this is how we draw relationships.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1751211995135/b9d990ca-171d-41ef-bc18-5a41bb3ef987.png align="center")

There is something called the foreign keys and its just the other terminology for saying, if primary key uniquely identifies a row of the data, if I am going to reference data from somewhere else we use the concept of foreign keys. In the above image, we can see we have added another table with the information of managers, and also added a column as *managerId* in our *USER* table. We have *managerId* as a primary key column in the second table (Manager Table) and foreign key in the first table (User Table). This helps us establish a relationship b/w the two tables. We can say that *managerId=m1* means *Clyde Bowle* and he is the manager of *Abhishek* and *Ajay* (mapped to *m1* id).

Note: A Foreign Key is a key that references the Primary Key, the unique identifier of a different table, therefore allowing a relationship to be formed. These keys cannot be deleted, if its deleted, it would cause issues throughout the system.

AND THAT’S A WRAP!

## Outro

We started with the older models like hierarchical and network, then saw how the relational model changed the game by making data easier to organize and understand. You also learned the teminologies of relational database model - what tables, rows, columns, and keys actually mean and why they matter.

In the next post, we’ll look at OLAP (Online Analytical Processing) and OLTP (Online Transaction Processing) and how these concepts come together.

**Thanks for reading, and see you in the next one!** 👋