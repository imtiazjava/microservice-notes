# microservice-notes
![REST-PRINCIEPLES](https://user-images.githubusercontent.com/26134506/186650829-39e23aaf-93af-4679-944e-cc04747f0c0b.jpg)
---------------------
```
@Entity
public class Address{
    private int addid;
	private String street;
	private String state;
	private String city;
	//no-arg constructor
	//arg-constructor
	//setters and getters 
}

@Entity
public class Employee{
	private int id;
	private String name;
	private double salary;
	@OneToMany(cascade=CascadeType.ALL)
	@JoinColumn(name="addid")
	private List<Address> address;

   //no-arg cons
   //arg-cons
   //setter&getters methods
}
```
---------------------------------------------------------------------------
Principle of REST:
-------------------
1.Client-Server
2.Uniform interface
3.Cachebaility
4.Stateless
5.Layered system architecture
6. Code on demand
-----------------------------------------------------------------

HttpRequestFormat:
-------------------
|-> When client send the request it send in the form of HttpRequestFormat the following
are the information it contain:
        
         I. Initial Request Line: Which contain the following 3 information
                  A. Method Name
                       -GET
                       -POST
                       -PUT
                       -DELETE
                       -TRACE
                       -OPTION
                       ..
                  B. REQUEST RESOURCE: The following are the request resource:
                        - It can be any thing:
                            -HTML
                            -JSP
                            -SERVLET
                            -XML
                            -JSON
                  C.  PROTOCOL/VERSION : HTTP protocol vesion can be anything.
        II. Zero or More no of Headers:
                   - Header will provide extra information either from client-server or server-client
                         A. User-Agent : Which give the browser information
                         B. Accept-Lang : Every lang and country has the code
                                eg: en-US
       III. Blank line

       IV.  Request Body : When we send the post request it will append the data in the request body and send to server.


 HttpResponseFormat:
 -------------------
  I. Initial Request Line: Which contain the following 3 information
                  A.Protocol/Version : Http protocol version can be anything

                  B.Status Code:Statu Message:

                         Status Code:
                         1xx
                         2xx
                         3xx
                         4xx
                         5xx
                         Statuc  Message:
                         OK
                         CREATED
                         .....

        II. Zero or More no of Headers:
                   ContentyType/MIME:
                   -text/plan
                   -application/json
                   -application/pdf
                   -json
                   .....
       III. Blank line

       IV.  Response Body : What ever the data send by server it will append in  response body and send to client. According to data which is send by server it will print
         the data on browser.

---------------------------------------------------------------------------------------------------------
Monolithic Architecture:
-------------------------

What is Monotlithi Application?

Ans : 
     - All the functionality of a project exist in a single unit then that appliction
     is known as a monolithic application.

     - We have to design a monolithic application in our lives in which we were given
       a problem statement and were asked to design a system with various functionalities.

     - We design our application in various layers like presentation, service and
       persistence layer and then we deploy that code as single jar/war file.

Advantages:
----------

|-> Easy
    -dev
    -dep

|-> Easy debug

|-> Simply the testing

.....

Disadvantages:
--------------
|-> Slow the application
|-> Scalibality
|-> Barrier to the technologies
|-> Deployment
|-> Fixing bugs


 Challenges of Monolithic Architecture:
 --------------------------------------
 
 |-> Monolithic applicaiton cannot be build using different technologies.

 
 |-> Even if one feature of the system/application does not work, then the
     entire system/application does not work.

 
 |-> Applications cannot be scaled easily since each time the application
     needs to be updated , the complete system/appliction has to be rebuilt.

 
 |-> Many featuers / component of the application cannot be build and deployed
     at the same time.

 
 |-> Development in monolithic application take lot of time to be build since
     each and every features/module/component to be build one after the other.

 |-> Not fit for complex application

--------------------------------------------------------------------------------
Microservices:
--------------

Q. What is Microservice?
Ans: It is an architectural style that structure an application as a collection of
      small autonomous services which will be modeled around a business domain.
      or

     It is an architecturual development style in which the application is made up
     of smaller services that can handle a small portion of the functionlity and
     data by communicating with each other directly using lightweight protocols
     like HTTP.

     or

     According to Sam Neman "Microserices are the small device that work together"


 ------------------------------------------------------------------------------

   Monolithic Arch                   vs            Microservie Arch
   ------------------------------------------------------------------
    -It is build as                                -It is build on small independent
     one single unit                                module based on Business fun

    -It is not Easy                                -It is easy to scale.
     to scale based
     on demand


    -It has shared the                             - Each project and module
      same database                                  has their own db.


    -Large code base                               -Each project is independent
     makes IDE slow                                 and small size.
     and build time
     get increase.


    -It extremely								   - Easy to change technology or
     difficult to                                    framwork because every module
     change technology                               and project are independent.
     or lang or framework
     because everything is
     tightly coupled and depend
     on each other



|-> Generally in micro service architecture, each service is self-contained
   and implements a single business capability.


|-> All the functionalites perfromed by microservices are communicated to the
    clients via API Gateway.

|-> All the microservices communicate with other throught a stateless server
    which is either REST or Message Bus.


 --------------------------------------------------------

 Microservice Features:
 ----------------------
  1. Decopuling
    - Services within a system are largely decoupled. So , the application as
         a whole can be easy built, altered and scaled.


  2. Compenentization:
     - Microservices are treated as independt component that can be easly replaced
       and upgraded.



  3.Business Capabilities:
   
   - Microservies are very simple and focus on single capability.


  4.Autonomy:
   
   - Developers and teams can work independently of each other, thus increasing the speed.


   5. Continuous Delivery:
   
    - It will allows frequent relases of s/w, through systematic automation of
        software -> creating -> testing -> deploy


   6. Decentralized Goveranace:
   
   - The focus is on using the right tool  for the respective services. Developers has the freedom to choose the best useful tools to solve their problem.

   7. Agility
   
      - Microservice support agile development that means any feature can be 
          develop quickly.


   Advantage of Microservices:
   ------------------------------
   1. Highperformance
   2. Independent Deployment
   3. Independent Development
   4. Fault Isolation
   5. Mixed Technology Stack
   6. Granular Scaling



------------------------------
