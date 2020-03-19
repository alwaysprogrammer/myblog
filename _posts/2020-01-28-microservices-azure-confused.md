---
title:  "Microservices on Azure: Where to start?"
tags: 
  - Microservices
toc: true
---

Few months ago, I was helping a startup called Abya Courses(name changed) to architect and build educational content streaming product on Azure, which allows users to register, purchase and download online courses. During this process, I learnt about many best practices and patterns of Microservices. In this blog I tried capturing my experience. Hope you will find it useful.

# Is Microservices architecture right choice for Abya's product? 
Microservices and cloud native are buzzwords. Large companies like Netflix and Amazon adopted this architecture and are very successful. However, the big question is Microservices right architecture to Abya's product? 

Deciding when to adopt Microservices is complex and difficult. So, asking critical questions keeping Microservices practices and patterns as guiding principles. I have listed few questions we used to get started.

## 1. What are your scalabality requirments?
**Abya's Answer**: 
*We are plannig to roll out to single region with approx. 5k user base and 20k transactions. System should be able to handle growth of 100% new users and 150% new transactions monthly. We are planning to go global in approx. 6 months, so sytem should be desinged to handle latency.* 

**Mapping to Microservices**:
Customer clearly communicated the qualitative growth scale like users and transactions which are tied to overall product. This can be achieved by both Monolithic and Microservices architecture. 
But why microservices? 
With monolithic service we must scale everything together by running many copies behind a load-balancer even though different modules have conflicting resource requirements. Microservices allows us to scale each service Independently. 
Abya’s transaction growth rate is expected to 150%, so scaling services that are part of transaction (like order and payment api) makes more sense than scaling entire system. This will allow us to run other services on smaller and less powerful hardware. 

## 2. How big is technical team and how are they organized?
**Abya's Answer**: 
*We have 8 developers and 3 admin engineer's. Developers usually build code and provide packages to admin's to deploy*

**Mapping to Microservices**:
We can take advantage of Inverse of Conway’s law * organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations*. In order to deliver value faster to your customers, teams must be organized in a way that allows them to own what they’re responsible for, end to end. This is what Amazon calls “you build it, you own it,” or “build and run” teams, responsible for development and production throughout the entire lifecycle for a chunk of software.
```html
{% raw %}<img src="{{ site.url }}{{ site.baseurl }}/assets/images/TeamOrg.PNG" alt="">{% endraw %}
```
Abys's engineering team is small and it is easy to re-organize.

## 3. Do we need to use mix of technologies and programming languages? If Yes? Why? 
**Abya's Answer**: 
*Traditionally, we adopted single platfrom strategy to avoid supportability issues and tehnical skillset required. However, we would like to reevaluate that decesion*

**Mapping to Microservices**:
Microservices architecture eliminates long-term commitment to specific technology stack allows developers to pick language and framework suited for the service. 
Example: If specific services data can be best expressed without relationships and need fast writes, NoSQL like CosmosDB will be better choice.

## 4. How often are we releasing new features? 
**Abya's Answer**: 
*We take user feedback seriously and try to change or add new features to system, so new feature and changes will be very frequent*

**Mapping to Microservices**:
Microservices allows developers to change or add new features easily because change or update is local to service. Releasing small changes and verifying thier quality gives teams the confidence to release features rapidly. Weakness of monolithic development is that releases often become large, coupling together disparate features at release time. 
 
## 5. Do we understand the complexities of distributed systems?
**Abya's Answer**: 
*We have not managed complex distributed systems so far, however we are okay to learn and skill people on what it demands*

**Mapping to Microservices**:
Designing microservices is designing distributed systems. Regardless of cloud vendors of infrastructure providers distributed systems will have parts that will fail at any point of time.

## 6. What level of security is required? Is it uniform across the product?
**Abya's Answer**: 
*Payment data like credit card information, PII's like email id, mobile number*

**Mapping to Microservices**:

## 7. Do we have customer using different devices like mobile, tablets, desktop?
**Abya's Answer**: 
*Yes. We have users accessing our content from different formfactors like mobile phones, desktops, tables*

**Mapping to Microservices**:

## 8. What are your go live timelines?
**Abya's Answer**: 
*We would like to deploy higly scalable sytem which will adopt to change so we will not go live until we are satisified*

**Mapping to Microservices**:
In Microservices approach speed of development is slow to begin with because