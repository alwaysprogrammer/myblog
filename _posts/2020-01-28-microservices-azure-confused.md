---
title:  "Microservices on Azure: Where to start?"
tags: 
  - Microservices
toc: true
---

Few months ago, I was helping a startup called Abya Courses(name changed) to architect and build educational content streaming application on Azure, which allows users to register, purchase and download online courses. During this process, I learnt about many best practices and patterns of Microservices. In this blog I tried capturing my experience. Hope you will find it useful.

# Is Microservices architecture right choice for Abya's application? 
Microservices and cloud native are buzzwords. Large companies like Netflix and Amazon adopted this architecture and are very successful. However, the big question is Microservices right architecture to Abya's application? 

Deciding when to adopt Microservices is complex and difficult. So, asking critical questions keeping Microservices practices and patterns as guiding principles. I have listed few questions we used to get started.

## 1. What is your scalabality requirments?
**Abya's Answer**: 
*We are plannig to roll out to single region with approx. 5k user base and 20k transactions. System should be able to support monthly growth of 100% new users and 150% new transactions. We are planning to go global in approx. 6 months, so sytem should be desinged to handle latency.* 

**Mapping to Microservices**:
Scalabality is effort required to increase capacity to handle greater amounts of load. Scalability can refer to many different parameters of the system: how much additional traffic can it handle, how easy is it to add more storage capacity, or even how many more transactions can be processed.

## 2. How fast you want to go live?
**Abya's Answer**: 
*We would like to deploy higly scalable sytem which will adopt to change so we will not go live until we are satisified*

**Mapping to Microservices**:
In Microservices approach speed of development is slow to begin with because

## 3. How big is technical team and how are they organized?
**Abya's Answer**: 
*We have 8 developers and 3 admin engineer's. Developers usually build code and provide packages to admin's to deploy the code*

**Mapping to Microservices**:
Dev, Infra and operations team must work closely when building microservices because

## 4. Do we need to use mix of technologies and programming languages? If Yes? Why? 
**Abya's Answer**: 
*Traditionally, we adopted single platfrom strategy to avoid supportability issues and tehnical skillset required*

**Mapping to Microservices**:
Microservices architecture eliminates long-term commitment to specific technology stack allows developers to pick language and framework suited for the service because

## 5. How often are we releasing new features? 
**Abya's Answer**: 
*We take user feedback seriously and try to change or add new features to system, so new feature and changes will be very often*

**Mapping to Microservices**:
Microservices allows developers to change or add new features easily because change or update is local to service 

## 6. Do we understand the complexities of distributed systems?
Designing microservices is designing distributed systems. Regardless of cloud vendors of infrastructure providers distributed systems will have parts that will fail at any point of time.

**Answer**: 

## 7. What level of security is required? Is it uniform across the application?

**Answer**: 

## 8. Do we have customer using different devices like mobile, tablets, desktop?

**Answer**: 