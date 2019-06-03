# Gateway module
The Gateway module usually publish REST API endpoint, or other interface to a client and hides
underlying backend module interface. It is a simple passthrough proxy, or it can adapts internal
API to outside world. Spring framework supports several approaches for the Gateway implementation:

* [REST Template](https://spring.io/guides/gs/consuming-rest/)
* [Feign client with Netflix stack](https://cloud.spring.io/spring-cloud-netflix/multi/multi_spring-cloud-feign.html)
* [Netflix Zuul](https://github.com/Netflix/zuul)
* [API Gateway](https://spring.io/projects/spring-cloud-gateway) 
  



