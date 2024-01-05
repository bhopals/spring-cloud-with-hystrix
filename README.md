## Introduction
Spring Cloud and Netflix's Hystrix project to help protect service clients from failing or poorly behaving services.  

The concepts of fail-fast service calls, bulkheads and fallbacks for when a client call fails.  

### Project Details:

1.  A Spring Cloud Config server that is deployed as Docker container and can manage a services configuration information using a file system or GitHub-based repository.

2.  A Eureka server running as a Spring-Cloud based service.  This service will allow multiple service instances to register with it.  Clients that need to call a service will use Eureka to lookup the physical location of the target service.

3.  A organization service that will manage organization data used within EagleEye.

4.  A licensing service that will manage licensing data used within EagleEye.

5.  A Postgres SQL database used to hold the data for these two services.


### There are four client resiliency patterns:

- 1. Client-side load balancing

   - The service client caches microservice endpoints retrieved during service discovery.

- 2. Circuit breakers

   - The circuit breaker pattern ensures that a service client does not repeatedly call a failing service.

- 3. Fallbacks

   - When a call does fail, fallback asks if there’s an alternative that can be executed.

- 4. Bulkheads

   - The bulkhead segregates different service calls on the service client to ensure a poor-behaving service does not use all
    the resources on the client.


- The four client resiliency patterns act as a protective buffer between a service consumer and the service.



### Software needed

1.	Apache Maven (http://maven.apache.org)
2.	Docker (http://docker.com)
3.	Git Client (http://git-scm.com)


### Building the Docker Images


Run the following maven command.  


   **mvn clean package docker:build**



### Running the services



   **docker-compose -f docker/common/docker-compose.yml up**

