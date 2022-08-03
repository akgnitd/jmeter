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
