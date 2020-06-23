# The Pragmatic Programmer

Below are notes per chapter on my reading of The Pragmatic Programmer by Hunt/Thomas

## Chapter 1 - A Pragmatic Philosophy
The Pragmatic Philsophy hits on a few key points on making sure you are the best software engineer you can be:

- Take responsibility for your code, having done the research and know exactly what needs to be done. Meaning you can provide plenty of options and not excuses.
- Help reduce entropy, clutter, and disorder in code. This allows you to work with the whole system and not have to work around one piece that is 'a dumpster fire'.
- Don't allow your code to degrade slowly. Always be ontop of the quality and fix problems as you come across them and know the bigger picture of how pieces of code work.
- Never accept 'good enough' as is. Know the trade offs and know when to stop refining your code.
- Always be refining your knowledge base. This means improving critical thinking abilities, knowledge of frameworks, languages, and general going ons in the community. Accomplishing this requires consistent studying and overall constant learning. Always be improving your skills.
- Be able to communicate. Know what you need to say, and how to say it to your audience. Do not try to communicate at incorrect times (such as after work hours) and be able to listen and respond to coworkers appropriately.

## Chapter 2 - A Pragmatic Approach

This chapter hits more specifically on how you can improve your software engineering abilities:

- Don't Repeat Yourself (DRY). Improving your craft as a software engineer means not writing the same code everywhere. Its having one calling place for a process and not having to replicate that process everywhere. Its knowing the use cases for certain procedures so that it is not unintentionally repeated elsewhere. A few more examples are:
    - Adding Documentation of what something does in code. This repeats what the code already states.
    - Adding Documentation as well as the code that does this work. This repeats the overarching logic and makes two places you have to maintain if that business logic changes.
    - Language Issues sometimes cause duplication that is not needed. This is unavoidable but should be noted should the engineer come across it.
    -Duplication can occur due to design mistakes. If you find yourself repeating information across multiple objects because you incorrectly designed for this information to exist in multiple locations, its worth double checking your design to consolidate how this data should persist.
    - Do not duplicate for the sake of time crunch of pressure. In environments where time is of the essence, this will only lead to more problems down the road. Remember chapter 1, and remember to always take care of your problems as you come across them.
    - Sometimes duplication of logic comes from the same work being done by separate developers. Try to be aware of the work other developers are doing, and use version control to acknowledge the work they are doing. If another developer wrote a method similar to yours or duplicates logic/functionality, merge the two together. Be aware of their work so that you can reduce duplication.

- Make your code Orthogonal by design. This essentially means you decouple modules from each other and allows for easier modifications. Addressing a change in X does not mean a change in Y. When systems aren't orthogonal, changing X does change Y and thus every system or module change has secondary effects to another module or system. Making your system more orthogonal allows for:
    - More productivity. Simply not having to touch secondary effects from changes you are making saves time and effort, which allows you to work on more curcial problems.
    - Promotes Reuse. By having one location of change you can reuse this functionality and know what to expect from everywhere it touches, rather than having secondary effects after the face.

- Reduces Risk. You know what you are getting into by simply changing one system. This makes your system more resiliant to change and modules more independent should they be desired for reuse elsewhere. This also allows for better testability.

- Team organization can lead to how orthogonal a team is. Chaotic teams who don't have clear lines of responsibility can lead to chaotic designs that don't have clear lines for subsystem responsibilities, leading to non orthogonal designs.

- Knowing toolkits and third party libraries is very important to maintaing othogonality. It is easy to just use a third party library to create the functionality you desire, however down the road that library could lose support and you're now held back from upgrading your system due to a dependency on an old and outdated library.

- How you code can allow for more othogonality as well:
    - Keep your code decoupled. Modules should not over depend on each other or know too much about each other.
    - Avoid global data which would expose too much knowledge and make functionality too dependent on that knowledge.
    - Avoid similar functions as this may violate DRY (don't repeat yourself) making it easier for functionality of one change cause a change elsewhere.

- Orthogonal systems are both easily testable and well tested. This means having sufficient unit, integration, and UI tests if necessary.
- Orthogonal systems also work well with documentation and the DRY principal. The two are closely related.

Improving yourself as an engineer requires the ability to reverse decisions you have made. If you find you have gone the wrong way on a design, you need to have a way to walk back your decisions and move to a different approach. You typically want to have more than one design in mind, and when you try one, see if it works. You should be able to turn around on this idea if it does not work to try another. Flexible architecture that allows for easy changes makes doing and undoing these changes painless and simple. By making your design flexible to these changes, you make reversability inherient in the design.

You can figure out if a design or system requirement works via Tracer Bullets. What these mean to engineers are things like prototyping or a bear bone system for early usage. This is beneficial for a few reasons:
    - Users get to see something work early. You can get something into the hands of those who wish to see their concept in life. That way they can let you know what will/won't change pretty easily.
    - Developers build a structure to work in. This lets you try out new ideas in a space that exists for experimentation. Its open enough to allow modifications and feature additions pretty easily.
    - You have an integration platform. Having this new functionality, even if dumb, simple, and not built to last, can be integrated into other components to test integration functionality.
    - You have something to demonstrate. This little bit of work allows for something to show to project owners and those who want to see what functionality may look like when all is said and done.
    - You have a better feel for progress. You can see what this work will look like and how far it'll take you. This gives you a feel for actually getting things done.

Its important to remember that prototyping is not identical to tracer bullets, as prototyping is typically code thrown away that was just used to test if something is possible. Tracer bullets are more for giving other engineers places to add functionality or show off bare bone functionality.

Prototyping is used a few more ways via:
    - Architecture
    - New functionality in an existing system
    - Structure or contents of external data
    - Third-party tools or components
    - Performance issues
    - User intefact design

Prototyping allow you to also ignore:
    - Correctness.
    - Completeness
    - Robustness
    - Style
This is all because at the end of the day, prototypes are expected to be thrown away. It is desirable to prototype architecture since you can verify some core questions you may have, such as:
    - Are the responsibilities of the major components well defined and appropriate?
    - Are the collaborations between major components well defined?
    - Is coupling minimized?
    - Can you identify potential sources of duplication?
    - Are interface definitions and constraints acceptable?
And make sure you do not use prototyping to end up as your core end product. It should be a proof of concept and nothing more.

A big influencer of how you approach engineering solutions is based off the domain language you choose. Make sure you choose a language that easily solves the problem at hand. Program close to the Problem Domain. If you need to, make your own mini language to solve the very specific problem you need to solve, assuming no better avenue exists. You can use your own Data language for how data looks in your system. Or you can have Imperative languages which contain statements, control constructs and similar which work with your Data Language.

Consider whether you want a stand-alone language or an Embedded Language. Make sure the solution you go for solves the problem at hand. And consider the trade off of if you want code Easily developed or easily maintained.

Become a great estimator to increase your ability in the industry. You'll often need to estimate time for units of work, systems of work, etc. and becoming great at this helps give product leads what they want while balancing the neccessary time for doing a great job at your craft. You'll do this well by giving close enough time estimations through your own past experience. You can become good at this by building a model for the work to be done, and breaking it a part into smaller and smaller units of work. Then estimating those small units, thus giving a time constraint for the entire project. Keep track of your ability to estimate so that you may improve over time.

## Chapter 3 - The Basic Tools

Every craft requires tools to perform the job. Programming is no different, and mastering some of the basic tools for the job will get you far.

Plain text is extremely useful to engineers, as it provides many applications that can assist you for almost any task. A few things they provide is:
- Insurance against obsolescence
- Leverage
- Easier Testing


Information in plain text will be able to be opened by any text application. The information it provides can be very important to an application becoming obsolete or not runable. It gives leverage over systems by being able to maintain information in it. Much like I am using this readme for my own application, so can text for yours. And text provides easier testing if you want to just load in specific data to be tested against. Its as easy as a text reader.

Another reliable skill to keep in your pocket is mastery of command line shells. You can learn quick commands that list files in your directory, of certain types, archive those files, etc. Being able to master these adhoc commands can go a long way in your development.

Mastering your Interactive Development Environment can speed you up in working. Knowing quick keys, how to easily refactor, etc are priceless to becoming a more efficient developer. The following are what you want to look for in your IDE:
- Configurable: You can configure your IDE however you see fit and develop in whatever way is most comfortable for you.
- Extensible: You can extend your IDE with plugins that provide fixes or add ons that help you, whether its see redundant code, unused methods, or poor naming conventions, you'll see everything you need to fix.
- Programmable: You should be able to program your IDE to perform macros that are efficient.

You also typically want the following features:
- Syntax highlighting
- Auto-completion
- Auto-indentation
- Initial code or document boilerplate
- Tie-in to help systems
- IDE-like features (compile, debug, and so on)

Make sure your IDE does not hinder your speed but actually makes you work better, smarter, faster. It should support your craft, not bring it down, otherwise you're better off using notepad. Every editor is different, so knowing what is available to you is key.

Source Control is something every single team and engineer should be using. Every project should be maintained via source control so that every line is known to everyone, who last touched it, who has ever touched it, and should anything be changed why it is changed. Source control keeps your final project orderly and maintained. It allows concurrent changes to be made to your program by various developers while not allowing conflicting changes to files to occur. Know the commands that your source control allows and mastering them will make it easy for you to ensure that you can get in and out of messes with little to no challenge.

Work towards a mastery of the art of debugging. Bugs will always pop up in your code, and there is no way around that. The following points well help you debug confidently.
- Keeping a grounded mindset when the fires begin will help you see clearly as the problem persists. 
- Focus on finding the problem and not who caused it. Everyone will create bugs so it is irrelevant who caused it. 
- Do not panic no matter how bad the problem is as panicing will only prevent you from seeing clearly. Know where to start. 
- If a bug is happening in a particular location of your code, then go to that part of your code base and work around to find the solution. 
- Build a working knowledge base of debugging strategies, such as only changing one thing when making adjustments, or burrowing to a stopping point quickly. 
- Be able to trace your code well so you know the path its going thrugh before the bug exists and be able to follow that flow in and out. 
- Rubber duck with your colleagues to bounce ideas off their head on why this bug may exist and what potential solutions are. 
- Work through a process of elimination in order to slowly knock out potential points of bug creation. 
- Never be taken by surprise, as a bug can always exist no matter how impossible its existence may be. If it truly is impossible to exist, prove that to be true.

Back on the mastery of text, being able to manipulate text is also an invaluable skill to have. Have a knowledge of Text Manipulation Languages that can help convert one language to another as necessary, or parse through these language files. A perfect example is being able to parse a sql file in your code base to make a legitimate query execution to your database.

Where possible in your process, master the ability to write code generators. Writing Passive code generators gives you the ability to create new source files or perform one-off conversions, as well as producing lookup tables and other computationally expensive resources. Active code generators can be converting your database schema into a code based representation. Ensure that your active code generator doesn't violate the DRY principle needlessly. Write your code generators as light weight as they need to be, and don't needlessly bloat them.

## Chapter 4 Pragmatic Paranoia

Another great tendency for Software Engineers mastering their craft is to acknowledge you cannot write perfect software. You cannot write unbreakable code, it is simply not possible. Knowing that, you want to maintain a level of defensiveness in your programming, to ensure that even though it isn't perfect, your code is as robust and protected as possible.

A way to do this is to maintain Designing by Contract. What this means is to design your code based off responsibilities and right you have predetermined. What this means is ensuring the following:
- Preconditions: ensuring what must be done or the state data should be in before it gets to your code
- Postconditions: ensuring what your data or states should look like when leaving your code.
- Class invariants: ensuring this functionality doesn't change and maintains this contract.

You want to ensure you use these contracts as a guide to writing your code. Don't write assertions that maintain these contracts, as this support typically is not supported. Ensure your language supports contracts when going to leverage this from going to design to implementation. If your code doesn't match a contract, be sure to crash early so that you can know your code has issues early on. Take use of various invariants that you can write for, such as loop, semantic and other invariants.

Program defensively, as if your program crashes you won't know why it crashed. Ensure you're prepared for crashing, and that you can process the errors effectively. Use assertions if necessary in your code. If your code isn't supposed to handle certain states, assert that it won't. And if neccessary, use exceptions so you can properly log and keep track of errors being thrown. Exceptions should be thrown on situations you -are not- expecting, so you can track down the why later. And be sure to manage all of your resources appropriately. This means deallocating when necessary, don't keep too much in memory, and throw/catch exceptions as needed.

## Chapter 5 Bend, or Break

An important mindset for an engineer to have when approach their code is to ensure that code is malleable. You want to be able to undo changes as needed or make adjustments without everything falling apart or having a ripple effect. There are a few mindsets you can maintain and principles to follow that will help you ensure this happens.

Minimize any coupling within your system. You want to keep separate modules as separate possible. Any inseparability will lead to unwelcomed dependencies. This makes making adjustments or changes quite difficult, as a change in one spot can lead to an unexpected change in another. Keep knowledge hidden in the specific modules that need to know about it and keep interactions between modules to a minimum. Leverage the Law of Demeter to minimize coupling as much as possible. The Law of Demeter is a principle of least knowledge design, where the following should happen:
- Each unit should have only limited knowledge about other units. Only units 'closely' related to the current unit.
- Each unit should only talk to its friends. Don't talk to strangers.
- Only talk to your immediate friends.
This means your object should only communicate with other objects/functions closely related to it, and not ones that are not immediately in contact.

Leverage Metaprogramming to get details for how the code should run out of the code itself. An easy way to do this is leverage dynamic configuration. An example of this is having your build pipeline set environment variables rather than your codebase have code directly setting it. There are a few benefits to Metadata-Driven Applications:
- It forces you to decouple your design which results in more flexible and adaptable program.
- It forces you to create a more robust and abstract design by deferring details out of the program.
- You can customize the application without recompiling, and leverage this customization to provide easy work-arounds for bugs in production systems.
- Metadata can then be written in a way that is closer to general purpose languages or problem domain, rather than to a specific language.
- You can implement several different projects of the same application all with different metadata.

Another means to move Metadata out is to move Business logic out of your codebase. Business logic is likely to change as the business needs change, so make sure this logic is easily maintained separately where possible.

Another means of preventing coupling is by eliminating Temporal coupling. Temporal coupling may occur if you write your code in too linear a fashion. If function A must always happen before function B but a new business need to is to access function B independently of A, you now have coupled function B and need to figure out how to break the dependency. One way to improve this is to work on your workflow so it isn't always linear. Try to start from the back and move to the front and vice versa. Work on the overall Architecture first so that you can see the dependencies in action. A perfect example for this is any work involving a database. If a query hits table A and need information from B but another query hits Table B which needs information from Table A, you can end up with deadlocking. To help break this coupling, you can design your modules independently in services so they are self contained. You can also design your code for concurrency so that multiple processes can run at one time without the risk of locking. By designing for concurrency you can deploy many numbers of your application and not worry about locking, making your overall architecture more robust.

Leverage different design principles to lower coupling. One example of this is a 'pub/sub' design. This is where you publish specific events to a queing service and a subscriber will consume these messages and perform specific tasks on them. This allows for specific workflows that are time insensitive to be performed. Another design processes is a Model View Controller process. This separates workflows based on their job. A model holds your data or state, a controller can manipulate this model and change the data or state, and a view will display a page based on this state. This allows you to separate responsibility and ensure specific workflows are happening in specific location.

You can also make your applications more malleable by leveraging a blackboard approach. This allows for fluid teams who can work together relatively seemlessly. Responsibility and work in progress is transparent, but more importantly it adds a level of clarity to your work. If you blackboard the various data states, you can see where dependencies are and where you can leverage concurrency. Seeing the big picture written out helps understanding of nuances.

## Chapter 6 While You Are Coding

Many of these chapters are about ideas to keep in mind when planning work. However, there are many things to keep in mind as you're actively programming, as much of the planning you do can be lost or forgotten when you're many functions deep.

An important concept to keep in mind while actively programming is to avoid Programming by Coincidence. It should not be happenstance that everything works. You should know it will work and know why it works. One mindset that helps ensure you can do this is to know why the code you refactored worked in the first place. Understand what your new code does and understand what the old code around your new code used to do. Try to avoid Accidents of implementation, where you write your code to communicate with older modules in a specific style because the older modules just happened to work that way. Without documentation or understanding you're relying heavily on unknown knowledge to make your code work. You want to avoid this because:
- The code you rely on may not be working properly, it just appears as if it does.
- The boundary conditions you rely on may be accidents and in different circumstances behaves differently.
- Undocumented behavior may change with different versions of libraries you rely on.
- Additional calls you do not need to make can slow your code.
- Additional calls can also increase risk of new bugs.

You may also end up on Accidents of Context where you write your code to rely too closely to the context of what you are writing. If you are writing code that works with a view, does your code have to specifically work with a view or can it work with any html page?

Make sure you program deliberately. Write what you mean to write, and develop how you mean to. You can do this by ensuring the following:
- Always be aware of what you are doing.
- Don't code blindfolded. This means building an application you don't fully understand or leveraging technology you don't entirely understand.
- Proceed from a plan and ensure you have that plan ready as a reference.
- Rely only on reliable things. Don't use libaries who don't serve your use case or have flaky support.
- Document your assumptions so that you know when you expect certain states, data structures, etc.
- Don't just test your code, but test your assumptions as well. This means testing your code thoroughly, and testing that all the situations you believe are handled, are in fact handled.
- Prioritize your effort and spend time on the important parts of your code.
- Don't be a slave to history and ensure you write your code as needed moving forward. Don't rely on older code to tell you how to code.

Be conscious of your algorithmic speeds. In this day, most applications aren't written in a tight fit for speed, however you also don't want to needlessly bog down an algorithm because it is needlessly processing elements you know you don't want. This also means you don't need to overly optimize an algorithm either as you can end up spending more time trying to perfect an algorithm's speed than to just write it in a comfortable speed. Leverage your knowledge of Big O notation to ensure your speed is optimal for your use case.

An important thing to do while you are coding is be ready to Refactor anything. When you see problems you typically want to clean them up. There are some easy to spot code smells that you can clean up as you see them:
- If you discover a violation of the DRY principle, remove duplication.
- When stumbling onto nonorthogonal design, work to make it orthogonal and independent.
- Any Outdated Knowledge you stumble on where business logic has evolved should be changed.
- If the performance of an algorithm is slow, see what optimizations you can make, if any.

Make sure you refactor when you stumble upon issues and keep that mindset going often. This will ensure that the system as a whole is constantly improving. While you do this, keep a couple key things in mind:
- Don't refactor and add functionality at the same time. Keep these processes independent in case something goes wrong.
- Make sure you have thorough testing coverage so that if you break something, it is caught quickly.
- Take small steps so that you can build often and test your changes consistently.

While you are coding, keep in mind to code in a manner that is easily testable. If you are writing functionality correctly, you should be able to independently test those units of work. If you are designing by contract you should be able to test against your contracts as well. Leverage testing harnesses to easily write tests for your application rather than designing your own harness entirely. Ensure you leverage some kind of test window so you can easily see what passed, what failed, and why tests failed. Write tests for everything you add so that if something breaks you know quickly.

Finally, be sure not to over utilize wizards for setting up new environments or projects. These wizards can bloat your projects with things you don't understand or don't need. Sometimes it is necessary to start a project with some things preconfigured, but be sure you know what you need and why you need it if you go this route.

## Chapter 7 Before the Project

There are a number of things to keep in your mind before you start a project. Things like setting requirements, solving the overarching problem, and specifying a project correctly.

Make sure when setting requirements for a project to dig enough for them. You want to ensure you're digging by considering the correct set of circumstances. Your use cases on who accesses what and in what scenarios should be thoroughly researched. When you figure out what your requirements are, make sure to document your requirements correctly. You can do this through various documentation procedures, such as a use case template which specifies various use cases for specific situations. You can also specify use cases by using a UML diagram to show interactions between various actors, or users. Be careful not to overspecify. You want to have an overarching design, not details. As the author states, Abstractions live longer than details. Make sure as well if you need to, to maintain a glossery of all terminology for this project and publish all your documentation for the teams that need to be aware.

Make sure not to get stuck trying to solve Impossible Puzzles. This means not to get stuck trying to find an optimal solution to a problem that might need an outside the box solution. This means that maybe the solution is to use a different framework, or approach the solution with a different process entirely. A good way to consider this is to look at your constraints and consider alternative ways to have an interaction play out. Think of the following concepts:
- Is there an easier way?
- Are you solving the right problem?
- Why is this thing a problem?
- What is it that is making it so hard to solve?
- Does it have to be done this way?
- Does it have to be done at all?

Don't start programming until you're ready. If you have any doubts, investigate them before you proceed to coding. Even if you don't have anything 'done' that doesn't mean you aren't doing anything. Make sure to thoroughly investigate everything you need to in order to feel ready to begin.

Make sure to specify as much as needed in the project, but that doesn't mean specify everything. You cannot specify everything and will most likely specify for the duration of the project if you tried to. You can alternatively describe things generally than to try and specify them in details.

When writing your design documents, use whatever works for what you need to describe. This means don't use UML diagrams for the sake of using UML diagrams. As the author also says, Expensive Tools Do Not Produce Better Designs. So use the tools that work for your team and product leads. Ensure you use the best tools for your team.

## Chapter 8 Pragmatic Projects

When working on projects make sure everyone is ontop of what they need to do. Automate what you can, testing all the code you need to, and have teams that stay ontop of the work they need to do.

Ensure you have Pragmatic teams. This means your team should stay ontop of quality of your project. Do not let any problems persist and tackle them as they come up. Communicate your problems properly and don't repeat yourself (DRY) either in person or in code. Ensure the team functions with orthogonality and writes this way as well. This means your teams should be organized functionaly, not around job functions. A good example of this is organizing your team by the work being done and not because they're all engineers. Your team should automate whatever takes them too much time to manually do, and ensure they know when a project is done and to stop dressing it up.

Automate everything you can and do your best not to rely on manual procedures. Compiling code and generating any code you need to should all be automated as well. Testing should not be manual and should be automated as changes occur in your code. When you automate these things, they ideally should be automated into one whole process. Check out the source code, build the projects, get a distrubtable image of the project, and run the specified tests against this build. Final builds of your project should be tagged and kept separate of your normal process as well. Automate any administrative tasks that you need to manually do as well. This includes web site generation, approval procedures, etc.

Test Early, Test Often, Test automatically. Ensure that when you write code you write tests for every feature you add. This means unit tests for individual pieces, integration tests for multiple pieces, as well as any performance testing or UI testing if needed. These tests should all be automated as much as possible and as early as possible. Make sure you are testing thoroughly and relentlessly to ensure your application stands the test of resiliency. Use pre-existing data for tests if you need to stress the system or test hard to recreate specific scenarios. If needed, write tests for your tests to ensure they are doing what you think they are. Test your state coverage and not your code coverage. It is irrelevant if you test every line of code, but more important that every state a user can get into is covered. Another important note on testing is that if a bug if found, write a test to ensure that the bug is fixed. This test should always exist so that the bug you found can never show itself again.

Use all the documentation necessary to clearly assist your code. By treating english as another programming language, you can add on a lot to the worth of your code. This means adding documentation to your code by means of comments, where the comments specify overarching reasons for a process and not needlessly duplicating code meaning. Things you do not want to comment on are
- List of functions exported by code
- Revision history
- A list of other files this file uses
- The name of the file

Ensure any executable documents you have line up with your code and are only created in one place. Doing otherwise would violate DRY principle. Also don't think of writing as just for internal use. External APIs are much more popular these days and thus being able to write documentation for people outside your code base is becoming very important. It is also important to write these documents so those not on your team but are internal can also understand your procedures correctly. Try to ensure your documentation can be produced by your code if possible. This can be done with markup languages as well.

Be sure to hit expectations and then go a bit beyond. Always communicate these expectations so you know where the finish line is at all times. Don't ever go above and beyond as what you feel is a 'nice to have' ends up a surprise to your team, leads, and the customer. Surprises can be good, but they can also be very bad, and anything you surprise people with is a potential ticking time bomb.

When all is done, take pride in your work, and take pride in what you do. Be proud to put your name on whatever you create, like anyone would with their craft. Work on it regularly, and ensure that you are a Pragmatic Programmer.