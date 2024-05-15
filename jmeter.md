### Thread (Users setup) > Samplers (Requests) > listeners (reports)
### Jmeter default GUI tool default port is 1099 RMI port (Remote Method Invocation) and port 4445 for CLI. 

## Threads: 

### Thread Group: 
- Diffrence between 'Start next thread loop' and 'stop thread': Stop Thread stops the current thread. And, Start next thread loop will stop current and start new thread loop.
- Diffrence between 'stop test' and 'stop test now': when error occurs, stop test stops test after all active threads have finished. Stop test now will kill every thread and will stop run.
- Ramp up period: Period in which JMeter will distribute the Threads load.                                                                                                      
- Delay thread creation until needed: Used when startup delay is needed before thread group creation.
  

### Open Model Thread Group: This one let's control users workload with methods like : ramp-up(gradual increase in load), ramp-down, plateau, spikes(where users increase or decrease gradually in a time period), and pauses.
- rate: How many threads per min or sec or hour.
- random arrivals: For how long it will run.
- Pause: pause load for given time
- comment: 

### Setup Thread Group: 


### Tear Down Thread Grouop: 


## Config element: 


## Listeners: 


## Timers: 


## pre-processors: 


## post-processors: 


## Assertions: 


## Test Fragement: 


## Non-Test Elements: 





## Sampler: 

### HTTP Request: 
- Redirect automatically : redirects to other url as per the server response, this donot consider each redirect as a saperate request.lowering memory taken and response time
- Follow redirect : This also redirects to other url.But, this consider each redirect as a saperate request. Takes more memory and response time.
- Keep alive: passes "Connection: keep-alive" in header. keeps consistant connection between server and cient and holds server resources. 
- use multipart/formdata: For sending json values to server.  
- Browser compatible headers: Selecting this supresses Content type and Content transfer encoding (It supresses HTTP headers that specify the nature of information being transmitted and how it is formatted for transmission). It only keeps Content-Disposition header(HTTP response header that indicates how to process a response payload for frontend view)
  
