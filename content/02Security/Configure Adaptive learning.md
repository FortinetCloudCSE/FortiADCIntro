---
title: "Task 1 - Configure Adaptive learning"
linkTitle: "Configure Adaptive learning"
weight: 1
---
######  *Configure Adaptive learning*  

Go to   
Web Application FireWall  → Adaptive learning    
Click on **Create New** 


![image37](image37.png)
**Name**:JuiceShop  
**Status:** enable the toggle  
**Sampling Rate:** 100  
**False Positive Threshold**:100000   
**Learning Time** 1  
 **SAVE**  


 ![Image38](image38.png)


On the same page click on the **Create New** button to create a **URL LIST** 

![Image39](image39.png)


**URL** /\*  
**SAVE**

Click SAVE again .   

![Image40](image40.png)
Click SAVE again . 

We will repeat the same steps for the second application 

**Name**:DVWA  
**Status:** enable the toggle  
**Sampling Rate:** 100  
**False Positive Threshold**:100000   
**Learning Time** 1  
 **SAVE**


![Image41](image41.png)
On the same page click on the **Create New** button to create a **URL LIST** 

**URL** /\*  
**SAVE**


![Image40](image40.png)


![Image42](image42.png)

Click SAVE again .

The Adaptive Learning page should look like the image below 

![Image43](image43.png)
We will create a WAF profile and associate the Adaptive learning profiles we created with the WAF profile. 

######  *Configure WAF Profile*   

Go to   
Web Application FireWall  → WAF Profile   
Click on **Create New**  


![Image44](image44.png)
**Name**: Juiceshop  
**Adaptive Learning:** Juiceshop from the dropdown menu   
**SAVE**


![Image45](image45.png)
For this exercise, we will focus solely on configuring the adaptive learning module and will not configure the other WAF modules. In a production environment, however, all relevant WAF modules would be configured as needed to ensure comprehensive protection.

We will create a second WAF profile for the DVWA application   
Go to   
Web Application FireWall  → WAF Profile   
Click on **Create New**  


![Image46](image46.png)

**Name**: DVWA  
**Adaptive Learning:** DVWA from the dropdown menu   
**SAVE**


![image47](image47.png)
The WAF Profile page should look like the image below 


![Image48](image48.png)
The next step is to associate the WAF profiles with a virtual server. Refer to the diagram in the traffic flow section to understand how traffic is processed through FortiADC for better context.

######  *Edit the virtual servers*  

Go to   
ServerLoad Balance  → Virtual Server  
Click on **juiceshop** 


![Image49](image49.png)
Click on the **Security** tab   
**WAF Profile:** Juiceshop from the dropdown menu  
**SAVE**


![Image50](image50.png)
We will follow the same steps for configuring the second application. 

Go to   
ServerLoad Balance  → Virtual Server  
Click on **DVWA**


![Image51](iamge51.png)
Click on the **Security** tab   
**WAF Profile:** DVWA from the dropdown menu  
**SAVE**

![Image52](image52.png)
## 
