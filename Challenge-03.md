Challenge 3: Get Your Hands Dirty
=================================
Next up, find the Lynda.com video series entitled: “Objective-C Essential
Training”. Watch each video in the following list and answer the corresponding
question.

Section 1: Getting Started
==========================
[1.1] Installing the tools (4:42)
---------------------------------
You should already have Xcode installed, but you will need to register as an
Apple Developer.

Do you like cats?

Yes

[1.2] Creating your first application (11:28)
---------------------------------------------
Create your first application using the same steps Simon describes in the video.
Familiarize yourself with the Xcode environment, specifically notice how it can
be manipulated to display different helper tools and how it will attempt to fill
in your code as you type it.

Yes

[1.3] Updates to this course (3:31)
-----------------------------------
Why do you think it's important to be aware of the idiosyncracies with older
versions of Objective-C and to keep up with new features as they are added?

It’s helpful to understand any program, also older versions, written in C / Objective-C. On the other side new features have been added, and some concepts like ARC are important to understand as we leverage a newer version of Objective-C.

Section 2: Objective-C Basics
=============================
[2.1] The Objective-C language (4:11)
-------------------------------------
How did Objective-C become the language to learn if you want to make apps for
the iPhone and iPad?

Objective-C was developed in the 80s for NeXT for NeXTSTEP Operating system, which was the foundation for OS X and iOS. Apple created/added a set of frameworks which are useful to create applications for iOS.

[2.2] The structure of an Objective-C program (6:15)
----------------------------------------------------
Create a new project. Go to the menu option `Xcode`, `Preferences`,
`Text Editing` and make sure *Line Numbers* is checked in the section marked
"Show." Then add comments describing the purpose of each auto-generated line in
the main.m file. For example on Line 17 I would write: 

```
NSLog(@"Hello, World!");  // instructs the console to output: Hello, World!
```

'#import <Foundation/Foundation.h>  //import the foundation framework so we can leverage those enhancements

int main(int argc, const char * argv[])  //main is the starting-point of the application, the initial method being called when the compiled application is being executed
{

    @autoreleasepool {  //autorelease pool concept is about keeping retain counts for objects, so that storage no longer needed can be automatically released.
        
        // insert code here...
        NSLog(@"Hello, World!"); //instructs the console to output the phrase "Hello, World!"
        
    }
    return 0; //return 0 means that the method finished OK without errors.
}

[2.3] Compiling and running your code (8:37)
--------------------------------------------
Why might you build in one version of iOS but deploy in an older version?

Not all users will be on the latest version of iOS, so to have greater reach of potential users, you might want to provide your application to run also on an older version.



Section 3: Program Flow
=======================
[3.1] Logging messages to the command line (6:07)
-------------------------------------------------
Following the example in the video, write a program that calculates and outputs
to the console the number of seconds in ten years. Copy and paste your code
here.

	int numOfYears = 10;
	int secondsPerYear = 365 * 24 * 60 * 60;
	NSLog(@"%i years have %i seconds (excluding leapyears)", numOfYears, secondsPerYear * numOfYears);


[3.2] Writing conditional code (7:01)
-------------------------------------
Using Objective-C, create an integer variable called "day" that represents the
days of the week. Write an if statement that checks whether "day" is a weekend
day. If the day is a weekend day then have your program print a message saying
"Have a nice weekend!" and if it's not, print a message saying "I hope you're
having a good week!"

	NSDate *today = [NSDate date];
	NSCalendar *gregorian = [[NSCalendar alloc]	initWithCalendarIdentifier:NSGregorianCalendar];
	NSDateComponents *weekdayComponents =
	[gregorian components:(NSDayCalendarUnit | NSWeekdayCalendarUnit) fromDate:today];
	NSInteger weekday = [weekdayComponents weekday];

	NSLog(@"Weekday %li", (long)weekday);
	if (weekday > 1 & weekday < 7){
		NSLog(@"I hope you're having a good week!");
	}
	else {
		NSLog(@"Have a nice weekend!");
	}	

[3.3] The switch statement (5:58)
---------------------------------
Create a variable called "hurricaneCategory" and a switch statement that prints
out a message describing a hurricane's category from 1-5.


for (int hurricaneCategory = 1; hurricaneCategory < 6; hurricaneCategory++) {
    reportHurricane(hurricaneCategory);
}

void reportHurricane(int hurricaneCategory)         // pass parameter
{
    switch (hurricaneCategory) {                    // depending on value of parameter, log a message
        case 1:
            NSLog(@"Category 1 - Very dangerous winds will produce some damage");
            break;
        case 2:
            NSLog(@"Category 2 - Extremely dangerous winds will cause extensive damage");
            break;
        case 3:
            NSLog(@"Category 3 - Devastating damage will occur");
            break;
        case 4:
            NSLog(@"Category 4 - Catastrophic damage will occur");
            break;
        case 5:
            NSLog(@"Category 5 - Catastrophic damage will occur");
            break;
        default:
            NSLog(@"Category undefined");
            break;
    }

[3.4] Code snippets (5:15)
--------------------------
Grab a code snippet, indent it to match the indent of your project, then add
comments to it, then select the entire snippet you just modified and save it as
your own code snippet. Time yourself and record how many seconds it takes you to
do all this.

IT TOOK ME 25 SECONDS

[3.5] Operators and expressions (11:08)
---------------------------------------
List the 6 types of operators described in this video. Provide their name, a
description of their meaning, and the syntax you would use to execute them. What
code snippet does the ternary operator replace?

1. Arithmetic operators: + - * /
	result = operand1 operator operand2;

2. Equalitay and comparison: == != > < <= >=
	BOOLEAN = operand1 operator operand2;

3. Logical and/or: && ||
	BOOLEAN = operand1 operator operand2;

4. Modulus operator: %
	result = operand1 operator operand2;

5. Increment / Decrement: ++ --
	operand++; operand--; ++operand; --operand;

6. Ternary: condition ? true : false

// The Ternary operator is a simple IF-Statement like below ...
if (condition) {
	result=true;
}
else {
	result=false;
}



[3.6] Loops (8:53)
------------------
Think of a scenario while using a mobile app that might require you to use a
"continue" statement in the middle of a loop.

for (int number = 1; number < 100; number++) {
    if (number % 7 != 0) {
        continue;
    }
    NSLog(@"Number %i is factor of 7", number);
}


[3.7] Functions (10:16)
-----------------------
What is a function? What is a function prototype? What are the purposes of each?
What are the rules for when and how you can call a function?

A function is a building block of code that can be called by name. It can be designed to receive 0 to n paramters, and a function may return a returnValue or nothing (void).

A function prototype is used to let the compiler know about the function. C requires to know about a function before it's going to be called. So to avoid compile errores because we fail to sort the functions properly, we can use a function prototype on top. The specific implementation of the function can follow later.

Syntax:
	returnType functionName (parameters){
		// function ...
	}
 

Section 4: Variables
====================
[4.1] Data types (7:06)
-----------------------
What are the primitive data types in Objective-C? Why did Apple add a set of
classes to handle other data types?

Primitive data Types: int, float, double, char, BOOL
Apple provided in the frameworks additional commonly used data types. Frameworks in general help to simplify and standardize coding.


[4.2] Working with numbers (9:33)
---------------------------------
Make a table of Objective-C primitive data types. Add numeric data types and
their properties to this table.

Data Type		Property
int				from -2 billion to +2 billion
unsigned int	from 0 to 4 billion
long long int	8 bytes
float			4 bytes
double			8 bytes
char			1 character
BOOL			YES -or- NO


[4.3] Working with characters (4:39)
------------------------------------
Add char and BOOL (the character data types) to your table created above.

**ANSWER ABOVE!**

[4.4] Variable scope (8:06)
---------------------------
Describe in your own words what the scope of a variable is in Objective-C

The scope of a variable is the section of the code in which the variable is known and referenced. The same name can be used for multiple variables on different levels of scope, which can make it tricky to read the code. The rule is the variable definition which is closest wins. Each functions has private variables, variables are passed by value to a function. It's possible to declare a global variable.


[4.5] Enumerations (3:35)
-------------------------
What does the `enum` keyword allow you to do?

Enum allows to restrict values a variable can contain.

[4.6] Using typedef (2:17)
--------------------------
When would you define your own data type versus using an enum?

Use a data type when you are going to declare multiple variables of a custom data type. In comparison to enum it helps to shorten the code.

[4.7] Preprocessor directives (5:56)
------------------------------------
Describe the three common preprocessor directives, `#import`, `#define`, and
`#if DEBUG`. Come up with one example where you would use each.

'#import:  paste content of a seperate file into this code 
'#define:  allows to define a macro. Typically used to define values. Technically it's a find/replace of the defines macro-name througout the code with the assigned value.
'#if DEBUG:	edit in schema the build-configuration, then you can generate additional code for debugging

Example: 	#import <myPlayListClass.h>
Example:	#define MAXATTEMPTS 3
			int maxLogOnAttempts = MAXATTEMPTS;
Example:	#if DEBUG
				NSLog(@"Max. Attempts: %i", maxLogOnAttempts);
			'#endif


[4.8] Working with strings (7:52)
---------------------------------
Define the same string using both NSString and C-style string syntax. Describe
the purpose behind each part of your definition.

NSString *myName = @"Josef"; // * means pointer, because we point to an object of type NSString 
char *myName2 = "Josef";	// as pointer to an array of character
char myName3[] = "Josef";  // as array of characters


Section 5: Classes
==================
[5.1] Introduction to object orientation (7:36)
-----------------------------------------------
Create an encapsulated (including generalized attributes and behavior)
description of a `MobileMakersParticipant` class. Instantiate a single object
representing yourself as a member of this class.

Properties: firstName, lastName, email, gender, numberOfAppsDeveloped
Behavior: addParticipant(firstName, lastName, gender), setEmail, addAppDeveloped
**DO YOU PROMISE YOU DID IT?**

[5.2] Using objects and pointers (6:38)
---------------------------------------
What is the pointer’s role in instantiating an object from a class? How is a
pointer different than a primitive?

A pointer points to a location in memory where the object's attribute values are stored.
As the compiler knows how much memory to reserve for primitives, no pointers are needed to reserve memory needed, but for objects the required memory is not fixed, it's flexible.

[5.3] Messages and methods (6:44)
---------------------------------
What is the main difference between Objective-C’s messages and method calls in
other languages? How can this difference be seen as an advantage while
programming?

Objective-C uses the square brackets instead of dot-syntax. 
Depending on the number of parameters passed, the signature of the method chances as well. Each paramter is named. 
Advantage: you know which method requires which paramters


[5.4] Using existing classes in the foundation framework (8:40)
---------------------------------------------------------------
What's the difference between a class method and an instance method?

Class methods: methods that work on class-level, e.g. instantiate a new object of the class
Instance methods: methods that work on instance-level, e.g. setEmail on the mobileMakerParticipant object


Try typing "NSD..." into your code window. Use the autofill feature and select a
single class name that starts with those three letters. Once the name has been
auto-completed, use the handy shortcut (Option + click) and investigate the
class whose name just got printed to the screen. Examine the task list for this
class. Do this a few more times until you're familiar with the process, or until
you've exhausted your curiosity, whichever comes last.


Section 6: Memory Management
============================
[6.1] What's new with memory management? (1:45)
-----------------------------------------------
Let it soak in. No questions for this one.

**PHEW**

[6.2] Memory management in Objective-C (6:58)
---------------------------------------------
What is the relationship between a pointer to an object, a block of memory, and
the owning and releasing process. Can you come up with an analogy for this
relationship?

A pointer is used to know the address to a block of memory which is used to store the object detail. The question is how long the object is required to allocate storage, and when it can be released. This is achieved with a retain count in the owning and releasing process: reference counting with a retain count is used to know how many references to that object and underlying area of memory are used. When objects are created, the retain counter set to 1. When an object is passed to another method, a retain message should be issued to increase the retain counter. When the object is no longer needed it must be released, at which time the retain counter goes down by one and once to zero and the memory block can be reused.


[6.3] Object creation (7:31)
----------------------------
What does the new method do when used to create an object instance of a class?
Why do we avoid using this method? How long is an object's lifetime?

The new method will allocate a block of memory, will initialize the object values, and return the address for the pointer to that memory block.

Instead of new, use alloc and init methods explicitly. With init methods it's possible to initialize attributes with specific values. An object can have multiple init-methods depending on the number of parameters being passed.
Objects must be released when no longer needed with the release method, ending the lifetime of the object.

[6.4] Using autorelease pools (5:14)
------------------------------------
How does the autorelease pool work? How and when can you use it deliberately?

With an autorelease pool, the technical release of objects is deferred until the pool is drained. Until that, each object which is set to be autoreleased gets an entry in the pool. 
A good reason to use autorelease is within creator-methods.
 
[6.5] Apple autoreleased objects (3:39)
---------------------------------------

What does ARC stand for? Why is it important to remember this?

I assume the question is about Apple autoreleased objects, not ARC :)
Answer: Some objects have other methods to create new instances than method new. For example NSString. Behind the implementation of these methods, there is already an autorelease built, hence it's not needed (actually we can't) manually release those instances. 

[6.6] Introduction to Automatic Reference Counting (ARC) (4:43)
---------------------------------------------------------------
What does ARC save us from having to do? How does it keep us from having to make
this extra effort?

ARC does what we used to do manually. It's part of the compiler to add the necessary memory release statements. I basically scans the code for object creation statements and inserts automatically necessary release/autorelease statements in the background. This avoid having bugy code due to memory leaks.

[6.7] What ARC manages (2:42)
-----------------------------
What are the differences between ARC and garbage collection? What makes these
differences advantageous?

Garbage collection is executed at runtime. Can have an impact on performance, when garbage collection kicks in. ARC is the same model as before, but the compiler figures out where the memory management should go.

[6.8] The rules of ARC (4:20)
-----------------------------
Why can you not release or dealloc memory when working with ARC?

You can't call memory management methods like release and dealloc when ARC is used. The compiler will issue an error. ARC is doing the reference counting, hence it's not allowed to interfere.


Section 7: Custom Classes
=========================
[7.1] Creating your own classes (14:01)
---------------------------------------
What are the two different sections used to create a class? What do they hold
and what files are they placed in?

.h file is the header file, containing the interface (the properties and method signatures)
.m file is the implementation
    
**Challenge!** Create a Tweet class for a twitter style app.

[7.2] Defining methods (8:36)
-----------------------------
**Challenge!** Define what should get passed in and what should get returned by
each of your methods in your Tweet class above.

**DO YOU LIKE TWITTER?**
I am not yet a real user of Twitter, I've only setup my Twitter account a few weeks ago. 

[7.3] Defining properties (7:21)
--------------------------------
How did Objective-C programmers handle instance variables before 2012? How are
they handled now? What got easier and what got obscured?

Before 2012:
- Define instance variable within interface file, and also the getter and setter signatures. 
- Define implementation of getter and setter methods in implementation file.

Since 2012: 
- no instance variables in the interface, only defined as properties
- use @synthesize in implementation file to generate getter/setter method ... and @synthesize is since XCode 4.4 also not needed anymore


[7.4] Defining initializers (12:30)
-----------------------------------
What are initializers and why do we need to use them? Describe a situations when
you can rely on the standard `init` method and when you have to create your own
custom initializer.

Initializer are used to set the default values for all attributes of a newly generated object.
Custom initializer are used to pass parameters into the initialization method. That way you can set the initializations values for attributes. 

[7.5] Using dealloc (5:33)
--------------------------
Why can we have a dealloc method in a class when using ARC, but we can't call
dealloc manually oursevles when using ARC?

Sometimes it is necessary to clean up resource (like DB connections). This can be implemented in the dealloc method. ARC will call the dealloc method.


Section 8: Collections
======================
[8.1] Working with C-style arrays (7:12)
----------------------------------------
What are the three constraints when using C-style arrays? Create a C-style array
that holds the days of the week.

Constraints are:
- no bounds checking
- fixed size
- can't mix types

NSString *weekdays[] = {@"Monday", @"Tuesday", @"Wednesday", @"Thursday", @"Friday", @"Saturday", @"Sunday"};


[8.2] Working with Objective-C array objects (8:00)
---------------------------------------------------
What is the difference between a mutable and an immutable array?

Immutable arrays can not be changed after initialization. Mutable arrays can be modified (add new elements, remove elements, etc.)


**Challenge!**
Create an immutable array containing the days of the week. Create a mutable
array that contains the days of the week that you will be at Mobile Makers. Add
the days of the week from the immutable array to the mutable array.

NSArray *daysOfWeek = [NSArray arrayWithObjects:@"Monday", @"Tuesday", @"Wednesday", @"Thursday", @"Friday", @"Saturday", @"Sunday", nil];

NSRange workingDayRange;
workingDayRange.location = 0;
workingDayRange.length = 5;
NSMutableArray *daysOfWeekAtMobileMakers = [NSMutableArray array];
[daysOfWeekAtMobileMakers addObjectsFromArray:[daysOfWeek subarrayWithRange:workingDayRange]];

[8.3] Using dictionaries (5:55)
-------------------------------
Create a dictionary that lists five or more events in your life and the
accompanying year (or date if you want to get fancy) of the event.

NSMutableDictionary *myEvents = [NSMutableDictionary dictionary];
[myEvents setObject:@"Born" forKey:@"1969"];
[myEvents setObject:@"Married" forKey:@"1998"];
[myEvents setObject:@"Started to work Fulltime" forKey:@"1989"];
[myEvents setObject:@"Ended to work for Coca-Cola" forKey:@"2013"];
[myEvents setObject:@"First Kid born" forKey:@"1996"];


[8.4] Fast enumeration (3:27)
-----------------------------
Use fast enumeration to log the timeline of the life events you described above
to the console.

for (NSString *year in myEvents) {
NSLog(@"%@ in year %@", [myEvents objectForKey:year], year);


Section 9: File Management
==========================
[9.1] Introduction to file management in Objective-C (6:44)
-----------------------------------------------------------
What can you do with files using the methods you are aware of that are available
in Objective C’s Foundation class?

NSFileManager can be used to locate files, as well as to rename, copy, remove files.
Classes like NSString on the other hand support conversion of String to files, both to read file content into strings, and to write strings into a file.


[9.2] Working with paths and URLs (7:17)
----------------------------------------
What are the three parts of a URL? What are the advantages to using NSURL?

Part1: scheme
Part2: domain
Part3: path

Advantages:
Faster than using string paths
Can trap errors
Used by more classes
Recommended by Apple

[9.3] Reading and writing strings (4:38)
----------------------------------------
What would be a reason you would want to write a string to disk instead of just
keeping it memory?

Any data which we like keep persistant should be written to disk. That way the App can reload data when needed (e.g. next time App is started).


[9.4] Archiving objects (12:41)
-------------------------------
Why would you want to archive an object instead of writing the data to disk
using the techniques discussed previously?

Using the archive, it's possible to write all attributes of one object together in one file, and using a structured way to name and access each attribute.


Section 10 - More Complex Classes
=================================
[10.1] Inheritance and NSObject (8:13)
--------------------------------------
How can you determine what methods you're inheriting from a super class? How do
you overide a method inherited from a super class?

In the class reference, go to the super class and check out the methods available in that super class. Continue to lookup the next level of super class until reaching NSObject.
To override a method, you provide a version of a method in your own class using the same signature which you like to override.

[10.2] Extending classes with categories (6:31)
-----------------------------------------------
What is the difference between a category and an inheritance? What are the
limitations of using a category?

With categories you can only add new methods, but no attributes.
The advantage is that you do not need to introduce a new class (a sub-class), within the code you can use the well known standard class and just add new methods.
Maybe one risk of using categories is, that potentially with a new Release a new method could be introduced which might be in confict with the method defined in the category. Simple refactoring should resolve this though.

[10.3] Defining protocols (5:14)
--------------------------------
How are protocols useful?

Protocols help to define how to use certain classes. It standardizes behavior or the way how objects should interact with each other. It's a list of required and optional methods.
 

[10.4] Dynamic typing (11:33)
-----------------------------
What are the advantages and disadvantages to dynamic typing?

(ID) can represent any object. Sometimes you might not know which class an object is made of, e.g. you might want to loop thru an array of objects but you don't know which class each object is made of. In this case using (ID) is a way to work with such objects, and then if needed it's possible to check the class of the object, or the signature (method) that the object should be handling.
In general the guideline would be to use static typing whenever possible, but some scenarios will need the dynamic typing feature.

