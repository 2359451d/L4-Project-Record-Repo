---
title: Week 19/7 Meeting Report
tags: Templates, Report
description: Weekly Meeting Report
---

# Week 19/7 - Meeting Report

Time: 22/02/2021 Tue 14:00-14:30

<!-- # Week 16/4 - Recap -->

<!-- previous week mentioned: -->

<!-- 1. It would be great if the compiler reports more errors as many errors as possible -->
<!-- 2. Experiment code generation with arithmetic expression first -->


# Week 18/6 - Progress

* Expression (logical, relational, arithmetic Operators) part code generation for **primitive types** finished
* Basic Procedure,Function declaration & call done
    * except for
        * **pass variable argument**, as Java only has concept of passing value, so this might need extra tricks
        * **nested procedure, function declaration**
        * pass **procedure, function as parameters**

procedure decl
![](https://i.imgur.com/ld0v2vw.png =600x)![](https://i.imgur.com/PqYaFnR.png =600x)
procedure call and output
![](https://i.imgur.com/RfJHMHs.png =600x)

function decl
![](https://i.imgur.com/LoeL2P3.png)
function call and output
![](https://i.imgur.com/hRpbIoe.png)


* **write, read procedure** works for all the **primitives**
    * But **Real type** would be printed in normal way(Java) rather than scientific way (freePascal)
    * ![](https://i.imgur.com/lWJgTFR.png)
* **if statement** done
* repetitive statements (repeat..until not done)
    * **while**
        * ![](https://i.imgur.com/dfIY22V.png)
    * **for**
        * ![](https://i.imgur.com/4KO9OqM.png)


<!-- # Decision

1. **Might not refine runtime overflow/underflow check** (literal overflow/underflow check partially implemented in contextual analysis)

* As JVM won't complain with intger overflow
    * ![](https://i.imgur.com/g4kLNIF.png)
    * this line would output `2` in jvm rather than throwing a runtime exception -->
 
<!-- # Questions

## Dissertaion-Related Questions

1. Does it make sense to have Test cases for code generation stage? (Then in Evaluation-Applicability part breaks into two subsections: Contextual analysis & Code generation)

* for example
    * compare the compiler running result with the results of equivalent Java program
    * regression test cases: check whether has expected output
* I'm worried about it as running regression test cases seems a little bit subjective. No evidence might guarantee the reliability... -->

<!-- # Questions

## Project-Related Questions

> Pascal to JVM compiler
> 
> The aim is to design and implement a compiler for the classic programming language Pascal (or another language), using Java Virtual Machine code as the target language. If time permits, language extensions can be explored.
> 
> Ideally the student will have taken PL(H). This project is an opportunity to put the concepts and techniques of that course into practice, as well as gaining an in-depth knowledge of the Java Virtual Machine.

1. Could the **intermediate code optimisation** be one of the extended direction or shall just let JVM process the intermediate code directly

2. Shall I go deep through the concepts of **NFA**(nondeterministic finite automaton & **DFA**(deterministic finite automaton) in syntatic analysis stage

* i.e. was this worth methioning in the dissertation though I'd assume all this concepts are being handled by the automation tools...

3. Shall I go deep through the **LL(1) parsing algorithm** of the top-down construction method?

* i.e. was this worth methioning in the dissertaion... like to describe how exactly the top-down method being implemented

4. Is the **Code Transformation** to the AST generated by the parser needed?
 -->
<!-- # Blockers

-- -->

<!-- # This week Plan (After Meeting)

* Orgnize minutes of this week
* Continue code generation coding
    * finish Expression (for simple types)
    * basic Procedure/Function Declaration, Statements
    * Control flow Structure (if, while, for)
    * ...
* Might start dissertaion background part if have time -->


---

# Week 19/7 - Meeting Minutes

would be organized after meeting... 

## 15th Meeting: 11/10/22 - Tue

time: 14:00 - 14:30

## Things Mentioned

* should switch to writing, so we have things to discuss related to the report
    * might want to implement constructs that havent done if have time (but **low priority** for now)
* Design part
    * Consider write about the standard compiler architure (3 stages)
        * what kind of things might need to do in each stages
        * like
            * syntactic
                * lexer, generate token based on production rules
                * take token, generate AST
            * semantic
                * consume AST (visitor pattern),
                * type check
                * scope check
            * code generation
                * code selection
                * emit target code (bytecode)?
        * substitude concrete concepts into standard compiler design?
* Implementation part
    * Seperate into 3 stages (Main sections)
        * language constructs as subsections in each stage?
            * expression
            * proc,func
            * control flow
            * ...
* Future Work
    * Might cover features that not implemented, and ideas about how these might be implemented
        * e.g. nested proc,func decl, pass them as parameter. 
* Reason of why only basic features of std Pascal implemented => more complex features are built upon simple one
    * if start from complex one, might need extra refactor work to do as time goes. As complex features might depends on different basic constructs, and it is hard to determine the uniform behavior of if starts from complex one.
    * go back might find that, other features worked entirely different, unexpected
    * **though only basic subset of Pascal features implemented, still the program can be expressed in straight forward way**