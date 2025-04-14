---
title: "Task 2 -  Define Application Servers and Pools"
linkTitle: "Application Servers and Pools"
weight: 5
---

##   Real Servers

Real servers are physical/virtual servers or public cloud instances that form real server pools. The Real Server configuration object specifies the status, type, and IP address or FQDN of the physical server. This Real Server configuration object can then be used as a member to form a real server pool.
When FortiADC is deployed in L7 mode (reverse proxy), a new TCP session is established from the FortiADC to the real server. A "Real Server SSL Profile" determines how SSL is negotiated between the FortiADC and the real server.

In the Next Few Steps we will Define Real Servers and use them to create a Server Pool.


For this lab we will define two application servers. 
#### Configure Real Servers
On the Web manangement interface of the FortiAdc, Go to

**Server Load Balance → Real Server Pool** <br>
**Click on Real Server Tab** <br>
**Create New** <br>

![Create Server ](<create Server.png>)

<br>

**Name** :APP-Server1 <br>
**Server Type**: Static <br>
**Status**: Enable<br>
**Type**:IP<br>
**Address**: 10.1.3.4<br>
**Save**<br>


![Create Server 2](<create Server2.png>)

<br>We will repeat the same steps as above to add the second application server. 

**Name** :APP-Server2 <br>
**Server** Type: Static <br>
**Status**: Enable <br>
**Type**:IP <br>
**Address**: 10.1.3.5 <br>
**Save** 

![Create Server 3](<create Server3.png>)<br>


Your final result should look like the image below <br>

![Create Server4](<create Server4.png>)

In the above example, we used IP addresses to define the real servers. However, we also have additional mechanisms, such as FQDN, to define the real servers. Additionally, the server status can be set to "disabled" to ensure FortiADC will not send traffic to the server, or it can be put in "maintenance mode" to allow current sessions to continue while preventing new sessions from being sent to the server. Please refer to the user guide for additional details

##   Server Pool
 
A server pool consists of multiple servers working together to manage incoming requests efficiently. By distributing the workload across all servers, the pool prevents any single server from becoming overloaded. A load balancer directs traffic to servers within the pool based on predefined criteria such as server capacity, current load, and health status. This configuration improves the availability, scalability, and reliability of applications and services.

Once a server is added to the pool, a health check must be assigned to ensure the FADC can assess the server’s status and availability before forwarding requests.

In the next step, we will define a new pool, add the servers created in the previous exercise, and bind the health check from the first exercise to ensure proper monitoring and load distribution 

On the Web manangement interface of the FortiAdc, Go to <br>
**Server Load Balance → Real Server Pool** <br>
Click on **Real Server Pool Tab** <br>
**Create New** <br>

![Create Pool ](<create Pool.png>)

**Name**: Web-Application <br>
**HealthCheck**: enable the toggle for health check and add the health check we created earlier<br>
Click **ok**  to save the configuration <br>


*Please note that if there is a requirement to encrypt the traffic between FortiADC and the application servers, you must configure the Real Server SSL profile and enable it within the server pool definition.*

![CreatePool2](<create pool2.png>)



Click on the **Create new** button under Member 

![createPool3](<create Pool3.png>)

**Real Server:**  APP-Server1 from the drop down menu <br>
Accept default values for the other options <br>
**Save**<br>


![createPool4](<create Pool4.png>)

Repeat the above process to add the second application server to the pool . <br>

**Real Server:**  APP-Server2 from the drop down menu   
Accept default values for the other options   
**Save**

![createPool5](<create Pool5.png>) 

Since we will be using two applications to run our lab we will repeat the above steps again to define our second Real server Pool. 

***Create Real Servers for 2nd application***

In this section we will define two application servers. <br>
On the Web manangement interface of the FortiAdc, Go to <br>

**Server Load Balance → Real Server Pool**  
Click on **Real Server Tab**  
**Create New**

**Name :** DVWA1  
**Server Type:** Static  
**Status:** Enable  
**Type:** IP  
**Address:** 10.1.3.4  
**Save**  

![createPool8](<create Pool8.png>)

**Name :** DVWA2  
**Server Type:** Static  
**Status:** Enable  
**Type:** IP  
**Address:** 10.1.3.5  
**Save** <br>

![createPool7](<create pool7.png>)
<br>

Next we will create a Server Pool and add the servers we created to the new pool. <br>
On the Web manangement interface of the FortiAdc, Go to <br>

**Name:** DVWA <br>
**HealthCheck**: enable the toggle for health check and add the builtin LB\_HLTCHK\_ICMP  <br>
Click **ok**  to save the configuration <br>

Add the Real Servers defined in the previous step to the pool   
Your final result should look like the image below 

![createPool12](createPool12.png)
