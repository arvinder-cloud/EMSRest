Spring Boot Rest API

EmsRestApplication is restful webservice built on spring boot and contains set following api opertaions...

For enabling XML representations, Jackson XML extension (jackson-dataformat-xml) must be present on the classpath. Add the following dependency to your project:
<dependency>
    <groupId>com.fasterxml.jackson.dataformat</groupId>
    <artifactId>jackson-dataformat-xml</artifactId>
</dependency>

Following technologies stack being used:

    Spring Boot 1.4.3.RELEASE
    Spring 4.3.5.RELEASE [transitively]
    Maven 3.1
    JDK 1.8
    Eclipse MARS.1

This is what our REST API does:

    GET request to /api/user/ returns a list of users
    GET request to /api/user/1 returns the user with ID 1
    POST request to /api/user/ with a user object as JSON creates a new user
    PUT request to /api/user/3 with a user object as JSON updates the user with ID 3
    DELETE request to /api/user/4 deletes the user with ID 4
    DELETE request to /api/user/ deletes all the users



#########################################################

1) Get the list of all users

2) Retrieve particular user

3) Try to retrieve user which does not exist

4) Create a new User

5. Create a User with an existing user-name

6. Update an existing user

7. Delete an existing user

8. Delete all users

#################################################################################################################

Detailed Explanation :

@RestController : First of all, we are using Spring 4’s new @RestController annotation.
 This annotation eliminates the need of annotating each method with @ResponseBody. 
Under the hood, @RestController is itself annotated with @ResponseBody, 
and can be considered as combination of @Controller and @ResponseBody.

@RequestBody : If a method parameter is annotated with @RequestBody, 
Spring will bind the incoming HTTP request body(for the URL mentioned in @RequestMapping for that method) 
to that parameter. While doing that, Spring will [behind the scenes] use HTTP Message converters 
to convert the HTTP request body into domain object [deserialize request body to domain object], based on ACCEPT or Content-Type header present in request.

@ResponseBody : If a method is annotated with @ResponseBody, 
Spring will bind the return value to outgoing HTTP response body. While doing that, Spring will [behind the scenes] 
use HTTP Message converters to convert the return value to HTTP response body [serialize the object to response body], 
based on Content-Type present in request HTTP header. As already mentioned, in Spring 4, you may stop using this annotation.

ResponseEntity is a real deal. It represents the entire HTTP response. 
Good thing about it is that you can control anything that goes into it. You can specify status code, headers, and body.
 It comes with several constructors to carry the information you want to sent in HTTP Response.

@PathVariable This annotation indicates that a method parameter should be bound to a URI template variable [the one in ‘{}’].

Basically, @RestController , @RequestBody, ResponseEntity & @PathVariable are all you need to know to implement a REST API in Spring.
Additionally, spring provides several support classes to help you implement something customized.

MediaType : Although we didn’t, with @RequestMapping annotation, you can additionally,
specify the MediaType to be produced or consumed (using produces or consumes attributes) by that particular controller method, 
to further narrow down the mapping.

###########################Testing the API##########################################################

To test this API, i will use an external client POSTMAN (An extension from CHROME).

############################################################################################################

Details of the RestAPI's is provide under filename : API-calls_details.txt

Postman collection export is available under file : EmsRestApplication-Postman.postman_collection.json

