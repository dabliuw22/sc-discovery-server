# Discovery Server

Servidor Discovery.

1. Pre-Requisitos:
	* Java >= 1.8.x
	* Spring Boot 2.0.3.RELEASE
	* Spring Cloud Finchley.RC2

2. Dependencias:
	* Actuator.
	* Cloud Discovery: Eureka Server.

```
	dependencies {
		compile('org.springframework.boot:spring-boot-starter-actuator')
		compile('org.springframework.cloud:spring-cloud-starter-netflix-eureka-server')
		testCompile('org.springframework.boot:spring-boot-starter-test')
	}
```

3. Anotar con *@EnableEurekaServer* a la clase de configuración.

4. Cambiar *application.properties* a *bootstrap.yml* y gregar configuración:
```[yaml]
server:
  port: ${PORT:8761}
  
spring:
  application:
    name: config-server

eureka:
  client:
    registerWithEureka: false
    fetchRegistry: false
```