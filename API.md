### What is an API? 
- In laymen terms, API is a server in restaurant you go to. Now, to have some food you don't directly get into kitchen to it right?. First you make a request/ order for something X(Biryani) to eat. Now Server is a guy who passes your set of requests(orders) to Kitchen assistant/ chef as Vivek need Biryani to eat he is at table No 4. Now, kitchen assistant is like database who has all details of every items(Preparation methods). So, Kitchen Assistant confirms you order to Server.  
- Server comes back to you with a response called your order is placed/ Confirmed.
- kitchen assitant prepares biryani and sends it to you with server to serve you the dish. 

- Same thing happens with API --> Application Program Interface ( application is a softtware, program is set of instructions, Interface is Communication with other Application/ Software, data base ).
- Basically, In the above humans interracted with each other to get their work done / Process their requests of delivering Biryani.
- Similarly, In software API's Communicate with each other to get thier work done/ to process the requests. But, how do Software communicates with each other they don't eat biryani's right ?
- So, here Human's in software terminology Users/Clients needs it. So place a orders on a Software/Application (Swiggy/ Zomato) the order request reaches to another application at restaurant you have placed. Chef's check the order and confirms it order placed on his application. The application at chef's end send's a confirmation response to your Application. So, in this way API's interact with each other to carry certain set of rules/ instructions. 
- What are instructions on those API's ?  
When see the above examples of your order. Order contains certains instructions of food you requested, the delivery address, location, name etc. 

- Same way API's has a piece of code in JSON format to interract with other Application.  
How data in JSON format is transffered to client, it is through internet using protocols such as HTTP, FTP, SMTP etc. Protocols is set of instructions. [Networking Notes](https://github.com/kunal-kushwaha/DevOps-Bootcamp/blob/main/Networking/Notes1.pdf)  


###### DEFINITION:  

-- API's are set of rules that are used  to enable Communication  between two Software Components.  

In Software terminology, The application sending request is Client and application send response is server.  
![Image](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.g2.com%2Farticles%2Fwhat-is-an-api&psig=AOvVaw02nRCGr50oxt1VUISXDPfi&ust=1700011875225000&source=images&cd=vfe&opi=89978449&ved=0CBIQjRxqFwoTCIDenPGrwoIDFQAAAAAdAAAAABAR)  

#### Types of API's :  
API's has different functionalities based on their function's there categorized.  

### SOAP API:  SIMPLE OBJECT ACCESS PROTOCOL  

* It uses XML to Interract with both Client and Server.  
[!Image](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.atatus.com%2Fblog%2Fsoap-vs-rest-whats-the-difference%2F&psig=AOvVaw0M9caJaA275qERhRc_MK2s&ust=1700014806454000&source=images&cd=vfe&opi=89978449&ved=0CBIQjRxqFwoTCMj-7ua2woIDFQAAAAAdAAAAABAR)  

### REST API : Representational State Transfer API  
* REST API has uses HTTP request that has some functions Called `GET`, `PUT`, `DELETE` `POST` to interract/ perform  `CRUD` Operations on Server's DataBase.  
* CRUD - Create, read, Update, Delete Records. Basically done on Database to perform these operations.  
-   CLient and Server exchange data using HTTP.
- An HTTP method tells the server what it needs to do to the resource. The following are four common HTTP methods:
- `GET` request to retrieve/ get the data, `POST` request to Create Data, `PUT` to Update a Recoord/Data, `DELETE` to Delete the Data.  
---
- APIs that follow the REST architectural style are called REST APIs. Web services that implement REST architecture are called RESTful web services. The term RESTful API generally refers to RESTful web APIs.

### How RESTful API work?  
- The basic function of a RESTful API is the same as browsing the internet. The client contacts the server by using the API when it requires a resource.  
 1. The client sends a request to the server.  
 2. The server authenticates the client (OAuth) and confirms that the client has the right to make that request.  
 3. The server receives the request and processes it internally.  
 4. The server returns a response to the client with status and Requested Resource.  

* When I send a Restful API call to server, it first Authentic me with basic details username/ API key's/ OAuth/ to process my request and sends back a response as Status Code

- #### What are status Codes?  
Status Codes are 3 digit number that describes status of your API call.  
 * 200 Sucess  
 * 201 POST Method Success Response
 * 400 Incorrect Resquest
 * 404 Resource Not Found

 * API end points should be Authenticated, make not vunerable.  
 API on creation should be tested for server responses one such tool we use test is post man. 
 * You can buy new web API's on  online platform like RAPID API, API LIST etc. There free PUBLIC API's too.  
 

