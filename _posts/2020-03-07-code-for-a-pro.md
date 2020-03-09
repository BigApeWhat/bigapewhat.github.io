---
layout: post
title: "Code for a Pro"
permalink: /blog/:title
date: 2020-03-07 20:00:00 -0700
categories: [development]
---
## That’s too complicated
Have you ever heard the saying “Write your code so that anyone can understand it”. Producing quality code is difficult and not always easy to understand. There’s a thin line between advanced coding techniques and hot garbage code. So why dumb down the code for all to understand? So that new employees will have an easier time adjusting? For the sake of JR devs that may have difficulties understanding? This excuse seems to be similar to “change your code so it can be easier to test”. The main objective is to create a quality that is maintainable and avoid refactoring as much as possible. So if “dumbing down the code” or “refactoring classes so its easier to test” do not contribute to a better product, this strategy should be re-evaluated.
<!--more-->

## Sometimes, but not always
It does make sense to make code easier to understand on a high level perspective. Other devs can read along easily, new devs boarding to a team would have a simpler process, wont be stuck in PR reviews, and even when changing teams and having to understand the logic. So yes, in a way I agree, make the code easy to understand and follow, but do not make the code worse by making it easy to understand. It is not a good excuse to simplify the code because it can be hard to follow (unless of course it is hot garbage). Although it can be acceptable to make the code easier to understand as long as it does not impact performance, otherwise just add well written documentation around the code in question.

## What is hot garbage code
Hot garbage code is code that violates CLEAN principals, language standards, or is just mixed with any other bad practices. 

Sometimes you are forced to produce this code just because of the solution or to reach the needs of consumers; as in what you need vs the data you have to work with. Example, street address needs to be title cased unless its a PO Box which then the “PO” needs to be capital and the “Box” is title cased, but the original format of in input string “PO Box” needs to be returned. So “p.o. box = P.O. Box || po. Box = PO. Box”. This is a prime example of a forced “hack” in which your solution will work but you may not feel glad about it. In this example I would say an acceptable solution would be to trim out white space and ‘.’, toLowerCase and check if string contains “pobox”, then split original string by white space, all caps in first [0], title case rest. There still are some loopholes in this logic but you get the idea, right?

Other times, the dev just has a bad day and writes something really bad and regrettable. This would be using bad names, violating standards and principals. Like naming variables ‘a’ and ‘b’ which are heavily used and change types (a = “5323”, a = 72, a = true) throughout the code snippet. The amount of errors I get in JavaScript when I thought I was using a variable as a JSON String but it got changed to a boolean. Python gets worse where the same class instance can have different methods. Either way this is garbage code and violates some rules, you get the idea, right?

## What is Advanced techniques
I would say that in Kotlin language stuff like chained functions, extensions, coroutines, bitwise operators, or delegation can be considered “advanced”, in a way not all devs do these and can get lost, if your shaking your head “no”, well sadly they do. You wont see every devs do these things, they are not hard to learn or implement, but they are at least hard to achieve properly.

One disappointment I have with chained functions is that they are hard to debug, but that should not be the reason to not use them at all. Breaking apart a filter, then mapping, just because having them together is hard to read. Yea it happens, mainly at places that switch from Java to Kotlin or any non functional language to a functional one.
 
Another disappointing battle would be to remove a bitwise operation in a loop to exit early. Since in JavaScript a boolean can be true, false, null, undefined, empty, number, basically anything. The suggestion was to do a bitwise operation ((A + B) | !(C + D)) to see if the fields have values and exit if they do. It was shutdown, and preferred to not exit early for the loop even when an elegant solution was sitting there because bitwise operations are “hard to understand and unpredictable”. One the flip side, if there was another solution that was requested that would perform within spitting range of the bitwise operation and would exit early, it would have been something I would prefer also but not replacing it and have a long running operation instead is pure disappointment.

##Coding for you Grandma
In the end, my point remains. Code like a pro, your granny isnt going to be reading this code, and the devs you work with should learn the more difficult tactics, that is how you become a better dev. 