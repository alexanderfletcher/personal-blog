---
title: How to approach programming problems. 
date: "2020-04-26"
description: "A introduction to test driven devlopmen designed to help students approach labs"
---
Recently, I've seen a fair few students struggle with some coding exercises and labs. 

**This is ok.**

As a beginner you are going to be confused, you're not going to have much confidence in your work and obviously you will arrive at a solutionslower than your more senior counterparts. 


### What do students do wrong? 
The simple answer here is they work to quickly, too eager to get into the core code and logic when they lack some simple fundamentals, this then normally manifests into one of the following scenarios. 

### **Situation 1**: *I've almost finished the implementation but I am unsure of what the question is actually asking?*
This is normally because of certain requirements being unclear, however a lot of the time this is because the student dives straight into programming a solution without thinking about the problem itself. 
### **Situation 2**: *I swear my implementation is correct but the online tests fail*
Well then is it correct? The main issue here is that between running the online test class, and the actual code algorithm the question is asking you to implement, there is a lot of areas where there could possibly be an issue; how the test class is running, how you're getting the data, how you're outputing the data and also the core algorithm itself. 

### **Situation 3**: *I don't know if my solution is correct*
I see this one occur about half way through where they hit a snag in their implementation, and normally the student hasn't actually ran their code at all. This is a problem as the student does not really know if they are moving in the right direction, aside from the infamously useless `lines of code`, they really have no **explicit** measure of progress. This causes further issues as the student is trying to knock out the entire solution in one go, which means when they get stuck they lack a `checkpoint`, a place to go back to and so end up having to question their entire work. 


If you hit any of these situations, I hope the following helps you in some way, as it is directly talking to you. 
## Why do you struggle with this?
This just comes down to two key points, you either: 

* have not encountered problems like these enough
* have not developed an effective strategy for dealing with problems

The first point comes from practice, coding is a craft and you should think of yourself as an apprentice, but thats for you to focus on (I can expand upon this later if you want). 
I use the term `effective strategy` for the second point as most students actually do have a strategy for dealing with problems, but it appears to be rushing to the solution and then figuring out if it is correct later on. This leads to a problem as if it turns out to be wrong, they often restart the entire problem or get stuck in a hole and ask for help. 
## Requirements
To come up with a successful strategy let's define our success criteria, in other words, what does this strategy need to fulfil in order to be considered successful. We will break these into must haves and should haves.
Must haves: 
1. Can be used to arrive at a correct solution
2. Can be applied to any programming problem in a lab style format. 
Should haves:
1. Easy to follow
2. Be applicable in other areas of programming (not just lab problems)
3. Improve your overall programming skills (hone your craft)
## Strategy
So based on the situations above, you probably focus too much on the solution and not enough on the problem. So a very simple tip is to just  **focus on the problem not the solution**, and here is how we do it. 
We are going to use something known as **Test-Driven Development** (TDD), this may seem like overkill but it will help you get familiar with some fundamentals that you lack, and will help you slow down. 
### Steps
### Every Step: Get frequent feedback: 
 Constantly make predictions and run your code, no matter how trivial. To start with this can be "I think this code should not crash" or "I think this will print hello world". There is a lot of learning to be done when your predictions are off and it will help you identify bugs earlier. 

 **Practie this now**: *In your language of choice, what do you think happens if you try to run an empty txt file? Write down your assumption, and now actually run an empty txt file. What happens? Does the program refuse to run, crash, or print some sort of warning?*/

#### Step 0: Learn git
https://guides.github.com/introduction/git-handbook/
This doesn't actually affect anything really in this guide, but seriously, just go learn it and start using it in everything you do. 

#### Step 1: Identify the problem
Make sure you understand the problem fully and come up with some examples (in some cases they will provide them for you). Ensure that you have super easy examples and some more complicated ones.  
A really important thing to note here is the expected input and expected output, most labs appear to be done by automatic test classes that directly call the code however some may require you to print or write to disk.

**Practice this now**: *Write down the single simplest example you can for a question simply asking you to reverse an input list.*
#### Step 2: Make a hello world
Yes, that's really it. I don't care how trivial this seems, or if you think you are too good for hello worlds as "theyre only for beginners" guess what?... well there's two things
1. That's you, you're the beginner. 
2. They're for everyone, I write hello worlds all the time. 
So yes. Just write it and then run it. It'll save you the embarrassment later on if you dont have something set up properly. 
#### Step 3: Make a function signature for your implementation that returns nothing
**Do not do any implementation**  
**Do not do any implementation**  
**Do not do any implementation**

You don't even have to have any inputs to your function, having something like this is perfectly fine.
```python
def my_function():
    pass ## super useful keyword in python
```
This function is where we're going to do all our `domain logic` , that means it's going to handle the core of our code and won't handle any file io etc. It will also be a pure function, that is *given the same set of inputs it will always produce the same output*. 
Printing this functions output should resemble the solution to the problem. 

**Do this now**:*Make a prediction about what happens if you were to run your code right now. And then run it and see if it matches.* 
#### Step 4: Write a test for you simplest example
In step 1 we came up with a super trivial example of something. So lets put it in a test, that is some way of showing that our implementation works for this example. 
For example, if our problem is that "Given any number, double it", it would end up something like this. 
```python
## case 0 should double to 0
assert my_function() == 0
```
note: you can use regular equality checks and print the result that's ok. 
#### Step 5: Run the test
You should see the test fail (as you haven't implemented anything yet), this is important. If the test passes because it was expecting void or something similar then have the function return something else to force it to fail. 
If you can't get your test to fail then you have a problem somewhere that you need to dig into. 
#### Step 6: Make the test pass
This is the stage you can start implementing your solution. Do the minimum to make the tests pass. So in our previous example we would end up with something like:
```python
def my_function(): 
   return 0
```
now make a prediction, and run your code (ie the tests).
It is important you run them frequently and get used to it. 
#### Step 7: The TDD loop
ok so now we have a basic implementation of one trivial example. If possible you should `git commit` at this point, this gives you a checkpoint to return back to. Every time a test passes you should commit.  
The basic TDD loop is simply to repeat steps 4 - 6 with more examples each time. 
That is: 
1. Write a failing test
2. Make the test pass
3. (Optional) refactor
And you keep doing this until you have no more tests to write. At that point you should be done with your implementation, if not it means you missed a requirement.
When coming up with test cases try and think of edge cases and how you should handle them. 

**Note:** *The reafactor 3rd step points out somethign critical, always make sure you write the simplest code to get something to pass, try and avoid premature optimisation and focus on the problem itself. Once you have a solution these tests allow you to go back and improve on your solution either by making it more readable, or perhaps faster.*
### Advantages
A big point is you know once you've finished as you have a suite of tests that you can run to verify your program, this means that you can actually reimplement it over and over again in different ways and still be confident that it is correct. Maybe your professor wants you to solve the same problem multiple times using a different method or algorithm. 
Deals with the scenarios: 
* You should understand the problem as it was step 1
* The online submission tests should pass and if they don't you can be confident that the issue is with your integration with their test suites rather than your core algorithm itself. 
* You know your solution is correct (at least close to correct) and you can prove it with tests

### Takeways

The most important part of this is you should learn from this is that you should slow down and think about what you are actually doing. In my work as a software engineer there has been plenty of days where I only wrote a few lines of code, but they were the correct lines of code and have accompanying tests to verify that. 

The techniques described here will be useful throughout you're engineering/development/cs career. To some they are known unknowns and to others they are unknown unknowns, (that is things people don't know that they don't know). Most importantly this is a **practical excersise**, reading this is only 10% of the value, to truly learn you will actually need to try it out. 

If you have any questions, reach out and I can improve or write a follow up, maybe an example walkthrough/screencast if needed. 