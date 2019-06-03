# Feign declarative REST API client
Feign supports declarative REST service client implementation. It works with Netflix OSS libraries
as [Hystrix](https://github.com/Netflix/Hystrix), [Ribbon](https://github.com/Netflix/ribbon) and
[Eureka](https://github.com/Netflix/eureka) client. You just define interface and use Java annotations.

## Implement Castle edge service using Feign
1. Include `spring-cloud-starter-openfeign` Spring Boot starter into your application.
2. Add _@EnableFeignClient_ annotation into SpringBoot application configuration class
3. Define client interface and use annotation _@FeignClient_ You should provide client name.
   Spring auto configures also Netflix Ribbon with client side load balancing. Ribbon will use
   Netflix Eureka client to discover service addresses, if Eureka client is enabled. You can
   configure Ribbon manually in _application.properties_.
4. You can implement your own Decoders/Encoders and other Feign components
5. Now, implement the client facing REST API which calls Feign client interface 
   It should be the @RestController which redirects the request handling to Feign client
   You can include the data transformation as well.
   
 





