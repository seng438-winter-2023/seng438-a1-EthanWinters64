>   **SENG 438 - Software Testing, Reliability, and Quality**

**Lab. Report \#1 – Introduction to Testing and Defect Tracking**

| Group: 16      |
|-----------------|
| Ethan Winters 30116419              |   
| Carter Marcelo 30089543             |   
| Karim Mansour 30112539     |   
| Jason Pang 30120722           |   


**Table of Contents**

(When you finish writing, update the following list using right click, then
“Update Field”)

[1 Introduction	1](#_Toc439194677)

[2 High-level description of the exploratory testing plan	1](#_Toc439194678)

[3 Comparison of exploratory and manual functional testing	1](#_Toc439194679)

[4 Notes and discussion of the peer reviews of defect reports	1](#_Toc439194680)

[5 How the pair testing was managed and team work/effort was
divided	1](#_Toc439194681)

[6 Difficulties encountered, challenges overcome, and lessons
learned	1](#_Toc439194682)

[7 Comments/feedback on the lab and lab document itself	1](#_Toc439194683)

# Introduction

Software testing is a phase of software development that ensures quality and reliability in the development of an application. The creation of a test suite based on requirements agreed upon by the developers and the stakeholders can ensure all desired functionalities of the system are implemented and behave as expected. The early identification and resolution of faults within the project lifecycle - as is accomplished by testing - can reduce costs and improve the efficiency of the development process. 

This report will examine the efficacy of three major test styles. These include Manual Scripted Testing with a defined Test Suite and Regressive Testing by repeating the use of this test suite on an updated application version. Exploratory Testing by first planning the scope to be tested and then working through the entire system will also be utilized for this report.  

# High-level description of the exploratory testing plan

When testing the ATM system, exploratory testing will be used initially to evaluate the functionalities of the system. This will include card insertion, PIN authentication, and customer transactions. Importantly, the exploratory testing phase is not intended to catch system faults that may arise during ordinary usage, and not as the product of edge-case inputs. Further comprehensive testing will be used to verify all functionalities of the system against a series of known inputs and their corresponding expected outputs. 

# Comparison of exploratory and manual functional testing

Through the use of the Manual Scripted Testing suite proves highly effective in revealing any errors in standard runtime operations. The categories of tests, such as transactions, card reading and withdrawals allow various principles of the same system components to be tested together, narrowing down where any and found errors are sourced from. Using this test suite allows the key functions of the system to be proven and showcase bare-minimum operations adequately. This style of testing is highly efficient in revealing major errors that would disrupt system operation. The categorization of the tests allows the work to be effectively split up among large teams to allow the testing to be done at an increased rate. 

The use of Exploratory Testing opens the possibilities for hidden errors to be exposed where they wouldn’t be found otherwise. By testing some of the extreme and rare cases, most notably those you’d never expect in normal system operation, rare yet harmful errors can be revealed. Though this method is not very efficient due to the randomness of testing preventing the splitting of work among large teams. It also may not catch all the existing errors due to the broad scope of testing not going into depth on various system components. When a very large system is going to be tested, it can be challenging to think of every possible case that may occur, which may lead to this method producing a measurable amount of redundancy in testing. 

# Notes and discussion of the peer reviews of defect reports

Various faults were observed in the testing of Versions 1.0 and 1.1. The most notable defects present in both 1.0 and 1.1 were found with the transaction functionalities. In both versions, the machine would print the incorrect card number on the user’s receipt, and choosing the “Money Market” account would result in an exception being thrown by the machine. When making transfers between accounts, the receipt would display the sending account and the receiving account in the wrong order. Account labels were missing in transfer logs, and the machine would show the option number corresponding to the account, instead of the account itself. 

A serious fault in the system was discovered through exploratory testing. Upon startup, the system prompts the user to enter an amount of $20.00 bills to add to the reserves of the machine. While the system checks for negative numbers as inputs, it does not enforce an upper bound on the number of bills. Exploratory testing found that inserting 108 (100 million) bills - an amount less than 231 – 1 (the upper limit of an int), would cause the machine to hang upon attempting any transaction.

Another key issue with the system was revealed though manual scripted testing involved the system’s response to incorrect entry of a PIN. An example of this was a case where the PIN was required to complete a transaction. The PIN was entered incorrectly the first time, and the expectation was that an error state would be triggered and then, when the PIN is entered correctly, the transaction could finish. Instead, when the PIN was entered correctly the second time, the system returned to the main login page instead of proceeding.

# How the pair testing was managed and team work/effort was divided 

With regular communication between group members, the exploratory pair testing was done collaboratively. Each member of each pair would run a number of tests and report on them independently. By allowing each member to perform their own tests, the other could repeat them and confirm the existence of any errors. 
With the larger tasks, such as the Manual Scripted and Regression Testing, the work was split up among all four group members, who would each do their own set of tests and report on them. Once the errors were found by Exploratory and Manual Scripted Testing, the Regressive Testing was done by splitting the errors to be tested among the four members again. The use of Azure made this useful, as all team members can now report and confirm the status of errors without having to constantly exchange messages. 

# Difficulties encountered, challenges overcome, and lessons learned

Due to the rather broad spanning of the activities in this lab, the challenge of the extent collaboration should be implemented was encountered. This was due to the number of tasks required and how some required more teamwork than others. This challenge resulted in new team collaboration levels being explored, such as Discord video calls for when the team was unable to meet in person yet still needed a high-feedback-rate communication method. 
The use of GitHub and Azure as new software platforms proved challenging as well for the team, since many of us are new to these platforms and/or have never used them in a collaborative setting. Ensuring all team members understood the operations and requirements of the various digital software we were using was critical to ensure collaboration could be upheld, and these issues were cleared up by simply holding a meeting to view the software together and discuss all the features found so we could determine and confirm all team members were on the same page with understanding it. 

# Comments/feedback on the lab and lab document itself

Through completing this lab procedure, many things can be confirmed. Learning quite a lot from this lab regarding these three testing practices, this lab will prove highly beneficial in future exercises when it comes to selecting the right testing approach based on the material to be tested. The use this lab makes of all three testing practices, both in groups and pairs allows for the process to be experienced as a pose to just known about, making it much easier to remember and understand for future use. The procedure of this lab, though challenging to follow at times, adequately demonstrates the interactive process of testing and how the various methods of testing can be combined to produce rich and accurate results as to where errors may be located. The use of various bug reporting and documentation software is demonstrated quite well in this lab, which will be proven beneficial in the future for any instances where a large number of tests must be done and properly logged. Overall, this lab has proven helpful in the development of software-testing skills and collaborative testing. 
