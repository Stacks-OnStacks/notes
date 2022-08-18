# Introduction to Web

-   Basically a system of internet servers that support specially formated documents
    -   Client requests for some resources
    -   Requests is sent to a web server
    -   Web server responds to the request and sends information back to client
-   **Web & HTTP**
    -   HyperText Transfer Protocol
        -   clients and servers use on the web to communicate

# Web Services

-   A software system designed to support interoperable machine-to-machine interaction over network
    -   **In ENGLISH please**
        -   machiens tlake to one another
        -   More Specifically
            -   a collection of **open protocols** and **standards** used to exhange that data between applictions or systems
            -   This Connects:
                -   Soft applications that are written in various programming languages (polyglot)
                -   Can also be runnign on various platforms
                    -   ie Something on Google Cloud that needs to speak to a application on Microsoft Azure
-   Their **interoperablitiy**
    -   communication between differen programming languages
        -   Java & Python or Java & Javascript etc
    -   Windows & Linux
    -   due to the **open standards**
-   Web Services have two types of Architecture layout
    -   SOAP
        -   you've heard soap. That's all you need to know about SOAP
    -   **_REST_**
        -   THIS IS OUR FOCUS

# Client-Server Architecture

-   a networking model in which the server provides services to clients to perform user-based tasks.
-   A client and a server are two pieces of software that might be on the same computer, or two different computers that might be separated by miles but connected by the Internet.

-   **Server**

    -   A server is software designed to process requests
    -   deliver responses to another computer over the internet.

-   **Client**
    -   A client is a program that runs on a local machine requesting service from the server.

![Client-Server Architecture](https://digitalthinkerhelp.com/ezoimgfmt/i.ibb.co/QkvfjDh/cna.png?ezimgfmt=rs:364x218/rscb1/ng:webp/ngcb1)

-   **Protocol**
    -   establishing a connection between Client and a Server according to a set of rules
-   **HTTP protocol**.
    -   There are quite a few protocols for different purposes, but HTTP is the most popular
    -   Once the connection is established:
    -   the Client sends **HTTP Requests** to the server in the form of XML or JSON, which both entities (Client and Server) understand. After parsing the request, the Server responds with appropriate data by sending back an **HTTP Response**.

## Requests & Responses

-   _Requests_
-   are made by clients/end-users
    -   Body
    -   Method/Verb
        -   GET PUT POST PATCH DELETE
    -   URL
    -   HTTP Version
    -   Headers
        -   meta-data to provide information about the request
-   _Response_
-   are made by the server/database
    -   Body
    -   Headers
    -   status code

### Types of Client-Server Architecture

-   **2 tier architecture** -

    -   The user interface stored at the client machine and the database stored on the server.
    -   _fat client thin server architecture_.
        -   If Business Logic & Data Logic collected at a client-sidea
    -   _thin client fat server architecture_.
        -   If Business Logic & Data Logic handled on the server
    -   has some limitations in performance, security, and portability.

-   **3 tier architecture**

    -   Has a middleware between the user interface and database.
    -   **3 Tiers Names**
        -   _presentation tier_
            -   the front end layer and consists of the user interface
        -   _application tier_
            -   contains the functional business logic which drives an application’s core capabilities
        -   _data tier_
            -   consists of a database system and the data access layer.

-   **n-tier architecture** -
    -   There are multiple Business Logic & Data Logic layers.
    -   It increases the flexibility and reusability of applications
    -   can be difficult to implement.

## URI

-   **Uniform Resource Identifier**
    -   SUPERSET of URL
    -   Main aim is to find a resource and differentiate from other resources on your server
        -   Imagine filepath

## URL

-   **Uniform Resource Locator**
-   Subset of URI
-   Main aim is to get the location or address of a resource
-   URL is used to locate only web pages
-   ALL URLs can be URIs

## Verbs/Methods

-   REST requires the use of HTTP verbs/methods in specific ways
    -   _GET_
        -   this is simply to request information
        -   Generally speaking it will have an empty body
        -   Data is sent in header
        -   _NOT_ secured
        -   Analogous to a select statement in postgres
    -   _POST_
        -   This is used to create a new object/add completely new data entry into your database
        -   You **NEED** to provided information in the body
            -   Employee_name, employee_email, employee_dob etc etc
        -   it is secured
        -   large amounts of data can be sent
        -   Analogous to insert statements
    -   _PUT_
        -   used to update a complete resource
        -   Information should be in body
            -   generally speaking it's the whole of the record/class/models
            -   update every column the row has
        -   Analogous to updates in SQL
    -   _PATCH_
        -   Used to update a specific part of the resource
            -   single field for an object, not all of the components
            -   analogos to the update set column1,column2
        -   Requires a body (identifier and the columns you wish to update)
    -   **DELETE**
        -   removing the resources
        -   analogous to delete sql
        -   **use with caution** as with every delete
            -   for instance, you could constrain delte commands to your admin

# Status Codes

-   100's
    -   Information
-   200's
    -   Success!
    -   201 successfully created
-   300's
    -   Redirect
-   400's
    -   Client Error!
    -   404 Not Found
        -   say you provided ID 203, the highest ID is 200
    -   403 Forbidden
        -   meaning this user doesn't have the required permissions
    -   418 I'm a teapot
    -   451 unavailable due to government censorship
-   500's
    -   Server Error

# Safe vs Idempotent Verbs

-   Safe
    -   it should NEVER make any changes to the server
        -   GET
        -   should be able to run 1000s and it does nothing to the server
-   Idempotent
    -   same request will result in the same state of the server/database if you send multiple times
    -   No matter how many requests you send, the server will remain the same
        -   GET, DELETE, PUT, PATCH

# JSON

JavaScript Object Notation

-   faster parsing
-   more compatible w/ JavaScript
-   less verbose
-   more universal (tags won't change with different developers)

## Terminology

**Marshalling**: converting JSON to Java Objects

**UnMarshalling**: converting Java Objects to JSON

-   As seen below in the examples, first being JS followed by JSON.
-   This is an array of Objects for students.

```javascript
{
    students: [
        {
            firstName: "Veronica",
            lastName: "Jones",
            age: 29,
            isEnrolled: true,
        },
        {
            firstName: "Paul",
            lastName: "McCormick",
            age: 29,
            isEnrolled: true,
        },
        {
            firstName: "Lola",
            lastName: "Nunez",
            age: 29,
            isEnrolled: true,
        },
    ];
}
```

```JSON
{"students":[
    {
        "firstName":"Veronica",
        "lastName":"Jones",
        "age": 29,
        "isEnrolled": true
        },
    {
        "firstName":"Paul",
        "lastName":"McCormick",
        "age": 29,
        "isEnrolled": true
        },
    {
        "firstName":"Lola",
        "lastName":"Nunez",
        "age": 29,
        "isEnrolled": true
        }
]}
```

# Servlets

## Overview

-   A website can consist of both static and dynamic webpages.
    -   **Static webpage**
        -   pre-built HTML page with the content explicitly written into the code, and stored in the webserver.
        -   display the same content each time we visit.
    -   **Dynamic webpage**
        -   loads dynamic content such as stock prices, weather information, news, and sports updates at different points of time.
-   In Java, there exists a way to generate static webpages with dynamic data, and that's with
    -   **_Java Servlets_**.
        -   a Java class that takes incoming _requests_, _processes_ them, and generates a _response_ to send back to the user.
            -   For example, an HttpServlet
                -   takes an HTTP request
                -   processes its headers and content
                -   and uses that information to write HTML, CSS, and JavaScript code into an HTTP response that can be sent back to the user's browser
        -   **Servlet container**
            -   is the component of an application server that interacts with Java servlets
            -   is responsible for managing the execution of servlets and JSP pages for Java applications.
        -   Robust & Scalable
        -   Provides Interfaces & Classes

# How Servlets work

-   Client sends a request to the application server,
    -   the application server receives and passes the request to the appropriate servlet.
    -   The servlet
        -   processes the request
            -   generates the response
            -   sends the response back to the application server
    -   The _application server sends the response back to the client_
    -   _Most servlets are HTTPServlets_
        -   which receive HTTP requests
        -   generate HTTP Responses out of HTML, CSS, and JavaScript code

![Servlet Flow](https://javabeat.net/wp-content/uploads/2014/01/Servlet-Architecture.jpg)

-   **Web Servers / HTTP Servers**
    -   used to handle HTTP requests sent by a client
    -   return HTTP responses.
    -   They are designed to serve static files from a website (HTML files, images, etc).
-   **Application Servers / App Servers**
    -   can also handle HTTP requests, but they are not limited to just HTTP.
    -   They can be support other protocols such as RMI/RPC.
    -   Typically pass incoming requests to one of the applications running on them, using metadata in the request to decide which application will handle it.
    -   Most can double as Web Servers.

## Servlet Container

-   a component of some application servers that can interact with Java servlets.
-   Responsible for
    -   **managing the life-cycle** of servlets
    -   **mapping a URL** to a particular servlet
    -   ensuring that the URL requester has the correct access rights and many more such services.

![](https://www.programcreek.com/wp-content/uploads/2013/04/web-server.jpg)

-   The application server receives HTTP requests and forwards the request to the servlet container.
-   The servlet container determines which servlet is able to service this request.
-   Then the container invokes the servlet, which reads data in the request and formulates a response.
-   Then the application server returns the dynamically generated response to the Client.

## Lifecycle of Servlet

-   A **servlet container** manages the life cycle of a servlet.
-   [Servlet](https://docs.oracle.com/javaee/1.4/api/javax/servlet/Servlet.html) is an interface defined in **`javax.servlet`** package.
-   A servlet container uses the Servlet interface to understand a specific Servlet object and manage it.
-   There are three life cycle methods of a Servlet :
    -   `init()`
    -   `service()`
    -   `destroy()`
-   The steps involved in the servlet life cycle are listed below:

    -   **Step-1 : Loading of Servlet**

        -   When the application server (e.g. Apache Tomcat) starts up, the servlet container deploys and loads all the servlet classes.

    -   **Step-2 : Creating an instance of Servlet**

        -   Once all the Servlet classes are loaded, the servlet container creates only one instance for each servlet class.
        -   All requests to the servlet are executed on that same servlet instance.
        -   Some application servers can create multiple instances of a servlet to handle a high volume of incoming requests, but that is not the default behavior.

    -   **Step-3 : Invoke `init()` method once**
        -   Once all the servlet classes are instantiated, the init() method is invoked for each instantiated servlet.
        -   The `init()` method is used to initialize the servlet. The `init()` method is called only once.
    -   **The `init()` method signature:**
        ```java
        public void init() throws ServletException {
        }
        ```
    -   **Step-4 : Invoke `service()` method repeatedly for each client request**
        -   The servlet container calls the service method each time a request for the servlet is received. The service() method determines the type of Http request (GET, POST, PUT, DELETE, etc.) also calls `doGet()`, `doPost()`, `doPut()`, `doDelete()`, etc. methods as appropriate.
        -   **The `service()` method signature:**
            ```java
            public void service(ServletRequest req,ServletResponse resp) throws ServletException,IOException {
            }
            ```
    -   **Step-5 : Invoke destroy() method once**

        -   The `destroy()` method is called only once at the end of the a servlet's life. The servlet container calls this method before removing the servlet instance from the service.
        -   **The `destroy()` method signature:**

            ```java
            public void destroy() {
            }
            ```

    -   **Life Cycle of a Servlet:**

    ![LifeCycle](https://media.geeksforgeeks.org/wp-content/uploads/Life-Cycle-Methods-of-a-Servlet.jpg)

## Servlet API

-   The [Servlet API](https://docs.oracle.com/javaee/6/api/javax/servlet/package-tree.html)

    -   provides interfaces and classes that are required to build servlets.
    -   These interfaces and classes represented in two packages:

        1. **`java.servlet`** package - used by the servlet or web container.
        2. **`javax.servlet.http`** package - used for handling http requests.

## Servlet Class Hierarchy:

-   _Servlet interface_
    -   root interface of the servlet class hierarchy.
-   _GenericServlet Class_
    -   implements Servlet, ServletConfig, and Serializable interfaces.
-   _HttpServlet Class_

    -   extends the GenericServlet class
    -   implements the Serializable interface.
    -   Provides HTTP methods such as
        -   doGet
        -   doPost
        -   doHead
        -   doTrace
        -   etc.

-   **Java Servlet Class Hiearchy:**

```
   Servlet    ServletConfig       Serializable  {Built-in Interfaces}
     |             |                   |
     -----------------------------------
                    |
                    V
              GenericServlet                    {Built-in Class}
                    |
                    V
               HttpServlet                      {Built-in Class}
                    |
                    V
             UserDefinedServlet                 {User defined servlet Class}
```

-   The user defined servlet class is created by implementing the _Servlet_ interface, usually by extending the _GenericServlet_ class or (more commonly) the _HttpServlet_ class.

-   In order to initialize a Servlet, a server application loads the user-defined servlet class and creates an instance.
    -   Then it calls the Servlet’s `init (ServletConfig config)` method.
    -   Since the `init()` method is run once, it stores the initial parameters or configuration information in the _ServletConfig_ object.
-   This information can be retrieved later by calling the Servlet’s `getServletConfig()` method.
    -   This is implemented in the _GenericServlet_ class definition.
    -   The _ServletConfig_ object contains Servlet parameters and a reference to the Servlet’s _ServletContext_.
    -   The **ServletContext** is an interface which helps to communicate with other servlets.
    -   Then, the `service (ServletRequest request, ServletResponse response)` method is called for every request to the Servlet.
-   When the Servlet needs to be unloaded the `destroy()` method is called.

## Creating a Custom Servlet using Maven

-   The steps for creating a custom servlet using the maven are as follows:

    -   Create a new Maven project in Eclipse by clicking :

        -   File -> New -> Project and select Maven Project from the list.
        -   _(If you do not see Maven Project, select Other then search for Maven)_

    -   Select `Create a simple project (skip archetype selection)`, then click `Next`.

![simpleproject](./images/custom-servlet-1.png)

-   Enter the `Group Id` and `Artifact Id`. Change `packaging` to `war`. - Click `Finish`.

![changepackaging](./images/custom-servlet-2.png)

-   After the Maven project is created

    -   the project will have an error marked with red.
    -   To fix that error, right-click on the project -> Java EE Tools -> Generate Deployment Descriptor Stub.

-   The Deployment Descriptor Stub, also referred to as the `web.xml` can be found in your `WEB-INF folder`.

![webinffolder](./images/custom-servlet-3.png)

-   Right click on the project -> Build Path -> Add Libraries.

-   Click on `Server Runtime` -> Next -> `Apache Tomcat v9.0` -> Finish.

-   If you right click on the project -> Properties -> Java Build Path,
    -   under the `Libraries` tab you should see that `Apache Tomcat v9.0[Apache Tomcat v9.0]` has now been added.

![libraries](./images/custom-servlet-4.png)

-   To create a new servlet class, right-click on `src/main/java` -> New -> Package. Enter the Java package name.

-   Then, right click on this package -> New -> Class. This class will extend `HttpServlet`.

-   Alternatively,

    -   Right click on this package -> New -> Other -> Search for Servlet and click Next. Ensure that this Servlet class extends `javax.servlet.http.HttpServlet` as the Superclass.

-   Configuring and running the servlets are discussed in the next module.

## Web application directory structure

-   To get a Java web server or servlet container to run your Java web application, you need to package the resources inside it (servlets, JSP's, etc.) in a standardized way shown below.

![directory structure](./images/directorystructure.gif)
