# ___<u>JMeter Learning</u>___
Apache JMeter is open-source software that was developed by Stefano Mazzocchi. JMeter was developed and designed to load test functional behavior and measure performance. On the other hand, JMeter can also be used to analyze and measure the performance of web applications, functional tests, and database server tests too.
<br/>

---
---

## ___<u>Test Plan</u>___
A Test Plan can be viewed as a container for running tests. It defines what to test and how to go about it. A complete test plan consists of one or more elements such as thread groups, logic controllers, sample-generating controllers, listeners, timers, Assertions, and configuration elements. A test plan must have at least one thread group.
<br/>

---
---

## ___<u>Test Plan - Elements</u>___

### Thread Group
Thread Group elements are the beginning points of your test plan. As the name suggests, the thread group elements control the number of threads JMeter will use during the test. We can also control the following via the Thread Group −
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

### ___<u>Execution Order of Test Elements</u>___
Following is the execution order of the test plan elements −
1. Configuration elements
2. Pre-Processors
3. Timers
4. Sampler
5. Post-Processors *unlessSampleResultisnull*
6. Assertions *unlessSampleResultisnull*

---
---

## ___<u>Assertions</u>___
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
### ___<u>Response Assertions</u>___
The most commonly used assertion is the Response Assertion, which checks whether a response text/body/code/message/header contains, matches, or equals a specified pattern.

The Pattern can be either be:

a “string” for “Equals” or “Substring” clauses
a “Perl5-style” Regular Expression for “Contains” or “Matches” clauses
Response Entities that can be checked include the following.

___<u>Text Response:</u>___
This is for the response that can be displayed in a browser

___<u>Document (Text):</u>___
This is for anything supported by Apache Tika (it assumes the presence of apache-tika.jar in /lib folder of a JMeter installation). This can include PDF, Office, audio, and video formats. Be careful, because this can be memory-intensive for high loads.

___<u>URL Sampled:</u>___
This assertion is used against a requested URL to ensure it matches expectations. For example, you may want to check that the redirect URL doesn’t contain an error somewhere in the path.

___<u>Response Code:</u>___
This checks to ensure the response code is expected. For 4xx and 5xx response codes, make sure you have checked the “Ignore Status” box (see below for a full explanation).

___<u>Response Message:</u>___
This verifies that the response message appears as expected.

___<u>Response Headers:</u>___
This is used against Response Headers to see if a specific HTTP header is present or absent.

___<u>Ignore Status:</u>___
JMeter out-of-the-box considers all 4xx and 5xx responses as failures. If your test case is negative and, for example, a 404 error is expected, you’ll check this box to suppress JMeter’s built-in status code check and substitute it with your own status code assertion.

---

### ___<u>Duration Assertion</u>___
The Duration Assertion is very simple. Used alongside the Response Assertion, it covers 90 percent of use cases where assertions are required. The usage is very straightforward: It provides the maximum duration in milliseconds, and, if any request lasts longer than the value specified, the sample is marked as failed. When you get a Duration Assertion failure, the output appears like this:

---

### ___<u>Size Assertion</u>___
Size Assertions check the response length to see if it’s equal/not equal/greater/less than the expected size in bytes. It can be applied to:

Full response (body and headers)
Response headers
Response body
Response code
Response message
The easiest way to check the response size is through the “View Results Tree Listener”

---

### ___<u>HTML Assertion</u>___
The HTML Assertion checks that the response HTML syntax is a well-formed HTML/XHTML/XML document. So it’s handy if your Web application or site requires zero HTML validation errors. Most modern browsers render even invalid HTML pages, but search engine robots or third-party integrations may not be so tolerant.

---
---

## ___<u>How to View Results of JMeter Assertion</u>___

In the GUI mode, there are two ways that failed assertions can be inspected:

 - ___<u>Assertion Results Listener:</u>___ This reveals the label under which all the assertions were taken.
 - ___<u>View Results Tree Listener:</u>___ This reveals all the assertions in the test plan.
