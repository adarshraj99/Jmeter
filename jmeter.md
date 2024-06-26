### Thread (Users setup) > Samplers (Requests) > listeners (reports)
### Jmeter default GUI tool default port is 1099 RMI port (Remote Method Invocation) and port 4445 for CLI. 

## Threads: 

#### Thread Group: 
- Diffrence between 'Start next thread loop' and 'stop thread': Stop Thread stops the current thread. And, Start next thread loop will stop current and start new thread loop.
- Diffrence between 'stop test' and 'stop test now': when error occurs, stop test stops test after all active threads have finished. Stop test now will kill every thread and will stop run.
- Ramp up period: Period in which JMeter will distribute the Threads load.                                                                                                      
- Delay thread creation until needed: Used when startup delay is needed before thread group creation.
  

#### Open Model Thread Group: This one let's control users workload with methods like : ramp-up(gradual increase in load), ramp-down, plateau, spikes(where users increase or decrease gradually in a time period), and pauses.
- rate: How many threads per min or sec or hour.
- random arrivals: For how long it will run.
- Pause: pause load for given time
- comment: 

#### Setup Thread Group: 

#### Tear Down Thread Grouop: 


## Config element:
Config elements in JMeter, or configuration elements, are used to modify or configure the sampler requests made to the server. 

#### HTTP Header Manager: 
Can define default headers here and itis used by Samplers.

#### HTTP Cookie Manager:
Here can define cookies which can be used by samplers. 

#### User Defined Variables: 
Can define user variables here and use anywhere like samplers, assertions.

#### CSV Data Set Config: 
used for providing external data to samplers by csv for testing scenarios with multiple datasets. 

#### Random Variable: 
Generated random values and match real time users as input to samplers.

#### counter: 
It creates unique values for each test iteration ,incremented by provided increment.



## Listeners: 
Displays the results of samples in a test in tables, graphs, trees, or log file. 





## Timers: 
timers are time pause in between the execution.

#### Constant Timer: 
 It gives fixed amount of time (in milliseconds) to pause the thread before proceeding to the next sampler.  

#### Uniform Random Timer: 
Provides random delay between requests between provided min and max range.

#### Constant Throughput Timer:
It creates constant throughput (number of requests per minute) as defined by you.




## pre-processors: 
preprocessors are elements that run actions before sampler requests are executed in a test scenario. 

#### JSR223 PreProcessor:
Allows to run custom java code before running sampler. Used to manipulate data, perform calculations, or interact with external systems prior to sending requests.

#### User Parameters PreProcessor:
Used as variables, it is used to avoid duplicate variables as it can be used by different samplers. 

#### DBC PreProcessor: 
Allows to setup DB connection and execute SQL query. 

#### BeanShell PreProcessor: 
Similar to JSR223 preprocessor this one uses BeanShell language. 




## Postprocessor: 

#### Regular Expression Extractor: 
Uses RE to extract specific value from response data that can be used for assertions or requests within tests. 

#### XPath Extractor:
Extracts specific elements or attributes according to the provuided xpaths. 

#### JSON Path Extractor:

#### Debug PostProcessor:
Helps in debugging .Prints the entire response or specific parts of it to the JMeter log. 




## Assertions: 

#### Response Assertion: 
to verify the patterns in the response body received from the server. like : contains, matches, equal, etc. 

#### Size Assertion: 
Size assertion is used to verify the expected number of bytes with >, <, =, etc. 

#### XML Assertion:
verify if the expected XML document is present in the server response or not. it does total expected finding in actual response. Actual can have extra things.

#### HTML Assertion: 
same like XML assertion. Verifies if the expected HTML is in the actual assertion. 

#### BeanShell Assertion: 
Can write custom logic using beanshell scripts. 

#### Duration Assertion: 
Checks response time of requests.


## Test Fragement: 
type of controller that acts like a reusable block of test logic. For code reusablity. Itis not executed until called. 

## Non-Test Elements: 
It is for recording the network traffic, recording test scripts, 




## Sampler: 

#### HTTP Request: 
- Redirect automatically : redirects to other url as per the server response, this donot consider each redirect as a saperate request.lowering memory taken and response time
- Follow redirect : This also redirects to other url.But, this consider each redirect as a saperate request. Takes more memory and response time.
- Keep alive: passes "Connection: keep-alive" in header. keeps consistant connection between server and cient and holds server resources. 
- use multipart/formdata: For sending json values to server.  
- Browser compatible headers: Selecting this supresses Content type and Content transfer encoding (It supresses HTTP headers that specify the nature of information being transmitted and how it is formatted for transmission). It only keeps Content-Disposition header(HTTP response header that indicates how to process a response payload for frontend view)

#### JDBC Request Sampler: 
for testing database performance. It lets you send SQL queries to a database server and retrieve the results. You can specify the connection details, SQL query, and how to handle the results.

#### FTP Request Sampler:     
This sampler is used for testing FTP servers. It allows you to upload, download, or list files on an FTP server.

#### SMTP Sampler: 
for testing email servers. It allows you to send emails from JMeter to verify email functionality and performance.




## Logic controllers: 
allows you to customize the logic used to decide when to send requests. It can change the order of requests, repeat requests, modify requets in run time, run requets in loop, 

#### loop controller: 
allows you to repeat a block of test elements (samplers, assertions, etc.) a specified number of times or indefinitely (useful for load testing).

#### If Controller:
enables conditional execution of test elements based on a specific condition.

#### While Controller:
 keep executing a block of test elements as long as a certain condition remains true. 

#### Transaction Controller:
groups related samplers together to represent a business transaction.

#### Simple Controller: 
basic container that holds a single sampler or another controller. It doesn't add any specific logic but can be used to group related elements for better organization.

#### ForEach Controller: 
iterates through a list of values and executes a block of test elements for each value.

#### Switch Controller:
Switch Controller: This controller evaluates a variable and executes the block of elements associated with the matching value. like a multi-way If Controller based on a single variable.



**********************************************************************************************************************************************************************

## Connecting to MySQL DB: 
Free DB : db4free.net
Free json APIs : dummyjson.com


Jmeter is written on java so, download JDBC driver > Copy mysql-connector.jar file into the jmeter's lib file > Restart Jmeter > In Thread group add config element as JDBC connection configuration > add sampler JDBC request > 
- In Sampler add JDBC connection configuration with DB url with correct port number to avoid connection issue. 
- setup sample in : https://www.youtube.com/watch?v=6i4Qc_jR7LE&list=PLVCgi5HZ0-Yt3N9tbjzi-WVQaH9UKkz73&index=4
   
