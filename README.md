# jmeter


# Creating a Basic Test Plan
First, let’s make sure our test works.

1. In the test plan, add ‘serverurl’ as ‘www.github.com’

![image](https://user-images.githubusercontent.com/19672171/182688464-4323da3d-b41f-4f8e-a284-037b1fbc3372.png)

jmeter test plan serverurl

2. Add a Cookie Manager

Right Click -> Add -> Config Element -> HTTP Cookie Manager

3. Add a Request Defaults element

Right Click -> Add -> Config Element -> HTTP Request Defaults

4. In the Request Defaults Server Name type:

Serverurl url variable ${serverurl}
Implementation - HTTPClient4
Protocol - http

<img width="694" alt="image" src="https://user-images.githubusercontent.com/19672171/183298829-93328493-c8fa-4ac4-8948-3dada1f6087b.png">

5. Add a Thread Group

Right Click -> Add -> Threads -> Thread Group

6. Add a HTTP Sampler as a child element to the Thread Group

Right Click on Thread Group -> Add -> Sampler ->  HTTP Request

7. Add a Listener

Right Click -> Add -> Listener -> View Results Tree

<img width="494" alt="image" src="https://user-images.githubusercontent.com/19672171/183298837-58ba6154-779d-467f-b95f-cd747dd84359.png">


8. Save the script and launch the test to ensure everything is working properly.

<img width="730" alt="image" src="https://user-images.githubusercontent.com/19672171/183482168-b3fb8691-1885-49ab-a339-ad5f9cb5f421.png">

# JMeter Thread Number Function

The Thread Number function is a function that shows the number of the thread that is being executed. To examine it, let’s modify one of the threads on our test to go through www.blazedemo.com/vacation.html

