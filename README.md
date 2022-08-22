# jmeter


# Creating a Basic Test Plan
First, let’s make sure our test works.

### 1. In the test plan, add ‘serverurl’ as ‘www.github.com’

![image](https://user-images.githubusercontent.com/19672171/182688464-4323da3d-b41f-4f8e-a284-037b1fbc3372.png)

jmeter test plan serverurl

### 2. Add a Cookie Manager

Right Click -> Add -> Config Element -> HTTP Cookie Manager

### 3. Add a Request Defaults element

Right Click -> Add -> Config Element -> HTTP Request Defaults

### 4. In the Request Defaults Server Name type:

Serverurl url variable ${serverurl}
Implementation - HTTPClient4
Protocol - http

<img width="694" alt="image" src="https://user-images.githubusercontent.com/19672171/183298829-93328493-c8fa-4ac4-8948-3dada1f6087b.png">

### 5. Add a Thread Group

Right Click -> Add -> Threads -> Thread Group

### 6. Add a HTTP Sampler as a child element to the Thread Group

Right Click on Thread Group -> Add -> Sampler ->  HTTP Request

### 7. Add a Listener

Right Click -> Add -> Listener -> View Results Tree

<img width="494" alt="image" src="https://user-images.githubusercontent.com/19672171/183298837-58ba6154-779d-467f-b95f-cd747dd84359.png">


### 8. Save the script and launch the test to ensure everything is working properly.

<img width="730" alt="image" src="https://user-images.githubusercontent.com/19672171/183482168-b3fb8691-1885-49ab-a339-ad5f9cb5f421.png">

# JMeter Thread Number Function

The Thread Number function is a function that shows the number of the thread that is being executed. To examine it, let’s modify one of the threads on our test 
1. So first, change the number of the threads to a different number, say 3.

<img width="544" alt="image" src="https://user-images.githubusercontent.com/19672171/184212159-d875e03d-b979-4c80-a68a-d8fd047554df.png">

2. Add an If Controller as a child element to the Thread Group. The If Controller lets us execute requests based on a specific condition.

Right Click on Thread Group -> Add -> Logic Controller -> If Controller

In the Condition, write the JMeter function:

${__threadNum()} == 1

This function refers to the thread that is currently executed, in this case, the first one.
<img width="727" alt="image" src="https://user-images.githubusercontent.com/19672171/184212266-87c20c7a-2620-41e8-b564-96c643feecd4.png">

4. Add a HTTP Sampler as a child element of the If Controller

Right Click on Thread Group -> Add -> Sampler ->  HTTP Request

5. Type vacation.html in the path field of the HTTP Request. This means we are running the first thread only through the vacation.html page.
<img width="418" alt="image" src="https://user-images.githubusercontent.com/19672171/184505543-46a5a940-a8ae-4317-b2af-9f232dea2b12.png">

6. Save the test, clear the results and run the script

<img width="455" alt="image" src="https://user-images.githubusercontent.com/19672171/184547932-fa3d7bc6-0a57-4c57-ab0d-2047c9c1d375.png">

You can see in the results that the vacation page was opened only once, and only for the first thread (we changed the HTTP Request’s name to Vacation, to ensure it was running properly).

<img width="759" alt="image" src="https://user-images.githubusercontent.com/19672171/184547948-d4eef36d-46f2-4b10-8dcc-662b65bb514a.png">

# The Information Function and the Function Helper Dialog

The Function Helper Dialog can help you create function strings and see the different function options you have.

1. Open it under JMeter Options, like this:

<img width="728" alt="image" src="https://user-images.githubusercontent.com/19672171/185211191-ee8d406f-6479-4a1e-bebe-c7af921deb8f.png">

2. In the Helper Dialog, you can choose the function you want and see what is required. Let’s look at the information (log) function, which logs a function and returns it in input string.

<img width="728" alt="image" src="https://user-images.githubusercontent.com/19672171/185211287-42329d5f-7f49-4a9c-8523-3c82458ec267.png">

3. Fill in the configurations:

* String to be logged - vacation.html
* Log level - OUT, this means this string will be printed out to the system log
* Additional comment - Some comment

![image](https://user-images.githubusercontent.com/19672171/185461022-bce83a5a-7a6a-41b4-9333-17a7b5c7a625.png)

Right Click on Thread Group -> Add -> Sampler ->  HTTP Request

4. Click on ‘Generate.

You will get the results in the bottom string.

${__log(vacation.html,OUT,,Some comment)}

![image](https://user-images.githubusercontent.com/19672171/185461287-6cfc7a2f-5881-4bbe-a9e3-62e27a0835f3.png)

Now, you can copy and paste it wherever you need it in your script.


5. We will put it in the path field of the HTTP Request under the If Controller.

![image](https://user-images.githubusercontent.com/19672171/185970149-38ab7e00-c65a-4fb4-a6ed-e4329c827860.png)
