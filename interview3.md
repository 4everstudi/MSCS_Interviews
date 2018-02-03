# Anonimous Interview 3

"A" for Interviewer statements

"B" for Interviewee answers

Interview was made on 10.07.2017, face-to-face

===

A. Here we go, okay, so back to the questionnaire … if I got it right you’re at the moment at the start of your journey to the microservices.

B. Yes, we are. Start is a relative term, but in terms of completion we are closer to the start than we are to the finish.

A.	Okay so how far are you guys?

B. Well that’s a tough question because there’s different teams in our development organisation at different paces. Speaking for myself, we started down this journey 2.5 years ago, maybe even three years ago. When we first started, microservices weren’t being discussed quite as openly as they are now, they just weren’t quite as big. About a year into it microservices was all the rage so I started doing quite a bit of research on it, and dabbling in microservices and working on a framework to enable microservices in our product. Over the course of the past year there’s been some reshuffling in priorities and so we now have two efforts to get our product cloud enabled, one starting from scratch, one team is starting from scratch and our team is looking to decompose the monolith and turn it into microservices and so at this point we are kind of restarting and starting from scratch. We have a microservices framework that’s going in, being completed in the next month and a half that makes use of a eureka directory service and a dispatcher from service side discovery. Right now we have one microservice that is nearing completion and will be production ready this year and then presumably others will come along quite rapidly.

A. Great. So did I get it right that from these both teams the most appropriate output was from the team that started from scratch?

B. Yeah the team that started from scratch. They have nothing production released yet at all. But it’s easier to start them … it’s a tough answer because i’ve read enough literature and some argue that starting from scratch is sometimes more difficult than decomposing the monolith because you can get stuck building artificial microservices. But they are building microservices [inaudible] to start with .. the foundational ones then build applications on top of that.

A. Okay so then lets move on to the first question actually. The first statement about he seize of microservice. You mean there’s no formal condition at all?

B. Correct. And I think that nothing in the world is black and white, especially in this space if you were to tell me as a rule of thumb that microservices should not be more than 10000 lines of code then I’d say ‘yeah that might be a good rule of thumb.’ But it might vary.In this case, 10-100 lines of code that would be a very useless microservice. I can’t imagine much production quality software that can be done in 10-100 lines of code.

A. Yeah right. So maybe if you used 10 frameworks in your ten lines you could achieve this but that’s not a goal?

B. Yeah it very well could be but that starts getting into the area of how much should a microservice stand on its own versus needing to incorporate other packages. That’s an interesting topic in and of itself. I try to write mine as stand alone as possible. I’m not saying I reinvent existing software but the less dependencies you have the better you are.

A. Yeah right. Okay the next question, which is a little bit funny regarding these pizza teams … [inaudible]

B. I always chuckle when I see that. You know that’s a big agile topic. I think the intent of that statement is probably true that you want microservices to be developed y smaller teams because if your team is very large either your microservice is too big and its no longer a microservice, or they're just highly inefficient. But I think yeah a small team is much more suitable to a microservice  and I think the best practice out there is that the microservice is developed by the same team, going down two questions below, that’s definitely best practice.

A. So another question will be what’s the size of a small team for your definition?

B. Could be as small as one person. I don’t think one is defined as a team. Right now our service framework, we’ve got one or two people working on it, I think that’s legitimate.

A. Yeah. What will be the maximum?

B. It’s hard to provide the maximum. What’s optimal? I would think … you know …. six people? But that’s just opinion. 

A. Okay, yeah.

B. That would be on the upper end of optimal.

A. Yeah right. Architecture should avoid synchronous communication. Your statement was clear. And the best way to you is to design in asynchronous way.

B. Yeah, yeah. Asynchronous, and more specifically, I recently attended the Go-To conference in Chicago and listened to a presentation on event driven. When the presentation first began I was highly sceptical and by the end I was a believer that if I were starting a microservice solution from scratch, I would utilise event driven architecture that is inherently asynchronis, to begin with.

A. Yeah but in my opinion there are still some services like for example, a translation server. There’s no point to design it in an asynchronous way. Or what do you think?

B. Well it depends. And this goes back to event based. If your system, and it may not be feasible to be completely event based, but if your system is event based and you fire an event that needs some response you’re not tied into the nature of who's responding. you're tied into someone responding thats fulfilling the contract that your event requested.

A. The next one: microservices should be maintained by the team that developed them.

B. Yes.

A. Okay that’s not so easy to achieve in my opinion. Not for every organisation at least. Because some teams will be put together only for developing one particular microservice then move on to the next project. Then its hard to decide who should maintain it in the future.

B. I think that gets into best practices. I think the industry as a whole is changing quite a bit right now and on this particular point. I was at microsft a couple of months ago trying to get an understanding of their transformation. And their teams that are transforming and their microservice based teams are absolutely following this ‘team develops it, team maintains it, team supports it’. You know, the trend is for any given team someone has the pager and is on duty in case there’s an outage. One person is responsible and that rotates across the team. You don’t have some larger support organisation that’s handling this and you only get called in certain situation the teams that develops it is the team that supports it.

A. Yeah exactly. What do you think about the requirement … that microservices require also the adaption of the organisational structure.

B. I think that’s very important and that’s something we’re struggling quite a bit with right now. Both organisation in the truest sense, you know, reporting structure, but also organisation in terms of just mindset, and how you develop something and the whole development process, the building and deployment process. It’s a significant change. You know, as I’ve gone through this experience of learning more about microservices I came up with the opinion that devops was born out of necessity, because if you’re developing a microservices without a devops process you'd have a nightmare situation. Whereas before you have a problem you go debug your application, and you can see step through and see what’s going on and you know how to build your application. With microservices being disconnected processes and products, debugging, building and deploying would become nightmares, so I think devops may have been largely born of out necessity.

A. How are you guys going about it?

B. Well it’s interesting I just came out a meeting before this one talking about how our service framework is going to follow a devops process using gitlab and using automated build and tests and making the build artefacts available on our monolithic application and trying to figure out to adapt the two process as we move from monolithic to microservices.

A. Yeah that’s the technical side of the question but about the organisation, its hard to imagine this shift to teams who are self-responsible for the output within an hierarchical organisation.

B. I’ll be honest, we haven’t really made that transition yet. The team I’m working with on the framework we’re one of the first ones and there was one other microservice team but we are trying to figure this out because as more teams come on and start trying to develop micorservices we need to have a template or a model in place that they follow so that we can add some organisation to the chaos that could ensue.

A. Okay. Yeah. In my opinion that’s one of the biggest challenges. The changes to mindset to prepare all the environment for microservices to adapt the processes.

B. Yeah it’s very hard, and with an organisation as large as ours and the fact that we still have a product today that we need to build and sell and make money on, it’s not like you can just switch over all at once, you still have to remain in production and somehow migrate to the newer process.

A. Yeah you have to design a kind of transition process.

B. Yeah.

A. So the next one, regarding the database for a microservice.

B. Yeah, I firmly believe in that that’s absolutely the best practice. Anything you read talks about this. And we struggle with that a little bit and I mention this down further bellow, but the nature of a PLM system with many different applications, i’ll call them, built on top of a central database and using the data across different solution it’s very hard and I think we struggle a little bit with how to adapt to a microservice architecture to our monolithic database. There’s differing opinions about how to approach this, and the debate rages on even right now still. But as written I do believe that microservices should be black box with their datastore managed by the microservice and not shared with any other microservices.

A. From my previous interviews, all the statements were clear, all of my interview partners have took this journey from a monolith to microservices and this monolithic application had one single database in the background but the statement was clear that everything that will be rewritten as microservice should rely on their own database so the integration of databases is an absolute no go.

B. Yeah absolutely, and I think you have to go through the microservice interface which is the contract. I don’t know how much you’ve talked to helmut about the project he’s working on but it came to me that we’re approaching that project with a microservice mentality and we’re approaching it in a very modular way first so that it can become a pure microservice in its own process base. And part of the challenge with that early design was getting helmut and others in the mindset that the data for their solution should be stored in its own data store and not merged in with the rest of it and after some discussions I think helmut definitely understands the vision now so its just a learning and transition process.

A. Yeah in my opinion again, that’s also a change that affects almost everything.

B. Yeah.

A. And there’s no single place where you can store all the stuff. You have to design it from scratch and rethink all your sub-systems. 

B. This is tough area. I’ve done a lot of research and asked experts in the industry and there’s no easy answer to it. Everyone agrees what the right approach ideally is but arriving at that is not always easy.

A, Okay. Individual microservices should match DDD bounded context?

B.Yeah. I think that’s just part of the microservice design philosophy. Establish your boundary context, your domains and develop and understand your domain. That conference I was at I went to a full day workshop and we went through an example when we took a seemingly simple product and tried to define your domain and do a domain analysis and try to derive your microservices based on that.

A. What do you think in general about the managing of design and its implementation - if you’re going about it and implement it right how will be written in a book. I have heard some opinions that can be really fast and expensive stuff.

B. Yeah, I’ve been through courses on domain driven design. I really haven’t had a chance to utilise it from scratch, it’s much harder when you’re trying to decompose an existing product because your domains have already been established whether they’re right or wrong. That’s the difference its a quite different conversation but they’re already been established so trying to re-establish them is very difficult. You know, I equate domain driven design to a bigger version of trying to establish your classes if you're developing in C++ in Java, whats your class breakdown when you're doing your design: similar kind of problem right?

A. What about the decisions which teams are ables to make. For example to choose a technology for a microservice, the programming language and so on.

B. Within reason I think micro sevices provide the autonomy for teams to make their own decisions. The reason I say within reason is that we’re in it to make money and you can’t have a team go off and pick some crazy language that doesn’t really fit into the built framework that you have and no one else in the organisation can support it that would be silly. But you know, within reason it does prevent them and gives flexibility to teams to do things in their own way. As far as using 3rd party, open source technologies like that again within reason as long as the open source is architecturally appropriate and can get through legal approval this provides teams the autonomy and I think this may be one of the biggest single values of this. Whereas today we have central governing bodies for architecture today teams will be able to govern themselves, and you know, they're creating their own product they’re kind of making their own great solution to their own mess and that only impacts them. Today in a monolith, if someone goes in and puts in a piece of code that has negative impacts across the whole monolith, that’s why we have to have a central governing body. Tomorrow microservices I think free the set up a little bit.

A. Again from my previous interviews, do you know <Company>? The European <...> company.

B. Yeah I do.
A. I’ve had an interview with their chief data engineer. And the statement was ‘the only thing which will be managed centrally is the design of the API, the rest is for the teams’ responsibility … which technology to take, which database, and so on’. Of course, they have a blacklist of unsafe technologies, but in general that’s the policy.’

B. Yeah and I think that’s the appropriate approach.

A. Yeah but again, the transition to this state is not so easy

B. There are a lot of things folks don’t think about. They go off and pick up some language and they want to utilitise it but then this language is supported on one of the platforms that we support so we’re on many, many different platforms. Solaris, Windows, Linux, IBM, AIX and so on, you know a lot of the things we look at are not supported on Solaris and AIX. And we have to take that into consideration.

A. For sure. And these kind of decisions should consider the requirements.

B. Yes.

A. Okay. microservices should be dynamically discovered.

B. Yes.

A. Period?

B. Simply yes. Yeah.

A. Okay. Fair enough. Microservices should be small enough to be rewritten within one sprint. 

B. I disagree with that, I think that’s not a feasible statement. 

A. Should I say what the others say about it?

B. Yeah what do they say?

A. Again, from <company>, they say it’s ‘clearly yes’. Strongly agree on this.

B. Oh

A. That’s a kind of policy … official policy.

B. I think some of that comes down to what do you mean by ‘rewritten’?

A. Rewritten from scratch.

B. So if I have a service written in Java, if I want to port it over to different language, or do I want to rewrite it from scratch? And take into account completely different source and logic and whatever and all that [inaudible] interface. And what is your sprint duration? Many of the teams round here are operating 2 week sprints, which I disagree with.

A.So I understand it in the following way: each team has to describe a microservicee API using an open API standard. It has to submit it to the API guild for approval and this specification shall be tiny enough to be implemented in whatever technology or programming language in one sprint of two weeks.

B. Yeah I mean I think it comes down to just trying to define the size and complexity of the microservice. If we could do that, that’d be great. We do a lot of complex stuff around here, a lot more than an E-commerce site. So…

A. Yeah, understand. But again, it depends on the definition of your bounded context. There’s no requirement to cover the whole context with one microservice but you still have a possibly to split it up into multiple microservices.

B. Yeah I agree, I totally agree. I think the generic purpose of striving for nice, small, tight, single purpose microservices is absolutely a good vision.

A. Okay it’s getting serious. Question number 2 - what is your definition of microservices … yeah just from your experience.

B. Yeah, you saw what I wrote there: ‘Individual component of a module that can be deployed on its own, manages its resources on its own, and has a clearly defined interface.

A. How are you going about the definition of interface for microservices?

B. You mean, conceptually, or physically?

A. Both.

B. You’re asking me what am I calling on interface or how do I define an interface?

A. How do you define it in your team? How do you keep track of changes and so on?

B. Well this is currently an open topic. Right now, we’re defining interface using swagger. But in terms of service interface versioning and what it means to rev an interface there’s still some debate there whether the URL of service has the interface in the URL or whether … how we reserve it. So we’re still debating that a little bit.

A. Yeah.

B. I tend to believe putting in it the URL is more stable, but it means more work for folks using that interface.

A. But you are trying to stick to the API service concept?

B. Yeah.

A. Good.

A. So the next one: the third question is already covered, more or less, I think …. the conversion from monolith systems…

B. Yeah, I think we’ve talked about that a lot.

A. Yeah.

A. What are the 3 most important challenges? You have written ‘where to begin’.

B. In your team … it seems quite like a trite answer but it really is. It’s an important thing. How to begin. Given it’s a mindset change, it’s an organisational change, that’s what I was talking about ‘where to begin’ - how do you identify these areas that are modular enough to break out? That’s a little bit unique to our problem Our monolith is rather entangled. Yeah. I guess the mind shift getting developers to rethink and understand and I guess abandon some of their preconceived notions. Performance is very important in our products, as in most products. But it’s just the different nature of our products and I guess so many naysayers who say microservices will never work, ‘you ever heard of interprocess communication? Moving data between processes is just not feasible, it’ll never work.’

A. Yeah, it’s just I’d never thought about it - how to start? Interesting

B. Yeah it’s just that given I was on a team. We started a few years ago and never really completed any real concrete deliverable. Things changed. It just makes it - how to start is a real … big deal.

A. How to identify areas of code that are modular enough to break out? It depends. About the modularity of your code. For sure, you are documenting everything. How does it look like currently when you’re starting to develop a feature for the product? Are you going to create a kind of model first? In any way, UML or something? 

B. It depends. If it’s a completely new feature we have a bit more flexibility in designing it in a modular way from the start. Thats really not the case often enough. Typically our features cut across many aspects of our system. and its a series of changes to different areas. And that makes it much, much more difficult. If we’re starting with a large new feature that can be modularised from the beginning, you know, start with woman driven design, establish your contexts, I think it makes much more sense from a microservice perspective. But trying to decide what pieces of team centre to break out into microservices … its just, its challenging because we don’t unfortunately have really clear interface points to our areas. I’ve read numerous books and articles that talk about how in many cases its best to modularise your system first and then go to microservices. Don’t try to do it all in one go because then you’re just taking on too much uncertainty.

A. Alright. What do you think about the statement that a move to microservice requires … can be described through the complexity which moves also from within the application onto another level … onto a level where the communication between microservices is settled.

B. Yeah, it’s interesting you talk about that. Because on one hand microservices can simply your system because now you have very clear models and they only communicate through these very well established interfaces. On another larger aspect, going to a microservice architecture is much more complicated. It’s what we called back many years ago ‘a distributed system’ and distributed systems are inherently hard. Again I was at that conference and one of the guys was presenting on a real life system outage and talked about the series of events that led up to it and what they had to do to resolve it and he kind of joked and said having an outage or a significant problem or an outage on a microservice turns what used to be a bug into everything becomes a murder mystery because you're trying to figure out whodunnit. Which microservice in the organisation is at fault? It’s not as easy as  just going and debugging and stepping around. Everything’s distributed so it puts a lot more emphasis on proper logging, proper monitoring and health check and analytics and telemetry.

A. Where are we at?

B. I think we’re on 3 or 4. 4. 

A. Oh right, yeah, the challenges. And the last one, significant mind shift. Mentioned already, multiple times. Oh right, the fifth one. Where are microservices hosted in the organisation.

B. For my particular team, we are focussed on on-premise. We’re an on-premise product. But we’re currently going through what we call a lift and shift process. Where we’re taking our product, moving it to the cloud, then shifting pieces to being more cloud-friendly via microservices. That’ll be done with AWS this year. Right now we’re on-premise.

A. What do you mean by ‘on-premise’?

B. Our product is an installable product. So a major customer would buy our product, receive the software, install it on their hardware, manage it.

A. Okay, so it is not hosted on our hardware?

B. No. We’re moving to that - that’s what we’re calling lift and shift but today we’re on-premise and that’s actually been one of the things keeping us from adopting microservices on a more aggressive basis because some feel that microservices are much more aligned to cloud hosted environment and doing non-premise microservices makes customers’ administrative burden much more difficult. And that’s been some of the roadblocks we’ve been dealing with.

A. But also if you develop on-premise software, they have to install it, different customers have different infrastructure requirements and so on. I mean to manage the whole configuration for all the possible combinations is a challenge if you go this way for an on-premise product.

B. Absolutely and I totally agree with that, but at the same time, since we have to support on-premise for the foreseeable future should we let that be a roadblock to not adopting a microservice architecture? If that’s the case then we’ll never move our product to a more modern architecture?

A. Right. What’s the hurdle on that? Who are your customers?

B. Our customers are, you know, Ford GM, BMW, Volkswagen, Boeing. Any major manufacturer that you can name, there’s a good chance they’re our customer.

A. I assume they are not always agreeing to use the cloud service for such stuff?

B. Correct. None of our big customers right now are hosting our product in the cloud. Zero. We’re currently working with a large aerospace customer, who, I don’t know whether it’s been announced, can’t say, managing their team centre environment in the cloud. That’ll be done in the next year.

A. Okay. The next question. You said we have no production microservices so we don’t yet have metrics but yeah … let’s keep it general then. In your eyes, which KPIs are … important?

B. I guess it comes back to what do we think the return on investment for microservices in general are? That would be faster time to market, with more features, more stability in our system.

A. Not necessarily.

B. Well for our product I think it will. That will come more through modularity than through microservices but I’m tying the two together. Today, in our system, you make a change in one part of the product and it breaks over something far away in another part of the product and so tomorrow with a microservice if its a black box and that black box is fully testable, I can have confidence, that even the smallest change I can test and ensure the system will hold together. And that comes from testability, well established contracts and no one using my service in ways that I’m not aware of. So I think you get a lot of those values. I think that’s a real important thing. And we get customers on one version of our product, versus many different versions that we have to support, so our support burden goes down.

A. Yeah, right. Back to challenges. I have a question: what about security? 

B. What about it?

A. Is that a challenge in your eyes? Or is it something that could be underestimated?

B. Well from a microservice perspective, purely, no more than with our existing product. We’re working on that right now where we have to do authentication. Any microservice call that goes through our system, has to be authenticated to ensure that the caller is who he says he is and so I don't see that as many significant burden more than we have today. Now in terms of going to the cloud, that’s not microservices, that’s a cloud security issue, that’s, yes that’s huge but thats not inherent to microservices that’s just the cloud in general. 

A. Okay. The next one ‘how does the life cycle of microservices look like?’

B. Yeah that’s a tough question because we really don't have production microservices. You know, the two teams that are working on this, from concept you have a problem, we have a set of requirements, determine whether microservices are the right architectural  technique for this is one of the first thing we ask and from there we start going into a little bit of domain design, trying to ensure that we establish the domains for that particular feature and then define the microservices and then the interfaces.

A. What will the goal … the idea for the case … how should I express it .. that’s maybe more about 7B, regarding the environment, and the use for the development because, again, the example from <companyName>, their goal is to restrict it for only one production environment, so all the updates and fixes should be rolled out directly to the production. They’re trying to achieve this.

B. Yeah, that’s a really hard question for us. I can give you the textbook answer, but for us since we’re not really deploying to a cloud with our microservices since we’re currently in an on-premise mode, it’s completely different. We’re not hosting any software users run in, we’re developing software, we host internal systems that folks can test with, people can play with but when we release our software, customers download it, install, they go through the same kind of thing, they typically have a dev environment, a dev and test environment, where they validate the new install, ‘Yes, this is good’, then they roll it into production. But in terms of when we go to the cloud, I don’t have a good answer as to how many environments we’ll have - I assume at a minimum three: dev, test and prod, or dev, staging and prod, call it what you what, but three.

A. Okay. The next one. How do you manage the microservice configuration? How are you going about it? Because many people say already that such tools like puppet or ansible (?) are kind of outdated.

B. Yeah. This is a topic of raging debate around here because if I had to choose right now to go for a strategy I would look at a solution such as Kubernetes and manage our microservices as containers, but given our system is a monolith and microservices are a very small part of it right now, I can’t put in Kubernetes, because its a significant hunk of software that complicates our architecture significantly so I can’t justify it. And so with that, Cubrinett’s, being our long term vision, I have to look at something that’s a little more lightweight, a little more tactical to start with. And just last week we started looked at PM2, process manager, as a way to start and manage the stability and the failover (?) of our microservices. Not as containers, necessarily, but as processes. So when you install our project, we install PM2, and PM2 will start up the microservice framework and then the couple of microservices we have … make sure they continue to run and we’ll have a dashboard to monitor their health and their running. That’ll give us the time to build up and move more towards [inaudible] containers and start incorporating these technologies into some of our products as a whole.

A. That’s interesting because you are maybe the fourth person who is talking about Kubernetes. I haven’t had a chance yet to take a look at this tool. What’s this?

B. Think of it as a container orchestration solution. It allows container start up, it allows auto-scaling, so if one of your services or one of your containers is getting pounded by a bunch of users, getting over utilised, it will spin up more containers on other hardware that’s in its pool of availability and it manages all that and when that service load declines it'll wind down those [???] containers so you’re optimising your hardware utilisation. So that’s one aspect of it, and it also handles, you know, when a new service comes in, and upgrading from version 1 to version 2 of a service, it’ll handle ramping one down and ramping up the new version, things such as that. I don’t have a lot of practical experience of Kubernetes. I’ve read some of the overviews and I know its on our list … its the primary contender for the solution we would want to use, but when I went to use it was so large and heavyweight it was really not a very good on-premise solution for us right now.

A. Okay, because another aspect that others mention often about Kubernetes is that this … platform … how should I call it … potentially can allow to design your system in a Cloud infrastructure agnostic way.

B. Yeah, you’re right. So if I were developing a system and I were just going to use let’s say Amazon’s AWS, I wouldn’t necessarily need Kubernetes. AWS probably provides enough infrastructure that I wouldn’t need to use it, right.

A. Sorry, and that’s exactly the problem right now for Talando, because they’re experiencing right now this window log (???) and they would like to try the Google Cloud but they cant’.

B. Yeah. And that’s where Kubernetes helps you solve that. There are several competing solutions out there, some pure container based, some not. 18 months ago we looked at a product called Pivotal by Cloud Foundry … it was okay. Again, it was super heavyweight. I played around with Microsoft’s service fabric solution. It’s actually a very nice solution, very very useable. It’s tied to processes, not necessarily to containers, but its really closely tied to .net and to Microsoft in general, so its not mature enough, I don’t believe, in terms of using it on Amazon or Google, or something else, so that’s why we kind of stayed a little bit away from that one. But Kubernetes seems to be the industry leader right now. I believe it came out of a collaboration with Google and someone else, I can’t remember. The other one that’s getting a lot of attention is Apache Mesos, it’s a direct competitor to Kubernetes.

A. Yeah. Because in the prime work of my masters thesis I also have a practical part, so at the moment I'm trying to figure out what will be an appropriate scenario to implement. I will implement it with the Amazon cloud … yeah … that’s the question. A lot of different tools provided by Amazon itself. A lot of different open source tools. And I just try to figure out what are the current challenges, what will be an interesting pattern or something to implement and just make a demo.

B. Yeah. Another aspect of this space, I don’t know if you’ve come across it yet, but you might want to look at is what’s commonly referred to as server-less computing.

A. Yeah, exactly.

B. And more practically, it’s Amazon AWS lambda. I’ve researched those a little bit over the past few months. At first I didn’t get what problem Lambda was trying to solve. Now I get it, I’m not quite sure how we would adapt it to our particular solution but it’s interesting. I saw a presentation from a customer, not a customer, a solution, a cloud-based solution. I can’t remember the name of it. But by using AWS lambdas, the lambdas are so small and getting such minimal usage at this point that they’re able to host their entire product in the cloud for the past 18 months for free. Because Amazon only charges for your lambdas once you reach a certain threshold. This was an online research site, a book site. You know how sometimes you can go online, take a training course and what not? it was that sort of thing. And they were doing it for free. Without any hardware costs, so that was pretty interesting.

A. Yeah, so I have also already tried lambdas. I tried to develop a kind of Alexa skill (???) that was really easy stuff to just write your code and upload it. The actual problem is when you have a complex product and then you have to access your data and lambda will work perfectly with the Amazon services, but when you have something else, then your lambda will grow really fast.

B. Yeah so that was my exact concern. I view lambda as basically functional programming rather than anything objectory in it. And so I cant imagine having many many different functions up in the cloud as lambdas. That would be a little too sparse, too shattered, I’ll call it.

A. Yeah, at the moment, I can say lambdas are a perfect extension for amazon services which make it a whole more flexible, but as a stand alone solution, not yet.

B. Okay.

A. But differently, also, many people say that the lambda will come in about two years, that will be the hot topic.

B. Yeah, I think it is, I think it’s an emerging topic. 

A. Okay. 10 minutes and 3 questions. How are your microservices coupled within each other? That’s again the topic regarding the communication, regarding message brokers, message streams and so on. How are you going about it? Which tools are you using as message brokers?

B. Well right now, we’re not a message broker based system. We’re a direct synchronis call. Our goal is to absolutely go to asynchronis calls. I don't honest know how to take us from where we are today to a message based, event-based system, in the next several years, that would be really a huge effort, so I’m really not entertaining that. But today we’re making direct synchronous calls. And we’re doing that by making a straight restful call to a single known endpoint. And that endpoint goes through our dispatcher that uses eureka to look up the implementing endpoint and routes the call onto that. 

A. Okay.

B. Just a basic directory service solution. And the value I see from starting now gets us into the microservice game. You have a single endpoint, you know. This gets into the discussion of client discovery versus server discovery. I understand the pros and cons of both. I think its simper to start with server based discovery so that if I have three people calling microservices they don't have to know how to call eureka and look up the service and blah blah blah. They make a straight restful call to the known URL endpoint and it gets delivered.

A. Yeah. I mean. It’s again the question about the architecture of your application. Again about the mindshift. How you design the whole stuff. Because the idea of microservices in my eyes, a microservice makes … performs some stuff, delivers an output, puts it into the queue, message broker or something else and then the next one comes. And of course if you have a monolith with so many dependencies, again, about the transition, it makes perfect sense to set it up as a synchronous communication to just mirror the previous architectural style and not make that many errors by redesigning the whole from scratch. Or…?

B. Yeah, I could not agree more and I think this question, or at least this part of the discussion kind of touches on number 11, or at least how I interpreted that question, data integrity: dealing with transactional integrity versus two-phase committed, versus eventual consistency. In our system it’s a very hard problem. Right now, we have complete transactional integrity and if you have multiple microservices envolved with modifying data that can be viewed as something of a larger construct, it’s very hard, you need to have consistency between that. And I think that’s where messaging systems I think make the situation even more complex.

A. Yeah that’s actually the question I’m struggling with, because each microservice has to have its own database in the background, has to perform some task. Which kind of data will be kept by the microservice itself? What will be posted and lands into the warehouse, and, I don’t know, just, I couldn’t find any appropriate example of, say, a workflow implementation of the microservices. And how can you decouple this switch between different demands and contexts and how can you think about the databases with the primary keys and so on? How can you implement something like this within the microservice context?

B. Yeah, I think it’s a complete paradigm shift. Let’s say we take a trivial example where you have five different, I‘ll just say operations, within the system. When you hit the button that creates something, five different things are happening in there that are ultimately creating data, if all those things need to work together as a unit, the typical way is you wrap them with a transactional boundary. Transaction begins, does the five things, either transaction commits, or transaction aborts, right. And so in a microservice world, if you think about each of those five things, storing the data in their own data store, it’s like ‘How in the world do you get all that organised?’ It’s just … you know … It’s one that I struggle with and I don’t have a great answer. I’ve researched everything from eventual consistency using the events mechanism right. Some customers are relying on the event message broker to store those events so they’re re-playable in terms of failure. I think that’s a very hard thing to imagine in our product’s domain. This is a tough one, this is a very tough one. I think banks and other financial institutions where you’d think they would be transactional, they’re actually relying on eventual consistency and I think it takes more effort to ensure those services do become eventually consistent and they don’t just drop information, and I think that’s getting by. I think.

A. Yeah I would like to implement something like this, at least as a concept for my thesis. Just a solution proposal for this problem.

B. Yeah I think that would be a very good slash interesting thing to do. I think that would carry a lot of weight for your thesis because I think this is one of the larger challenges for this architectural approach.

A. Okay last question. Real quick. Regarding the patterns.

B. Yeah that’s a hard one. I mean I could go to the book and pull out all the different patterns but you could do the same thing. I don’t know that we are using any hard, fast patterns. You know I mentioned client side discovery versus server side discovery. That’s one of the patterns where we’re actually doing server side discovery. I guess the directory service pattern in general we’re using. Yeah, I’d have to go back and look at them. I must admit that when I develop my software I don’t tend to think about patterns directly. I know the patterns, and I tend to use them, but I don’t really use them by their hard, fast name. It’s just the concept I’m aware of and I tend to do that. Some people are pattern-mongers: they can tell you the name and the principles of every pattern, and they can tell you every pattern they’ve used. I can go through my code and [inaudible] tell you the patterns that are there, but it’s not like I track the patterns we use. 

A. Yeah, but the patterns are extremely important for someone who's just starting with this stuff because its a kind of formalised knowledge that’s already available on this. 

B. Yeah, you’re right. I’ve read this stuff, the whole 12 factor apps and I’m sure there’s some design patterns by name that we’re using relative to aggregated logging because I think that’s a whole other aspect of microservices that is interesting. You know whereas a monolithic it can log to a file, someone can look at that logged file and see what is going on. With microservices being distributed, how do you get the big picture of system behaviour without an aggregated log solution?

A. Okay. Great. Then I think we are done for today. 

B. If you have followup questions, shoot me an email and we can catch up later. I hope this was helpful for you. I would be very interested to see any of your output and/or reading your thesis on this. I’d like to see how you do on this!

A. Sadly I am writing it in German!

B. Oh. Okay.

A. My bad! But once again, thanks a lot for your time, and for your willingness to help. That was a really great conversation a lot of interesting …

B. If you have any interesting notes, feel free to send them my way. And I actually host a microservices blog on the pl connect community site that I can send you a link to if you’d like to take a look at any of the articles that I post on there.

A. Oh really? That will be great!

B. Yeah. I will drop you a note on that after lunch.

A. Okay, thank you!

B. Okay, good luck!

A. Have a nice day Tony.

B. Goodbye.

A. Bye.
