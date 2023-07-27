Simple way to setup a Eureka naming server

1. Add the @EnableEurekaServer to the main method class. 
2. Add the followering to the application.properties: 
	spring.application.name=naming-server
	server.port=8761
	eureka.client.register-with-eureka=false
	eureka.client.fetch-registry=false

Access the naming server locally by: http://localhost:8761

Additional, it might be necessary to add ONE of the followering configs to the client. 
	1. eureka.instance.prefer-ip-address=true
	2. eureka.instance.hostname=localhost
	
It is also necessary to add the client dependency to the client microservices. 

<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
</dependency>

Build Goal: spring-boot:build-image