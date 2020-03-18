---
title:  "Microservices on Azure: Where to start?"
tags: 
  - Microservices
toc: true
---

Few months ago, I was helping a startup called Abya Courses(name changed) to architect and build educational content streaming application on Azure, which allows users to register, purchase and download online courses. During this process, I learnt about many best practices and patterns of Microservices. In this blog I tried capturing my experience. Hope you will find it useful.

# Is Microservices architecture right choice for Abya's application? 
Microservices and cloud native are buzzwords. Big companies like Netflix and Amazon adopted this architecture and are very successful. However, the big question is Microservices right architecture to Abya's application? 

Deciding when to adopt Microservices is complex and difficult. So, it is very important to ask few critical questions keeping Microservices practices and patterns as guiding principles. I have listed few questions we used to get started.

## 1. What is your scalabality requirments?
Scalabality is effort required to increase capacity to handle greater amounts of load. Scalability can refer to many different parameters of the system: how much additional traffic can it handle, how easy is it to add more storage capacity, or even how many more transactions can be processed.

**Answer**: 

## 2. How fast you want to go live?
In Microservices approach speed of development is slow to begin with because

**Answer**: 

## 3. How big is technical team and how are they organized?
Dev, Infra and operations team must work closely when building microservices because

**Answer**: 

## 4. Do we need to use mix of technologies and programming languages? If Yes? Why? 
Microservices architecture eliminates long-term commitment to specific technology stack allows developers to pick language and framework suited for the service because

**Answer**: 

## 5. How often are we releasing new features? 
Microservices allows developers to change or add new features easily because change or update is local to service 

**Answer**: 

## 6. Do we understand the complexities of distributed systems?
Designing microservices is designing distributed systems. Regardless of cloud vendors of infrastructure providers distributed systems will have parts that will fail at any point of time.

**Answer**: 

## 7. What level of security is required? Is it uniform across the application?

**Answer**: 

## 8. Do we have customer using different devices like mobile, tablets, desktop?

**Answer**: 