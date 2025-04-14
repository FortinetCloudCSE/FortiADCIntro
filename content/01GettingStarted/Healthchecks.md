---
title: "Task 1 - Health Checks"
linkTitle: "Health Checks"
weight: 1
---

### Health Checks

In server load balancing deployments, the system uses health checks to poll the members of the real server pool to determine if an application is available. You can also configure additional health checks to poll related servers, and include results for both in the health check rule. For example, you can configure an HTTP health check test and a database server health check test. In a web application that requires access to a database to function, the web server is deemed available only if both the web server and the related database server pass the health check.


##### Configure Health Check 

On the Web manangement interface of the FortiAdc Go to <br>


**Shared resources → Health check** <br>
Click on **Create New**

![create a new Health Check ](HC-1.png)


**Name**  Web Application <br>
**Type** 	HTTP <br>
**Port**	0<br>
**Save**<br>


*Notice that when you change the Type to HTTP, additional options related to HTTP become available, such as method, version, response code, and authentication requirements. For this exercise, we will accept the default values for all other entries except those defined above.*

![Health check configuration](HC-2.png)
