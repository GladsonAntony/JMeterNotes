# ___<ins>JMeter Learning</ins>___
Apache JMeter is open-source software that was developed by Stefano Mazzocchi. JMeter was developed and designed to load test functional behavior and measure performance. On the other hand, JMeter can also be used to analyze and measure the performance of web applications, functional tests, and database server tests too.
<br/>

---
---

## ___<ins>Test Plan</ins>___
A Test Plan can be viewed as a container for running tests. It defines what to test and how to go about it. A complete test plan consists of one or more elements such as thread groups, logic controllers, sample-generating controllers, listeners, timers, Assertions, and configuration elements. A test plan must have at least one thread group.
<br/>

---
---

## ___<ins>Test Plan - Elements</ins>___

### Thread Group
Thread Group elements are the beginning points of your test plan. As the name suggests, the thread group elements control the number of threads JMeter will use during the test. We can also control the following via the Thread Group
 - Setting the number of threads
 - Setting the ramp-up time
 - Setting the number of test iterations

**Action to be taken after a Sampler error** − In case any error occurs during test execution, you may let the test either
 - Continue to the next element in the test
 - Stop Thread to stop the current Thread.
 - Stop Test completely, in case you want to inspect the error before it continues running.
  
**Number of Threads** − Simulates the number of users or connections to your server
application.

**Ramp-Up Period** - Defines how long it will take JMeter to get all threads running.

**Loop Count** − Defines the number of times to execute the test.

**Scheduler checkbox** − Once selected, the Scheduler Configuration section appears at the bottom of the control panel.

**Scheduler Configuration** − You can configure the start and end time of running the test.

---
---

### ___<ins>Execution Order of Test Elements</ins>___
Following is the execution order of the test plan elements −
1. Configuration elements
2. Pre-Processors
3. Timers
4. Sampler
5. Post-Processors *unlessSampleResultisnull*
6. Assertions *unlessSampleResultisnull*

---
---

## ___<ins>Assertions</ins>___
The different types of assertions in JMeter include:

 - Response Assertions
 - Duration Assertions
 - Size Assertions
 - XML Assertions
 - Beanshell Assertions
 - MD5Hex Assertions
 - HTML Assertions
 - XPath Assertions
 - XMLSchema Assertions
 - BSF and JSR223 Assertions
 - Compare Assertions
 - SMIME Assertions

---
### ___<ins>Response Assertions</ins>___
The most commonly used assertion is the Response Assertion, which checks whether a response text/body/code/message/header contains, matches, or equals a specified pattern.

The Pattern can be either be:

a “string” for “Equals” or “Substring” clauses</br>
a “Perl5-style” Regular Expression for “Contains” or “Matches” clauses</br>
Response Entities that can be checked include the following.

___<ins>Text Response:</ins>___
This is for the response that can be displayed in a browser

___<ins>Document (Text):</ins>___
This is for anything supported by Apache Tika (it assumes the presence of apache-tika.jar in /lib folder of a JMeter installation). This can include PDF, Office, audio, and video formats. Be careful, because this can be memory-intensive for high loads.

___<ins>URL Sampled:</ins>___
This assertion is used against a requested URL to ensure it matches expectations. For example, you may want to check that the redirect URL doesn’t contain an error somewhere in the path.

___<ins>Response Code:</ins>___
This checks to ensure the response code is expected. For 4xx and 5xx response codes, make sure you have checked the “Ignore Status” box (see below for a full explanation).

___<ins>Response Message:</ins>___
This verifies that the response message appears as expected.

___<ins>Response Headers:</ins>___
This is used against Response Headers to see if a specific HTTP header is present or absent.

___<ins>Ignore Status:</ins>___
JMeter out-of-the-box considers all 4xx and 5xx responses as failures. If your test case is negative and, for example, a 404 error is expected, you’ll check this box to suppress JMeter’s built-in status code check and substitute it with your own status code assertion.

---

### ___<ins>Duration Assertion</ins>___
The Duration Assertion is very simple. Used alongside the Response Assertion, it covers 90 percent of use cases where assertions are required. The usage is very straightforward: It provides the maximum duration in milliseconds, and, if any request lasts longer than the value specified, the sample is marked as failed. When you get a Duration Assertion failure, the output appears like this:

---

### ___<ins>Size Assertion</ins>___
Size Assertions check the response length to see if it’s equal/not equal/greater/less than the expected size in bytes. It can be applied to:

Full response (body and headers)
Response headers
Response body
Response code
Response message
The easiest way to check the response size is through the “View Results Tree Listener”

---

### ___<ins>HTML Assertion</ins>___
The HTML Assertion checks that the response HTML syntax is a well-formed HTML/XHTML/XML document. So it’s handy if your Web application or site requires zero HTML validation errors. Most modern browsers render even invalid HTML pages, but search engine robots or third-party integrations may not be so tolerant.

---
---

## ___<ins>How to View Results of JMeter Assertion</ins>___

In the GUI mode, there are two ways that failed assertions can be inspected:

 - ___<ins>Assertion Results Listener:</ins>___ This reveals the label under which all the assertions were taken.
 - ___<ins>View Results Tree Listener:</ins>___ This reveals all the assertions in the test plan.

---
---

## ___<ins>Timers in JMeter</ins>___

Jmeter threads usually run one after another without any time delay. This can be unrealistic in nature because a normal user will take time gaps to read or think between performing every action. That time is called Think Time and it should be added to make the script more realistic and reliable. To perform such operations JMeter is providing 9 types of timers and the user can select the one which suits the scenario.

---

### ___<ins>Timer’s Present in JMeter</ins>___
 - Constant Timer
 - Gaussian Random Timer
 - Uniform Random Timer
 - Constant Throughput Timer
 - Synchronizing Timer
 - JSR223 Timer
 - BeanShell Timer
 - BSF Timer
 - Poisson Random Timer
 - Every timer has its own usability.

### ___<ins>Constant Timer</ins>___

This can be used to add some delay/think time between each request. The constant timer has the following components. The name that we have given is displayed on the tree and here thread delay is taken in milliseconds. For example, if we want to add 3 seconds think time then we have to enter 3000 as shown above.

### ___<ins>BeanShell Timer </ins>___

This is a scripting-based timer in which we can develop the logic of how to implement a timer. The Bean shell timer has the following components.

### ___<ins>JSR223 Timer </ins>___

JSR223 Timer is also a scripting-based timer similar to Bean shell timer. In JSR223 Timer we can create delays between the user requests using the JSR223 Scripting language. JSR223 Timer components are as follows.


### ___<ins>Uniform Random Timer </ins>___

Uniform Random can be used to add a random amount of think time between the user requests. The Uniform Random Timer has the following components. Name element is meant to give a name to the timer that is to be displayed in the tree. Random Maximum Delay as the name suggests we should enter the maximum delay or think time then it will give a random think time to user requests which are not above the given value. For example, if we don’t want the time time to exceed 10sec then we should enter the value to this is 10000. Constant Delay Offset is an additional value taken in milliseconds. Similarly, other timers are used according to the situation or the requirement of testplan.

---
---
