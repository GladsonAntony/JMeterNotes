# JMeter Learning
Apache JMeter is open-source software that was developed by Stefano Mazzocchi. JMeter was developed and designed to load test functional behavior and measure performance. On the other hand, JMeter can also be used to analyze and measure the performance of web applications, functional tests, and database server tests too.
<br/>

## Test Plan
A Test Plan can be viewed as a container for running tests. It defines what to test and how to go about it. A complete test plan consists of one or more elements such as thread groups, logic controllers, sample-generating controllers, listeners, timers, Assertions, and configuration elements. A test plan must have at least one thread group.
<br/>

## Test Plan - Elements

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

### Execution Order of Test Elements
1. Following is the execution order of the test plan elements −
2. Configuration elements
3. Pre-Processors
4. Timers
5. 1Sampler
6. Post-Processors *unlessSampleResultisnull*
7. Assertions *unlessSampleResultisnull*


