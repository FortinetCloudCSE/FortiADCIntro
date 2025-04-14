---
title: "Task 2 - Testing and viewing the Adaptive learning "
linkTitle: "Testing and viewing the Adaptive learning "
chapter: false
weight: 2
---

#### Testing and viewing the Adaptive learning 

For the next section we will use scripts that we will run on the client machine to generate traffic and to simulate attacks . 

SSH into the client machine   
fortinet/fortinet  
Change the directory dvwa : **cd dvwa**  <br>
Run the script dvwa : **./dvwa** <br>

<br>

![Image53](Image53.png)



Login to the FADC   
Web application Firewall → Adaptive learning – \>Adaptive learning view   
Expand the DVWA TAB and observe the different directories detected by the module 

![Image54](image54.png)
Click on the Login.php page and notice that the system has identified 3 parameters on the page and with the expected input type

![Image55](image55.png)

Expand the “fi” page and notice the system has identified a parameter called page 

![Image56](image56.png)

Switch over to the Recommendation TAB and review the details of the recommendations   
Accept the recommendations and review the config changes by the system 

![Image57](image57.png)

![Image58](image58.png)

In the example below notice the web attack signature created and applied to our virt


![Image59](image59.png)
For the next section we will use a second script  that we will run on the client machine to generate traffic and to simulate attacks . 

SSH into the client machine   
fortinet/fortinet  
Change the directory jshop : **cd jshop**  
Run the script jshop : **./jshop**

**Enter the Juice Shop server address : [https://10.1.1.100](https://10.1.1.100)**

**Choose option 12 to generate traffic** 

![Image60](Image60.png)

**Choose option 10 to simulate some attacks** 

![Image61](image61.png)

Login to the FADC   
Web application Firewall → Adaptive learning – \>Adaptive learning view   
Expand the Juiceshop TAB and observe the different directories detected by the module 

Click on the change-password page and notice that the system has identified 2 parameters on the page and with the expected input type  

![Image62](image62.png)

Switch over to the Recommendation TAB and review the details of the recommendations   
Accept the recommendations and review the config changes by the system

![Image63](image63.png) <br> <br>


![Image64](image64.png)

In the example below notice the web attack signature created and applied to our virt <br>

![Image65](image65.png)

If you run the scripts from previous steps again , you will notice that the waf signature is catching the attacks <br>

![Image66](image66.png) <br>

![Image67](image67.png)





