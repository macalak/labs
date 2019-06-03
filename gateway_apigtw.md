# Spring Cloud Gateway
This project provides a library for building an API Gateway on top of Spring MVC. Spring Cloud Gateway aims 
to provide a simple, yet effective way to route to APIs and provide cross cutting concerns to them such as: 
security, monitoring/metrics, and resiliency.

## Implement Castle edge service using Spring Cloud Gateway
1. Include `org.springframework.cloud:spring-cloud-starter-gateway` Spring Boot starter into your application.
   Use the https://start.spring.io/ app and add dependency named as "Gateway"  
2. Being focused on routing requests, the Spring Cloud Gateway forwards requests to a 
   Gateway Handler Mapping – which determines what should be done with requests matching a specific route.
3. Route definition consists of:
  * Route – the primary API of the gateway. It is defined by a given identification (ID), a destination (URI) and set of predicates and filters
  * Predicate – a Java 8’s Predicate – which is used for matching HTTP requests using headers, methods or parameters
  *  Filter – a standard Spring’s WebFilter  
  Route all traffic to castle service:
```java
@Configuration
public class ApiGatewayConfiguration {
    @Bean
    public RouteLocator customRouteLocator(RouteLocatorBuilder builder) {
        return builder.routes()
                .route("castle", r -> r
                        .path("/**")
                        .uri("http://localhost:8091"))
                .build();
    }
}
```
4. You can use application.yml to define routes
5. Spring Cloud API Gateway also supports service discovery, so you do not have to use IP address in a route definition
   The route then looks like:
```java
return builder.routes()
                .route("castle", r -> r
                        .path("/**")
                        .uri("lb://castle"))
                .build();
```   

   
## References
* https://spring.io/projects/spring-cloud-gateway 
* https://cloud.spring.io/spring-cloud-gateway/single/spring-cloud-gateway.html




