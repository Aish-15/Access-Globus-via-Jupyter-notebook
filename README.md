# Access Globus via Jupyter notebooks
## Introduction
### Globus SDK

The [Globus Python SDK](https://www.globus.org/blog/using-globus-jupyter-notebooks) allows you to access and control Globus services using Python code. You can write code to control data transfers between systems, access your transfer history, examine your authentication credentials, and more. All these functions can be used in Jupyter Notebooks.

#Image 1
![image](https://user-images.githubusercontent.com/79628214/118164353-05291200-b3f1-11eb-985c-ccc4fac32b9a.png)


### First things first!

Get a Client <br>
Get and Save Client ID <br>
Get Some Access Tokens! <br>
Use Your Tokens, Perform operations. <br>

#Image 2
![image](https://user-images.githubusercontent.com/79628214/118171830-aa47e880-b3f9-11eb-9f70-b81f8710265d.png)

* [Globus SDK](https://developers.globus.org/) use the link to create an application. <br>
* By  clicking on first option on Globus developers link, it lets the user to create and register the application with Globus developers. <br>
* After clicking, the link navigates to the page to create an account using the user credentials.

### Create the Project
#Image 3
![image](https://user-images.githubusercontent.com/79628214/118172605-90f36c00-b3fa-11eb-8119-690e9313046a.png)


By following the instructions on screen, first create a project. <br>
After clicking on the create project, fill in the details that are required for the project. <br>
After successfully creating a project, click on ‘add app’.
Find the [tutorial](https://globus-sdk-python.readthedocs.io/en/stable/clients/transfer.html) here.

### Application registration
#Image 4
![image](https://user-images.githubusercontent.com/79628214/118172672-a2d50f00-b3fa-11eb-9814-c97d50c8f631.png)


* By clicking on add new app, App registration page opens. <br>
* Enter all the required information for the app registration. <br>
* Make sure, you click on “Native app” if you  would like to run the app on local host otherwise, you may use the URI and other required information related to your application. <br>
* A complete step-by-step tutorial is provided in the link. By clicking the link, you may follow all the required steps and create an application. <br>
* By clicking on “Create App,”  the app is successfully created under the project. <br>
* For this tutorial, I have created the application as a ‘Native app’ and used the same redirect URLs and scopes as specified  in the tutorial. <br>

### Generating client ID

#Image 5
![image](https://user-images.githubusercontent.com/79628214/118172708-acf70d80-b3fa-11eb-9bc2-699fe98203d9.png)

By creating an application, a Client ID is generated. <br>
This Client ID is very important for the further steps of the process. <br>

### Accessing Jupyter notebook

#Image 6
<img width="565" alt="image" src="https://user-images.githubusercontent.com/79628214/118180232-4e369180-b404-11eb-91c0-3723a61e417c.png">

Open the Jupyter Notebook and start importing libraries. <br>
Gather the UUIDs of both the endpoints you wish to exchange the information with. <br>
The Globus Python SDK makes transfer functionality available via a TransferClient class. <br>
We want to configure a TransferClient with an OAuth2 access token, to authenticate its connections with Globus. <br>
The client ID generated is used here.

### Authenticating the application via jupyter notebook

#Image 7
![image](https://user-images.githubusercontent.com/79628214/118180294-5bec1700-b404-11eb-97bb-9933c1a07438.png)

Since the app is native app, when we run the Oauth, and this generates a link in the output. <br>
By clicking on the link, you will be redirected to a page with the authentication code. <br>
Copy the authentication code. This code is valid for only 10 minutes. <br>
Every time we rerun the cell; it generates new link with new code. <br>



#Image 8
![image](https://user-images.githubusercontent.com/79628214/118180329-673f4280-b404-11eb-9f48-653fab680f34.png)

The authorization code looks like this

#Image 9
![image](https://user-images.githubusercontent.com/79628214/118180386-76be8b80-b404-11eb-8214-2dd3ff6ec5a6.png)


This is very important step in accessing Globus from Jupyter notebook. The authorization code generated is copied and pasted here. By running this cell, it authenticates and lets the user perform further operations.

### Transferring files in Globus

#Image 10
![image](https://user-images.githubusercontent.com/79628214/118180408-7e7e3000-b404-11eb-90ad-7951e9239fbc.png)

To perform the transfer operation, get the source and destination path and perform the transfer operation. 
This block of code generates the task ID. 
This Task ID is used to get the status of the task and the other information related to the task.

#Image 11
![image](https://user-images.githubusercontent.com/79628214/118180439-863dd480-b404-11eb-89c9-2768798033b7.png)


By using the generated task ID, the status of the task can also be determined.

#Image 12
![image](https://user-images.githubusercontent.com/79628214/118180483-935ac380-b404-11eb-9cc9-f69c179adaf3.png)

Several other operations can be performed like, getting the previously generated task list with their status, searching for the active 0r successful or the failed statuses.
By using the previously  generated task ID, the task can be cancelled too. 
If the task has been successful, then you cannot cancel the task. 
