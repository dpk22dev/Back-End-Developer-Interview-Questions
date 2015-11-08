Back-End Developer Interview Questions
======================================

I'm not a big fan of asking technical questions in job interviews: I'd rather prefer to sit together with candidates in front of some real code, facing a real problem, and have a full day of pair programming rotating with all the team members. Yet, some technical questions could be used to start a deep and nice conversation, and this can be useful to get a deeper knowledge of eachothers.

This repo contains a number of backend interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

This project is admittedly inspired by [Front-end Job Interview Questions](https://github.com/darcyclarke/Front-end-Developer-Interview-Questions) by [@darcyclarke](https://github.com/darcyclarke)

**Note:** Keep in mind that many of these questions are open ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would. Again, I stress that just asking question is hardly sufficient. Complete the interview with a long pair programming session with your candidates: it is one of the best opportunities to know eachothers' style and approach and to let candidates know some details about their future dayjob.


## <a name='toc'>Table of Contents</a>

  1. [General Questions](#general)
  1. [Open Questions](#open)
  1. [Questions about Design Patterns](#patterns)
  1. [Languages Questions](#languages)
  1. [Web Questions](#web)
  1. [Databases Questions](#databases)
  1. [NoSQL Questions](#nosql)
  1. [Code Versioning Questions](#codeversioning)
  1. [Concurrency Questions](#concurrency)
  1. [Questions about Distributed Systems](#distributed)
  1. [Questions about Software Lifecycle and Team Management](#management)
  1. [Questions about logic and algorithms](#algorithms)
  1. [Questions about Software Architecture](#architecture)
  1. [Questions about Service Oriented Architecture and Microservics](#soa)
  1. [Questions about Security](#security)
  1. [Bill Gates Style Questions](#billgates)
  1. [Questions based on snippets of code](#snippets)


####[[↑]](#toc) <a name='general'>General Questions:</a>

* Why Functional Programming matters? When should a functional programming language be used?
I think current Procedural or OOP languages can't be run on multiple processors simultaneously because of their binding with data. Functional programming can benefit from it. eg: Scheme and Haskell
Good in concurrency, gamingAPI, mathematical computations.

http://fsharpforfunandprofit.com/posts/ten-reasons-not-to-use-a-functional-programming-language/ 

* What is Encapsulation important for? difference of encapsulation with abstraction.
encapsulation hides how a function does it. eg: convertStringToNumber( str ) , how it does is hidden because of encapsulation.
abstraction( saransh in hindi ): revealing what function does( show essential details only ). above function tells that it converts string to integer.

* What is a real-time system and how is it different from an ordinary system?
real time system has to do its task within time frame with minimum delay. it should have minimal context switching latency, interrupt latency. eg: ABS system in cars, pacemaker

* What's the relationship between real-time languages and heap memory allocation?
? 

* Immutability is the practice of setting values once, at the moment of their creation, and never changing them. How immutability can help writing safer code?
to avoid someone from accidently changing the constant or read only value, immutability is used.

* Pro and cons of mutable and unmutable values.
http://stackoverflow.com/questions/214714/mutable-vs-immutable-objects 

* What's the Object-Relational impedence mismatch?
https://en.wikipedia.org/wiki/Object-relational_impedance_mismatch

* What's the difference between design, architecture, functionality and aesthetic? Discuss
software architecture is about design of entire system giving bigger picture while design include designing module/class or implementation details.
http://stackoverflow.com/questions/704855/software-design-vs-software-architecture

functionality is practically working of things while aesthetic means prettiness of things.

* Which principles would you apply to define the size of a cache?

* How do Companies like Microsoft, Google, Opera and Mozilla profit from their browsers?

* Why opening a TCP socket has a large overhead?
* What's the difference between TCP and HTTP?
* Remove the concept of "null" from your preferred language.
  http://stackoverflow.com/questions/1296843/what-is-the-difference-between-null-0-and-0

* What are the tradeoffs of client-side rendering vs. server-side rendering?
using client side rendering( jQuery, AngularJS etc.. ) avoids loading whole page on small changes. but it harms SEO ( although phantomJS can be used, but it adds complexity ), quirks on various browsers. Sometimes it takes more time to load than getting page from server. So I think we should consider client side rendering only if number of simultaneous users are very high on server, then its good to offload some work to client side.
http://www.quora.com/What-are-the-tradeoffs-of-client-side-rendering-vs-server-side-rendering

####[[↑]](#toc) <a name='open'>Open Questions:</a>
* What did you learn this week?
* List the last 5 books you read. 
* Let's have a conversation about "*Reinventing the wheel*", the "*Not Invented Here Syndrome*" and the "*Eating Your Own Food*" practice
its good not to waste time in something which has already been created, tested and optimized. if we think that we are doing something new, we should check that someone else has done same thing earlier, because most of the time someone has already faced the same problem and might have given solution. 

In programming, it is also common to refer to the "NIH syndrome" as the tendency towards reinventing the wheel (reimplementing something that is already available) based on the belief that in-house developments are inherently better suited, more secure, more controlled, quicker to develop, and incur lower overall cost (including maintenance cost) than using existing implementations. -- wiki
but sometimes it may be good because of patent infringement, lock-in, better control

Eating Your Own Food is using own product, eg: using bing search only. although its good bugs to find bugs.
e difficult? What makes maintaining software hard?
more you know about technology, architecture more you think about scalability, portability, performance harder it get.

* Would you prefer working on Green Field or Brown Field projects? Why?
https://en.wikipedia.org/wiki/Greenfield_project



* [What happens when you type google.com into your browser and press enter?](https://github.com/alex/what-happens-when)
* As a software engineer you want both to innovate and to be predictable. How those 2 goals can coexist in the same strategy?
* There is an aesthetic element to all design. The question is, is this aesthetic element your friend or your enemy?
* What does your computer do when you wait?
* Explain Unicode/Database Transactions to a 5 year old child
* Defend the monolithic architecture
simple to develop, deploy, scale: just use multiple copies of application behind load balancer
but as application grows code becomes difficult to understand, modify. scaling is in 1D, everything has to be scaled. what if only few parts of applications are loaded.
OR we can use microservices arch :)

* What does it mean to be a "Professional Developer"?
* Is developing software an art, a craftsmanship or an engineering endeavour? Your opinion.
* "People who like this also like... ". How would you implement this feature in an e-commerce shop? 
* Say your Company gives you one week you can use to improve your and your colleagues' lifes: how would you use that week?
* What's the next thing you would automate in your current workflow?


####[[↑]](#toc) <a name='patterns'>Questions about Design Patterns:</a>

* Tell me about the Hollywood Principle.
https://en.wikipedia.org/wiki/Hollywood_principle 

* About the Law of Demeter (the Principle of Least Knowledge): write a code violating it, then fix it.
component units should be decoupled in such a way that they call only their neighbours not strangers. increases adaptability and portability.

* Which are the limits and pitfalls of Active-Record?
* What are the differences between Active-Record and Data-Mapper?
http://culttt.com/2014/06/18/whats-difference-active-record-data-mapper/ 

* What is the intent of the Null Object Pattern?
In Null Object pattern, we create an abstract class specifying various operations to be done, concrete classes extending this class and a null object class providing do nothing implemention of this class and will be used seemlessly where we need to check null value. 
http://www.tutorialspoint.com/design_pattern/null_object_pattern.htm

* Why is Composition often better than Inheritance?
http://stackoverflow.com/questions/2399544/difference-between-inheritance-and-composition
http://stackoverflow.com/questions/49002/prefer-composition-over-inheritance

* Domain driven design 
You should have knowledge of domain( say banking software ) before building software or that domain

* What is an Anti-corruption Layer?
similar to adapter design pattern but different, you are fixing someone else's code.
http://programmers.stackexchange.com/questions/184464/what-is-an-anti-corruption-layer-and-how-is-it-used

* Could you write a Thread-Safe Singleton class?
auto thread safe singleton pattern can be used: 
  private static final Object instance = new Object();

	public static Object getInstance() {
		return instance;
	}

* Could you implement Objects in terms of Higher Order Functions, and vice-versa?
?

* Show with an example that global objects are evil.

* The ability to change implementation without affecting clients is called Data Abstraction. Produce and example violating this property, then fix it.

* Write a snippet of code violating the DRY principle. Then, fix it.

* How would you deal with Dependency Hell?
use tools like npm for nodejs, use composer for php, make files can help. OS have their own package managers.

* Why is goto evil?
goto is a quick way to get out of mess. if you have to use goto there might be some problem with design. I think if we can't redesign we should use goto.

* Suppose the system you are working on does not support transactionality. How would you implement it from scratch?


####[[↑]](#toc) <a name='languages'>Questions about Languages:</a>

* Tell me the 3 worse defects of your preferred language
php: dynamic typing and casting like C, == and === for comparison
doesn't support unsigned integers, have to use lib BCMath, auto conversion of integers to float in overflow
order of arguments differ strpos and array_search
can't do recursion

* Why is there a rising interest about Functional Programming?


* What is a closure, and what is useful for? What's in common between closures and classes?
* What are generics useful for? 
* What are high-order functions? What are they useful for? Write one, in your preferred language. 
* Write a loop, then transform it into a recursive function, avoiding mutability. Discuss. 
* What does it mean when a language treats functions as first-class citizens? <br/>

this means the language supports passing functions as arguments to other functions, returning them as the values from other functions, and assigning them to variables or storing them in data structures.

* Show me an example where an Anonymous Function can be useful <br/>
https://en.wikipedia.org/wiki/Anonymous_function

* What is Dynamic Method Dispatch? <br/>
http://stackoverflow.com/questions/20187587/what-is-the-difference-between-dynamic-dispatch-and-late-binding-in-c
<br/>


* What are namespaces useful for? Invent an alternative.

* Talk about Interoperability between Java and C# (choose 2 other arbitrary languages)

* Why do many software engineers not like Java? <br/>
http://www.forbes.com/sites/quora/2015/02/21/java-makes-programmers-want-to-do-absolutely-anything-else-with-their-time/
complexity, running in VM etc...

* What makes a good language good and a bad language bad? <br/>
https://www.quora.com/What-makes-a-good-programming-language


* Write two functions, one Referentially Transparent and the other one Referentially Opaque. Discuss.<br/>
if compiler can replace funciton with expression( content in funciton )  function is referentially transparent other wise its opaque. funciton using global vars can be opaque. 
https://en.wikipedia.org/wiki/Referential_transparency_(computer_science)

* Whats the Stack and what's the Heap?
* Why is it important that in a language functions are first class citizen?


####[[↑]](#toc) <a name='web'>Questions about Web development:</a>
* Why first-party cookies and third-party cookies are treated so differently?<br/>


####[[↑]](#toc) <a name='databases'>Questions about Databases:</a>
* mysql vs postgress sql <br/>
http://stackoverflow.com/questions/110927/would-you-recommend-postgresql-over-mysql


* How would you manage the migration of a project from MySQL to PostgreSQL? <br/>
 https://wiki.postgresql.org/wiki/How_to_make_a_proper_migration_from_MySQL_to_PostgreSQL
 http://stackoverflow.com/questions/4756825/mysql-to-postgresql-migration

* Why in SQL ```SELECT * FROM table WHERE field = null``` does not match records with null ``field``? <br/>
http://stackoverflow.com/questions/12853944/why-in-sql-null-cant-match-with-null

* What's ACID (Atomicity, Consistency, Isolation, Durability)?

* How would you manage database schema migrations? <br/>
when adding or removing coloumn, other teams should be notified about changes. be careful, sometimes old codebase might not work with new schema. situation like we changed database, new code doesnt work with it and old code doesn't work too because db has changed. get help from migration tools. 

* How is Lazy Loading achieved? When is it useful? What are its pitfalls?
Lazy Loading is a programming practice in which you only load or initialize an object when you first need it.  eg: lazily loading images on scroll of page or some threshold time.

if we are using ORM, due to lazy loading ORM will fire query for each cat, which will flood DB.
$cats = load_cats();
foreach ($cats as $cat) {
  $cats_hats = load_hats_for_cat($cat);
  // ...
}

we can batch queries or use eager loading by:

$cats = load_cats();
$hats = load_all_hats_for_these_cats($cats);
foreach ($cats as $cat) {
  $cats_hats = $hats[$cat->getID()];
}

http://www.sitepoint.com/silver-bullet-n1-problem/

* What's the N+1 problem?
https://secure.phabricator.com/book/phabcontrib/article/n_plus_one/

* How would you find the most expensive queries in an application? <br/>
http://www.ducea.com/2006/11/06/identifying-mysql-slow-queries/ 
or we can find interval it took to fetch/update data...

####[[↑]](#toc) <a name='nosql'>Questions about NoSQL:</a>

* What is Eventual Consistency? <br/>
Eventual consistency => data will be updated eventually like DNS system. strong consistency => but SQL requires databases to be ACID compliant and latest data should always be visible.

https://cloud.google.com/datastore/docs/articles/balancing-strong-and-eventual-consistency-with-google-cloud-datastore/

* About the CAP Theorem, make examples of CP, AP and CA systems. <br/>
C - consistency, A - availability, P -partition tolerant: can't have more than 2 at a time <br/>
http://stackoverflow.com/questions/3342497/explanation-of-base-terminology

* How does NoSQL tackle scalability challenges? <br/>
http://programmers.stackexchange.com/questions/194340/why-are-nosql-databases-more-scalable-than-sql

* mongoDB vs lucene searching
mongodb stores data, creates indexes as in sql so searching is similar to sql. but lucene stores inverted indexes for tokens, so its good for full text search


####[[↑]](#toc) <a name='codeversioning'>Questions about code versioning:</a>

* Why branching with Mercurial or git is easier than with SVN?
* What are the pros and cons of Distributed Version Control Systems like git over Centralized ones like SVN?
* Could you describe GitHubFLow and GitFlow workflows?
* What's a rebase?
* Why merges are easier with Mercurial and git than with SVN and CVS?



####[[↑]](#toc) <a name='concurrency'>Questions about Concurrency:</a>

* Why do we need Concurrency, anyway? Explain. <br/>
http://programmers.stackexchange.com/questions/115474/why-should-i-know-concurrent-programming

* Why is testing multithreading / concurrent code so difficult? 

* What is a Race Condition? Code an example, using whatever language you like. <br/>
http://stackoverflow.com/questions/34510/what-is-a-race-condition

* What is a Deadlock? Explain using code. <br/>
 http://www.java2novice.com/java-interview-programs/thread-deadlock/

* What is Process Starvation?
* What is a Wait Free algorithm?

####[[↑]](#toc) <a name='distributed'>Questions about Distributed Systems:</a>

* How to test a distributed system?
* In which case whould you apply asynchronously communication between two systems?
* What are the general pitfalls of Remote Procecure Call?
* If you are building a distributed system for scalability and robustness, what are the different things you'd think of in the case you are working in a closed and secure network environment or in geographically distributed and public system?
* How to manage Fault Tolerance in a Web application? And in a Desktop one? 
* How to deal with failures in Distributed Systems?
* Let's talk about the several approaches to Reconciliation after network partitions
* What are the Fallacies of Distributed Computing? 
* When would you use Request/Reply and when Publish/Subscribe?


####[[↑]](#toc) <a name='management'>Questions about Software Lifecycle and Team Management:</a>

* What is agility?
* How would you deal with Legacy Code?
* I'm the CEO of your Company. Explain me Kanban and convince me to invest on it.
* What is the biggest difference between Agile and Waterfall?
* Being a team manager, how would you deal with the problem of having too many meetings?
* How would you manage a very late project?
* "*Individuals and interactions over processes and tools*" and "*Customer collaboration over contract negotiation*" comprise half of the values of the Agile Manifesto. Discuss
* Tell me what decisions would you take if you could be the CTO of your Company.
* Are Program Managers useful?
* Organize a development team using flexible schedules (that is, no imposed working hours) and "Take as you need" vacation policy
* How would you manage a very high turn over and convince developers not to leave the team, without increasing compensation?


####[[↑]](#toc) <a name='algorithms'>Questions about logic and algorithms:</a>

* Make a FIFO Queue using only LIFO Stacks. Then build a LIFO Stack using only FIFO Queues.
* Write a snippet of code affected by a Stack Overflow 
* Write a tail-recursive version of the factorial function
* Using your preferred language, write a REPL that echoes your inputs. Evolve it to make it an RPN calculator.
* How would you design a "defragger" utility?
* Write a programs that builds random mazes.
* Write a sample code that produces a memory leak
* Generate a sequence of unique random numbers
* Write a simple Garbage collection system
* Write a basic message broker, using whatever language you like.
* Write a very basic web server. Draw a road map for features to be implemented in the future.
* How would you sort a 10GB file? How would your approach change with a 10TB one?
* Implement the `rnd()` function.


####[[↑]](#toc) <a name='architecture'>Questions about Software Architecture:</a>

* What is CQRS (Command Query Responsibility Segregation)? How is it different from the oldest Command-Query Separation Principle?<br/>
 http://programmers.stackexchange.com/questions/165120/separation-versus-segregation

* What is Three-Tier architecture? 
http://stackoverflow.com/questions/4577587/mvc-vs-3-tier-architecture

* How would you design a software system for scalability?
 
* What are the strategies to deal with the C10k problem?
https://www.youtube.com/watch?v=73XNtI0w7jA&feature=youtu.be

* How to deal with failover and user sessions?

* How would you design a decentralized (that is, with no central server) P2P system? <br/>
http://abdulapopoola.com/2013/03/12/design-patterns-pub-sub-explained/

* pubsub vs observer <br/>
http://stackoverflow.com/questions/15594905/difference-between-observer-pub-sub-and-data-binding

* Why doesn't CGI scale?
* How would you defend the design of your systems against Vendor Lock-in?
* What makes code readable?
* What are the disadvantages of the Publish-Subscribe pattern at scale?
* When would you apply horizontal scaling and when vertical scaling?
horizontal or scaling out: use cluster of multiple machines. scaling vertically: increase RAM/CPU on same machine.<br/>
http://stackoverflow.com/questions/11707879/difference-between-scaling-horizontally-and-vertically-for-databases

* When is a cache not useful or even dangerous?<br/>
http://www.slideshare.net/betclicTech/minitraining-to-cache-or-not-to-cache

* What's new in CPUs since the 80s, and how does it affect programming?<br/>
http://danluu.com/new-cpu-features/

* In which part of the lifecycle performance should be taken in consideration, and how?

* How could a Denial of Service arise not maliciously but for a design or architectural problem?
* Why does Event-Driven Architecture improve scalability?

* What’s the relationship between Performance and Scalability?<br/>
http://apmblog.dynatrace.com/2008/09/11/performance-vs-scalability/

* When is it OK to use tight coupling?<br/>
http://stackoverflow.com/questions/19976273/where-loose-and-tight-coupling-would-be-used-as-a-real-scenario<br/>

* What characteristic should a system have to be Cloud Ready?<br/>
http://www.ibm.com/developerworks/websphere/techjournal/1404_brown/1404_brown.html<br/>
http://vitalflux.com/how-to-design-develop-cloud-ready-applications/

####[[↑]](#toc) <a name='soa'>Questions about Service Oriented Architecture and Microservices:</a>
* Why, in a SOA, long-lived transactions are discorauged and Sagas are suggested instead?
* What are the differences between Soa and Microservices?
* Let's talk about web services versioning, version compatibility and breaking changes.
* What's the difference between a transaction and a compensation operation in a saga, in SOA? 
* When is a Microservice too micro?
* What are the pros and cons of MicroService architecture?


####[[↑]](#toc) <a name='security'>Questions about Security:</a>
* What's Two Factor Authentication? How would you implement it in an existing web application?


####[[↑]](#toc) <a name='billgates'>Bill Gates Style Questions:</a>
* What would happen if you put a mirror in a scanner?
* Imagine there's a perfect clone of yourself. Imagine that that clone is your boss. Would you like to work for him/her?
* Interview me
* Why are Quora's answers better than Yahoo Answers' ones?
* Defend Cobol against modern languages
* Where will be you, in 10 years?
* You are my boss and I'm fired. Inform me.
* I want to refactor a legacy system. You want to rewrite it from scratch. Argument. Then, switch our roles.
* Your boss asks you to lie to the Company. What's your reaction?


####[[↑]](#toc) <a name='snippets'>Questions about snippets of code:</a>
* What's the output of this Javascript function?
```javascript
function hookupevents() {
  for (var i = 0; i < 3; i++) {
    document.getElementById("button" + i)
      .addEventListener("click", function() { 
        alert(i); 
      });
  }
}
```

* About Type Erasure, what's the output of this Java snippet, and why?
```java
ArrayList<Integer> li = new ArrayList<Integer>();
ArrayList<Float> lf = new ArrayList<Float>();
if (li.getClass() == lf.getClass()) // evaluates to true
  System.out.println("Equal");
```


* Can you spot the memory leak?
```java
public class Stack {
    private Object[] elements;
    private int size = 0;
    private static final int DEFAULT_INITIAL_CAPACITY = 16;

    public Stack() {
        elements = new Object[DEFAULT_INITIAL_CAPACITY];
    }

    public void push(Object e) {
        ensureCapacity();
        elements[size++] = e;
    }
   
    public Object pop() {
        if (size == 0)
            throw new EmptyStackException();
        return elements[--size];
    }

    /**
     * Ensure space for at least one more element, roughly
     * doubling the capacity each time the array needs to grow.
     */
    private void ensureCapacity() {
        if (elements.length == size)
            elements = Arrays.copyOf(elements, 2 * size + 1);
    }
}
```

* `if`s and in general conditional statements lead to procedural and imperative programming. Can you get rid of this `switch` and make this snippet more objetct oriented?

```java
public class Formatter {

    private Service service;

    public Formatter(Service service) {
        this.service = service;
    }

    public String doTheJob(String theInput) {
        String response = service.askForPermission();
        switch (response) {
        case "FAIL":
            return "error";
        case "OK":
            return String.format("%s%s", theInput, theInput);
        default:
            return null;
        }
    }
}
```


* Can you get rid of these `if`s and make this snippet of code more object oriented?

```java
public class TheService {
    private final FileHandler fileHandler;
    private final FooRepository fooRepository;

    public TheService(FileHandler fileHandler, FooRepository fooRepository) {
        this.fileHandler = fileHandler;
        this.fooRepository = fooRepository;
    }

    public String Execute(final String file) {

        final String rewrittenUrl = fileHandler.getXmlFileFromFileName(file);
        final String executionId = fileHandler.getExecutionIdFromFileName(file);

        if ((executionId == "") || (rewrittenUrl == "")) {
            return "";
        }

        Foo knownFoo = fooRepository.getFooByXmlFileName(rewrittenUrl);

        if (knownFoo == null) {
            return "";
        }

        return knownFoo.DoThat(file);
    }
}
```
