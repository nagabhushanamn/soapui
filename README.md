# soapui



'No Software is alone now'



The term web service is either

(generic) a service offered by an electronic device to another electronic device, communicating with each other via the World Wide Web, or
(specific) a web service implemented in the particular technology or brand, W3C Web Services.




SOA architecture came advantages 
    
Reusability

Better scalability

Platform independency

Business agility

Enhanced security


But there are also disadvantages:

Increased response time

Service management effort is high

Implementation cost is high





Web Services - How to implement ?



2 approaches widely used now 

1. SOAP protocol & standards
2. REST constraints/patterns/styles









These constraints restrict the ways that the server may process and respond to client requests so that, by operating within these constraints, the service gains desirable non-functional properties, such as performance, scalability, simplicity, modifiability, visibility, portability, and reliability.
If a service violates any of the required constraints, it cannot be considered RESTful.


Client–server architecture
Separating the user interface concerns from the data storage concerns improves the portability of the user interface across multiple platforms.
Statelessness
The client–server communication is constrained by no client context being stored on the server between requests
Cache-ability
As on the World Wide Web, clients and intermediaries can cache responses
Layered system
A client cannot ordinarily tell whether it is connected directly to the end server, or to an intermediary along the way.
Code on demand (optional)
Servers can temporarily extend or customize the functionality of a client by transferring executable code.
Uniform interface
The uniform interface constraint is fundamental to the design of any REST service.It simplifies and decouples the architecture, which enables each part to evolve independently.

The four constraints for this uniform interface are:

Resource identification in requests
Individual resources are identified in requests, for example using URIs in Web-based REST systems. The resources themselves are conceptually separate from the representations that are returned to the client. For example, the server may send data from its database as HTML, XML or JSON, none of which is the server's internal representation.

Resource manipulation through representations
When a client holds a representation of a resource, including any metadata attached, it has enough information to modify or delete the resource.

Self-descriptive messages
Each message includes enough information to describe how to process the message. For example, which parser to invoke may be specified by a media type

Hypermedia as the engine of application state (HATEOAS)





Applied to Web services

a base URL, such as http://api.example.com/resources;
a media type that defines state transition data elements.The current representation tells the client how to compose requests for transitions to all the next available application states. This could be as simple as a URL 
standard HTTP methods (e.g., OPTIONS, GET, PUT, POST, and DELETE).[16]


Relationship between URL and HTTP methods



Rules for ‘REST API’ Design

 

URI Format : URI = scheme "://" authority "/" path [ "?" query ] [ "#" fragment ]



File extensions should not be included in URIs



The URI path conveys a REST API’s resource model

http://api.soccer.restapi.org/leagues/seattle/teams/trebuchet

http://api.soccer.restapi.org/leagues/seattle/teams

http://api.soccer.restapi.org/leagues/seattle

http://api.soccer.restapi.org/leagues

http://api.soccer.restapi.org 



URI Query Params

The query component of a URI may be used to filter collections or stores

GET /users
GET /users?role=admin

GET /users?pageSize=25&pageStartIndex=50





HTTP - Methods

GET must be used to retrieve a representation of a resource

HEAD should be used to retrieve response headers

PUT must be used to both insert and update a stored resource

PUT must be used to update mutable resources

POST must be used to create a new resource in a collection

POST must be used to execute controllers

DELETE must be used to remove a resource from its parent

OPTIONS should be used to retrieve metadata that describes a resource’s available interactions










https://developer.mozilla.org/uk/docs/Web/HTTP/Methods

https://developer.mozilla.org/en-US/docs/Web/HTTP/Status


REST API documentation tools

https://swagger.io/

demo : a quick play with RESTful services





SOA testing tools

Comparative Analysis:

S.No

Factors

SoapUI

SaopUI PRO

ITKO LISA

SOA Parasoft

1

Cost

Open source

400 $/License

Highly Costly

Highly Costly

2

Multilayer testing

Yes

Yes

Yes

Yes

3

Scripting support

Yes

Yes

Yes

Yes

4

Protocol support

Yes

Yes

Yes

Yes

5

CI support

Yes

Yes

Yes

Yes

6

Ease of use

8/10

9/10

9/10

9/10

7

Learning curve

8/10

8/10

6/10

6/10



SoapUI and SoapUI Pro to be the first choice for Test Architects and Test Managers for their projects.

SoapUI & SoapUI Pro are from the same family, Eviware, which is now SmartBear. 


Here is a quick comparison:

Criteria

SoapUI

SoapUI Pro

Reporting

Very limited, no rich reporting

Reports are available in different formats

XPath Builder

Not Available

Available

Data source

Not Available

Multiple options for data sources available

Data sink

Not Available

Available

XQuery Builder

Not Available

Available


The additional functionality that is available in SoapUI Pro can be achieved by SoapUI using Groovy script. 

To sum up everything that is given as UI functionality in SoapUI PRO is achievable with little effort in SoapUI which finally makes SoapUI open source the preferred choice for tool pickers.


SoapUI provides the following testing features to the test team
Functional testing [manual]

Function test automation

Performance testing

Security testing

Web service interoperability testing


Apart from these, SoapUI is also capable of integration with the following:

LoadUI for advanced performance testing

Selenium for multilayer testing

Jenkins for continuous integration

HP QC for end-to-end test automation management and execution


Note: SoapUI has a comparatively simple architecture as compared to other tools in the SOA testing world.




SoapUI architecture


Test config files: Files which require power to test this includes test data, expected results, database connection variables and any other environmental or test specific details.

Third-party API: Third-party API helps create an optimised test automation framework example. JExcel API to help integrate with Microsoft Excel to create a data driven framework.

Selenium: Selenium JARs to be used for UI automation.

SoapUI Runner: This is used to run the SoapUI project and is a very useful utility for test automation as it allows you to run the test from the command line and acts as a trigger for test automation.

Groovy: This library is used to enable SoapUI to provide its users with groovy as a scripting language.

Properties: Test request properties to hold any dynamically generated data. We also have Test properties to configure SSL and other security configurations for test requests.

Test Report: SoapUI provides a Junit style report and user Jasper reporting utility for reporting of test results.

Test architecture in detail

SoapUI Architecture is composed of many key components which help provide the users of SoapUI with advanced functionality like virtualization, XPath, invoking services with JMS endpoints, logging, and debugging.

Jetty: Service virtualization/mock services

We can create replicas of services in cases where the service is not ready or buggy to test. In the meantime, we want to create our test cases, for that we can use service virtualization or mocking and use that service.

Jetty is used for hosting virtual services.

Provided by Eclipse, Java based web server.

Works for both SOAP and Rest.


Jasper:

Is used to generate reports

Open source reporting tool


Saxon XSLT and XQuery processor:

We can use Path and XQuery to process service results

The Saxon platform provides us with the option to process results using Path and XQuery


Log4J:

Used for logging

Provides SoapUI, error, HTTP, Jetty, and memory logs


JDBC driver:

To interact with different databases we would need the respective drivers



Hermes MS:

Is used in applications where high volume of transactions take place

It is used to send messages to the JMS Queue

Receiver results from the JMS Queue

We can incorporate Java JMS using Hermes JMS


Scripting language:

We can choose with Groovy or JavaScript

We can select language for each project

We can set language at project property level


Monitoring:

To check what is sent to the service and what is received from the service


Runners:

Execution can be run without using SoapUI

Run from the command line

Test runner

LoadTestRunner

SecurityTestRunner

MockServiceRunner

Can also be executed from build tools such as Jenkins



Test approaches in SOA testing


Approaches to test SOA architecture are usually based on the scope of the project and requirements to test


Functional testing

Performance testing

Security testing

Boundary attack

Cross-site scripting

XPath injection

SQL injection

Malformed XML

XML bomb

Malicious attachment


SoapUI's security testing functionality provides scans for every attack type and also, if you want to try a custom attack on the service by writing a custom script.

So the scans provided by SoapUI are as follows:

Boundary scan

Cross-site scripting scan

XPath injection scan

SQL injection scan

Malformed XML scan

XML bomb scan

Malicious attachment scan

Fuzzing scan

Custom script




Hands on



site
https://www.soapui.org/

download and install
https://www.soapui.org/downloads/soapui.html


Getting Started with SoapUI

create new REST-project from menu  with resource URI :

         http://petstore.swagger.io/v2/pet/findByStatus?status=available
          
Understanding REST Parameters

You use request parameters to set varying parts in simulated requests. SoapUI supports the following parameter types:

QUERY
TEMPLATE
HEADER
MATRIX
QUERY Parameters
QUERY parameters appear in the URL after the question mark (?) after the resource name:

https://myserver.com/resource-name?param1=value1&param2=value2


HEADER Parameters
HEADER parameters are passed in the headers of outgoing requests:


TEMPLATE Parameters
These parameters appear in resource paths. They give API developers a flexible way of parameterizing resources:

http://myserver.com/some-path/parameter/path-continued/parameter2

http://petstore.swagger.io/v2/store/order/1


MATRIX Parameters
These parameters also go in the request URL. They reside between the resource path and QUERY parameters, and are separated from the resource path by a semicolon (;):


PLAIN Parameters
SoapUI also uses the PLAIN parameters. These parameters are present in the request editor, but SoapUI does not include them into simulated requests. 


Parameter Level: RESOURCE and METHOD
In SoapUI editors, you can define parameters at the RESOURCE or METHOD level:





Working With REST Services
    

by resource URI
by swagger
by WADL

Items of the REST service project:


The project (Project1)
The REST service (My Sample IOT API)
Resource nodes (/connectors, /devices, /lighting/dimmers/{deviceId}/{value}, and so on)
Method definitions (getDevices, setDimmer)
A default request generated by SoapUI for a method (Request 1)



Functional API Testing    ( on shop api )

1. Create a test from a request
2. Add an Assertion to the test
3. Run a Test

Structuring and Running Tests

1. Test Structure
SoapUI structures functional tests into three levels; TestSuites, TestCases and TestSteps.

A TestSuite is a collection of TestCases that can be used for grouping functional tests into logical units. Any number of TestSuites can be created inside a soapUI project to support massive testing scenarios.
A TestCase is a collection of TestSteps that are assembled to test some specific aspect of your service(s). You can add any number of TestCases to a containing TestSuite and even modularize them to call each other for complex testing scenarios.
TestSteps are the "building blocks" of functional tests in soapUI. They are added to a TestCase and used control the flow of execution and validate the functionality of the service(s) to be tested.
2. Test Execution
TestSuites and TestCases these can be executed either in sequence or parallel

The execution order of TestSteps in a TestCase is always in the order they are displayed, branching/looping can be achieved with dedicated test-steps or scripts.
3. Test Output

Working with TestSteps

TestSteps are the core building blocks of functional tests in soapUI; each TestStep performs some step for validating the functionality to be tested.

TestSteps are by default executed sequentially, but several possibilities exist for branching, looping and even calling other TestCases, making complex testing possible when required.

Any number of TestSteps can be added to a TestCase; add them by either right clicking in the TestStep list and selecting add/insert or by pressing the corresponding TestStep button in the TestCase window:



Validating Messages ( Assertions )

 Assertion categories

Property Content Category

Contains - Searches for the existence of a string token in the property value, supports regular expressions. Applicable for any property.
Message Content Assertion - Allows for complex content validation of XML messages. Applicable to any property containing XML.
Not Contains - Searches for the non-existence of a string token in the property value, supports regular expressions. Applicable to any property.
XPath Match - uses an XPath expression to select content from the target property and compares the result to an expected value. Applicable to any property containing XML.
XQuery Math - uses an XQuery expression to select content from the target property and compares the result to an expected value. Applicable to any property containing XML.Compliance, Status and Standards

Compliance, Status and Standards
Script
SLA
JMS
JDBC
Security


Validating XML Messages

XPath Match Assertion
    
declare namespace sam='http://www.example.org/sample/';
//sam:loginResponse[1]


- for content
- wildcards
- count
- for existence .    exist(//xpath)
- for content matching with RegEx .  matches(//xpath,'pattern')

The XQuery Match Assertion

<Result>
    for $v in /item
    order by $v/price
    return <price>{data($v/price/text())}</price>
</Result>     

Validating JSON Messages


JsonPath Assertions

JsonPath Count uses a JsonPath expression to count the occurrences of an element. Applicable to any property containing JSON.

JsonPath Existence Match

JsonPath Existence Match uses a JsonPath expression to select content from the target property and compares the result to an expected value. Applicable to any property containing JSON.

JsonPath Match

JsonPath Match uses a JsonPath expression to select content from the target property and compares the result to an expected value. If the values match the assertion passes, otherwise it fails. Applicable to any property containing JSON.

JsonPath RegEx Match

JsonPath RegEx Match uses a JsonPath expression to select content from the target property and compares the result to a specified Regular Expression. Applicable to any property containing JSON.


Using Script Assertions

The Script-Assertion allows for arbitrary validation of a message, which included message content, HTTP headers, etc. Validation scripts are written in the project scripting language (Groovy or JavaScript) and are executed whenever the assertion-status of the containing sampler TestStep is updated. Add a Script Asssertion to your TestStep with the standard "Add Assertion" button;


1. Validate the content of an HTTP Header in the response

// check for the amazon id header
assert messageExchange.responseHeaders["x-amz-id-1"] != null
2. Validate a certain response time

// check that response time is less than 400 ms
assert messageExchange.timeTaken < 400
3. Validate the existence of an attachment in the response

// check that we received 2 attachments
assert messageExchange.responseAttachments.length == 2
4. Validate the existence of a specific XML element in the response

// check for RequestId element in response
def holder = new XmlHolder( messageExchange.responseContentAsXml )

assert holder["//ns1:RequestId"] != null



Controlling Flow
By using the Conditional Goto TestStep
By creating a Script TestStep that does this for you
Modularizing your Tests
If your Test Scenarios get increasingly complex, you might want to share a number of TestSteps between different TestCases, maybe for setting up some prerequisites (logging in, etc) or for performing certain steps in different contexts. As always, there are several ways to achieve this in SoapUI;
By using a "Run TestCase" TestStep to execute other TestCases
By creating a Script TestStep and using the SoapUI API to execute desired TestSteps, TestCases, etc.

Using Scripts for Modularization

import com.eviware.soapui.model.testsuite.TestRunner.Status

// get TestCase

def tc = testRunner.testCase.testSuite.project.testSuites["Sample Simple TestSuite"] .testCases["Simple Login and Logout w. Properties Steps"]

// set login properties tc.setPropertyValue("Username", "ole" ) tc.setPropertyValue("Password", "nomoresecrets" )

// run test synchrouously def runner = tc.run( null, false )

// show that it worked out ok log.info "Status: $runner.status, time taken for TestCase was: $runner.timeTaken ms"

// assert that it didn't fail assert runner.status != Status.FAILED : runner.reason






Working with Scripts


Scripting is a central aspect of SoapUI, allowing you to tailor the behavior of your Test execution to your specific needs. Within the scope of a functional testing, the following scripting possibilities are available:



Script TestSteps in a TestCase.
Setup and TearDown scripts at the Project, TestSuite and TestCase level.
Script PropertyExpansions in any context being evaluated during Test execution.
Project-level Event Handlers for events related to Test Execution. 

The Script TestStep
The Script TestStep is the most powerful TestStep in SoapUI, in the sense that it allows you to do more or less whatever you might need to within the execution of your Tests. The contained script will be executed each time the TestStep is run and can do more or less anything possible with the built in API's available (JRE, SoapUI, all dependencies, etc).





testRunner - a TestCaseRunner object (javadoc), which is the entry-point to the SoapUI API for accessing project items, results, etc. The TestRunner is the object that is actually executing the TestCase by cycling through the TestSteps in the TestCase and executing them. It exposes methods related to test execution and the underlying object model (via the testCase property). Common usage scenarios are:
using testRunner.testCase to get hold of the containing TestCase from which all other objects in the project can be accessed and manipulated.
using testRunner.fail(...) (or testRunner.cancel) to abort the ongoing TestCase when an error occurs.
using testRunner.gotoStepByName(...) or testRunning.runTestStepByName( ... ) to transfer execution to another step than the one after the Script TestStep in the TestCase.
context - a TestCaseRunContext object (javadoc) holding context-related properties. The main usage for this is to store values that can be used in subsequent TestSteps or related scripts. For example

Setup and TearDown Scripts



Working with Properties


In Functional Testing properties are used to parameterize the execution and functionality of your tests, for example:

Properties can be used to hold the endpoints of your services, making it easy to change the actual endpoints used during test execution (see example below).
Properties can be used to hold authentication credentials, making it easy to manage these in a central place or external file.
Properties can be used to transfer and share session ids during test execution, so multiple teststeps or testcases can share the same sessions.
etc.




day-2 : 


              


              








    



















       


















