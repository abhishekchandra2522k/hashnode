---
title: "Understanding Databases: Backbone of Modern Technology"
seoTitle: "Understanding Databases: Backbone of Modern Technology"
seoDescription: "Discover the fundamentals of databases and why they are the backbone of modern technology. Learn how data is stored, managed, and used in everything."
datePublished: Mon Jun 09 2025 09:59:14 GMT+0000 (Coordinated Universal Time)
cuid: cmbox6xk7000302jshsll6e8j
slug: understanding-databases-backbone-of-modern-technology
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1749462822262/84612485-c9de-43b5-b346-971e6761b5b1.png
tags: databases, sql, dbms

---

Disclaimer: This article contains very basic information related to the Databases. Please follow the series to understand the Databases and Management Systems completely.

## Why is Database?

Let’s rewind to mid 1990s, when there was an e-commerce boom. Amazon, eBay, Alibaba, Walmart were some of the prominent e-commerce companies and were growing rapidly. Let’s suppose you started an e-commerce company in the 1990s and you also start to get some orders and deliver some products, at first, maybe you will use notebook, pen, paper etc. to track your orders. Eventually, this approach may overwhelm you and you decide - let’s use excel, and track the orders via excel sheets. You would fill in every detail:

* Name of the customer
    
* Product ordered
    
* Quantity
    
* Delivery address
    

It will start to look more cleaner instead of a pen and paper.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1749455043269/bd2a60b2-02c4-43eb-9b3d-367daec98fdb.png align="center")

But, here comes the problem, excel sheet gets a little bit bigger, and we have something confusing that Abhishek has done. You see, Abhishek wants to get some cool sunglasses, so first he orders them and then once he sees them, he doesn’t really like them, so he decides to return them, and a week later, he decided, he wasn’t thinking straight, those cool glasses, those were actually really very cool. So, he decided to order them again but at a different address.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1749455561398/4237ea97-9e47-43ae-84b2-493f130c6510.png align="center")

This gets confusing, as you will not be sure if Abhishek is the same user who returned the sunglasses and order it from Japan or he is a different user all along. As the orders grows, more information, more data, will lead to more confusion. **AND THIS IS WHY DATABASES EXISTS!** to streamline the data storage and data analysis process.

## What is a Database?

A database is a collection of data and also a method for us to access and manipulate that data.

#### Most Popular Databases:

1. MySQL
    
2. PostgreSQL
    
3. MongoDB
    
4. Redis
    
5. Microsoft SQL Server
    
6. Cassandra
    
7. IBM DB2
    
8. Oracle DB
    
9. Elastic Search
    
10. Maria DB
    

Let's look at some of the basic terminologies of the databases world.

**DBMS**: Database Management System

* A DBMS is a software that is used to manage the database. It can receive instructions from us to manipulate the data.
    
* DBMS offers us to create, read, update, delete the data from the database, these operations are often referred to as CRUD operations.
    

**RDBMS**: Relational Database Management System

* A RDBMS is a subset terminology under the DBMS. It is the most useful and popular DBMS such as PostgreSQL, MySQL, Microsoft SQL server, etc.
    

**SQL**: Structured Query Language

* SQL is a way for us to interact with the Database Management System (DBMS). It is a very simple English like language.
    
* SQL is not really a programming language like Python, Java, C++. It's a query language, where its role is to give us the ability (to the people like product manager, business analysts, data engineers, web developers, etc.) to communicate with the databases.
    

### 5 Main Types of Database Models:

1. **Relational Databases**:
    
    * MySQL, PostgreSQL - Used in assets transaction.
        
    * Example: E-commerce website where customers/ users data is maintained.
        
2. **Document Databases:**
    
    * MongoDB, Apache CouchDB, or Firebase
        
    * Data is almost in a document rather than rows and columns. These databases are usually a big document that contains a ton of related information good for scalability.
        
3. **Key Value Databases**: Redis, DynamoDB
    
4. **Graph Databases**: Neo4j, AWS Neptune. Graph model is less used due to complexity but it's really good for the data that is connected in different ways for example social networking websites.
    
5. **Wide Columnar Databases**: This database model was pioneered by Google’s Big Table databases like Apache, Cassandra.
    

## What is a Database Management System? (Detailed)

DBMS is a software that is used to manage our database. It is going to be a supervisor to our database. It knows all of the rules about the way we want to store our data and when we give DBMS an actual query, it knows exactly how to get our data and give it back to us. It’s kind of like our mediator or manager. DBMS is going to enforce very specific rules on us to manage our Database. DBMS will use SQL as a way to talk to us or to understand something. It is also going to make sure that our Database is safe and secure.

What DBMS can do?

#### CRUD - Create, Read, Update, and Delete.

#### MSP - Manage, Secure, Price/Transaction Management

Let’s look at an example to understand DBMS:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1749443469739/1ec23e0b-dd03-4f62-8fc8-8e020adb25a0.png align="center")

Similar to an outlet, SQL (user writing query) acts a as customer to the Database Management System, which takes query (make a pizza) from the user and returns the data (pizza) back to the user. See the below image for more technical representation.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1749444387817/0f3a9af7-9bbc-48de-8cee-4bf6a8b44fe4.png align="center")

### BONUS - DBMS and AI:

A DBMS (Database Management System) is super useful in AI because it helps store, organize, and manage large amounts of data efficiently. AI systems learn from data — and without a well-structured place to store and retrieve it, training models or making decisions becomes chaotic. DBMS ensures that data is clean, consistent, and easily accessible, so AI can process it quickly, find patterns, and give accurate results. It's like the brain’s memory — organized, searchable, and reliable.

## Outro

We've covered what a DBMS is, its key components, and why it's crucial in managing data efficiently. With these fundamentals in place, you're now ready to explore the next layer of database systems.

🚀 **Up Next:** In the next post, we'll dive into **Relational Database Management Systems (RDBMS)** — the most widely used type of DBMS. We’ll explore how data is structured in tables, what makes relationships between them powerful, and why SQL is at the heart of it all.

Stay tuned and keep learning!