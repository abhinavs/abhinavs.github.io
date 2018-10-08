---
layout: post
title: How to engineer an MVP
excerpt: "A few things to take care while building your MVP"
tags: [MVP, StartUp, Product Development, Engieering]
comments: true
---
As per wikipedia, MVP or Minimal Viable Product is a product with just enough features to satisfy early customers, and to provide feedback for future product development. 

While it's a known paradigm in lean startup philosophy, however I have seen a lot of product engineering teams struggle to create one which can yield valuable learnings quickly. Here are some of my recommendations to product and engineering teams to help them create a good MVP.

### Before you start
* Though it is important that PMs think unconstrained while trying to build the product, however EM (and/or senior engineers) in the team should be consulted before MVP spec is locked down
* PMs should clearly communicate to engineering team the vision of the product and should list down set of hypotheses they are trying to validate from this MVP - this helps engineering team understand set of non-negotiable components and visualize future requirements
* Engineering team should also ask PMs to list down a couple of directions this MVP can take - through this engineering team can understand components which need flexibility and will change soon after.
* Remember MVP is principally a learning product, and iteration speeds will play an important to adapt product for users’ needs. Engineering team should find out time duration PMs will take to validate initial set of hypotheses - this will play a key role in deciding how much hacky/non-optimal code will be okay. If PMs can validate hypotheses in a couple of days, before team is required to work on V1 - team should likely not hack much or build code which can be iterated for V1 quickly. However if validation time is large, engineering team can enable PMs with quickly built MVP, and find time to build V1 while PMs validate the solution with users.

### Building
* Engineering is all about balancing the trade-offs and so is engineering an MVP. Good engineering teams know that right problems need to be solved at right stage, and solving them prematurely or too late can be fatal. Example - building generic systems or scaling them prematurely can waste a lot of important time, while continuing with non-optimal systems or processes for long can negatively impact your iteration speed.
* Though it is outside of scope for this document to define what is a good hack and what is a bad one, try to avoid bad hacks as much as you can. Example - hardcoding keys in client is a bad hack.
* Contain your hack. Spend time in finalizing contracts, input and output parameters - this gives you flexibility to implement API/module non-ideally and fix/refactor it later on without a need for large scale refactoring. 
* Document your assumptions clearly - most of the hacks are actually nothing but assumptions which may not stay valid later on - document them, and share them widely in the team so that these hacks can be fixed at right time.
* Don’t automate from day one, but if you are spending 1+ hour as a team everyday in doing something manually, automate (at least partially) if you can. 
* Backend and frontend should settle on API contracts as soon as they can, so that frontend team can stub API calls and develop in parallel. However, integration between backend and frontend should happen as early as possible - this avoids fixing mismatch of assumptions at the last moment.

(This post is WIP (work in progress) and I will keep it updating with more recommendations)