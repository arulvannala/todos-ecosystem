## Todo(s) Ecosystem of Microservices

Each of these Microservices can be developed and deployed individually or as an EcoSystem of Microservices.

EcoSystem Goals:

1. Highlight [Spring Boot](https://spring.io/projects/spring-boot) Microservices on [Pivotal Application Service](https://pivotal.io/platform/pivotal-application-service)  
1. Demo by doing  
1. Proving ground

### Part(s)

The Ecosystem is divided into smaller parts, each highlighting specific features of [Spring Boot](https://spring.io/projects/spring-boot), [Spring Cloud](https://projects.spring.io/spring-cloud/) and [Pivotal Application Service](https://pivotal.io/platform/pivotal-application-service).  Feel free to clone and play around with [each one](#apps) individually or work through these Part(s) which builds out the EcoSystem on the [Cloud](https://run.pivotal.io/).

#### Build and Deploy  


1. [Todo(s) Base Set](PART_1.md) - cf push...awe yeah :sunglasses:
2. [Spring Cloud](PART_2.md) - Spring Cloud stack
3. [Todo(s) Data](PART_3.md) - Todo(s) Data to enable SQL persistence
4. [Todo(s) Cache](PART_4.md) - Todo(s) Cache to enable Redis caching
5. [Todo(s) CQrS](PART_5.md) - Todo(s) CQrS implementation

### Apps

App | Description | Local Port | PAS enabled
------------ | ------------- | ------------- | -------------  
[todos-ui](https://github.com/corbtastik/todos-ui) | todomvc.com Vue.js frontend Todo(s) UI | 4040 | [yes](https://github.com/corbtastik/todos-ui#run-on-pas)

### JVM Microservices

Microservice | Description | Local Port | PAS enabled
------------ | ------------- | ------------- | -------------  
[todos-gateway](https://github.com/corbtastik/todos-gateway) | Todo(s) API gateway featuring Zuul | ``9999`` | [yes](https://github.com/corbtastik/todos-gateway#run-on-pas)
[todos-api](https://github.com/corbtastik/todos-api) | Todo(s) REST API in Spring Boot 2.0 | ``8080`` | [yes](https://github.com/corbtastik/todos-api#run-on-pas)  
[todos-restclient](https://github.com/corbtastik/todos-restclient) | Todo(s) HTTP Client, used to call Todo(s) API(s) | ``8006`` | [yes](https://github.com/corbtastik/todos-restclient#run-on-pas)  
[todos-command](https://github.com/corbtastik/todos-command) | Todo(s) CQRS impl, command pattern, Spring Boot w/ Spring Cloud Streams | ``8001`` | [yes](https://github.com/corbtastik/todos-command#run-on-pas)  
[todos-query](https://github.com/corbtastik/todos-query) | Todo(s) CQRS impl, query pattern, Spring Boot w/ Feign Client | ``8005`` |  [yes](https://github.com/corbtastik/todos-query#run-on-pas) 
[todos-cache](https://github.com/corbtastik/todos-cache) | Todo(s) cache, Spring Boot w/ Spring Data Redis and Spring Cloud Streams | ``8002``  | [yes](https://github.com/corbtastik/todos-cache#run-on-pas)
[todos-data](https://github.com/corbtastik/todos-data) | Todos(s) Data Microservice, using Spring Boot JPA and Spring Data REST | ``8003`` | [yes](https://github.com/corbtastik/todos-data#run-on-pas)
[todos-webflux](https://github.com/corbtastik/todos-webflux) | Todo(s) REST API in Spring Boot 2.0 WebFlux for non-blocking endpoints |
[todos-webclient](https://github.com/corbtastik/todos-webclient) | Todo(s) Reactive HTTP Client, used to call Todo(s) API(s) |  
[todos-source](https://github.com/corbtastik/todos-source) | Todo(s) Event Driven Source Microservice in Spring Cloud Streams |  
[todos-sink](https://github.com/corbtastik/todos-sink) | Todo(s) Event Driven Sink Microservice in Spring Cloud Streams |  
[todos-kotlin](https://github.com/corbtastik/todos-kotlin) | Kotlin implementation of Todo(s) REST API with Spring Boot 2.0 Reactive Stack |  

### Non JVM Microservice

Non JVM Microservice | Description | Local Port
------------ | ------------- | -------------
[todos-nodejs](https://github.com/corbtastik/todos-nodejs) | Todo(s) REST API in Node.js w/ Express.js | 

### Spring Cloud Support

Spring Cloud component | Description | Local Port
------------ | ------------- | -------------
[config-server](https://github.com/corbtastik/config-server) | Spring Cloud Config Server, used to host external config for ecosystem | 8888
[cloud-index](https://github.com/corbtastik/cloud-index) | Spring Cloud Netflix Eureka Server, used for Service Discovery | 8761

### Build, Release, Run

CI/CD | Description
------------ | -------------
[todos-cicd](https://github.com/corbtastik/todos-cicd) | Build, Release and Run scripts for local and cloud deployment of the ecosystem

### Spring Cloud Support

Each JVM based Microservice taps into the power of Spring Cloud which you'll need if you're deploying Microservices on a Macro scale.

Each Microservices uses these Spring Cloud Dependencies

* Spring Cloud Config Client for Centralized Config
* Spring Cloud Eureka Client for Service Discovery
* Spring Cloud Sleuth for Tracing

And a few such as the Spring Cloud Streams and Spring Data Microservices use Hystix

* Spring Cloud Hystrix for Circuit Breaking
