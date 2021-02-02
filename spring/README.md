[Back](../README.md)

# Spring questions

## What parts of Spring you used

  - Spring IoC
  - SpringBoot
  - Spring AOP
  - Spring Web Services (RestController) / actuator
  - Spring Data / Spring Data JPA
  - Spring Security

## Spring Bean Lifecycles

  - Bean Definition
  
Spring Bean will be defined using stereotype annotations or XML Bean configurations.

  - Bean Creation and Instantiate

As soon as bean created and It will be instantiated and loaded into ApplicationContext and JVM memory.

  - Populating Bean properties

Spring container will create a bean id, scope, default values based on the bean definition.

  - Post-initialization

Spring provides Aware interfaces to access application bean meta-data details and callback methods to hook into the bean life cycle to execute custom application-specific logic.

  - Ready to Serve

Now, Bean is created and injected all the dependencies and should be executed all the Aware and callback methods implementation. Bean is ready to serve.

  - Pre-destroy

Spring provides callback methods to execute custom application-specific logic and clean-ups before destroying a bean from ApplicationContext.

  - Bean Destroyed

Bean will be removed or destroyed from and JVM memory.

## Spring Bean Scopes

  - singleton (default*)

Scopes a single bean definition to a single object instance per Spring IoC container.

  - prototype

Scopes a single bean definition to any number of object instances.

  - request

Scopes a single bean definition to the lifecycle of a single HTTP request; that is each and every HTTP request will have its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring ApplicationContext.

  - session

Scopes a single bean definition to the lifecycle of a HTTP Session. Only valid in the context of a web-aware Spring ApplicationContext.

  - global session

Scopes a single bean definition to the lifecycle of a global HTTP Session. Typically only valid when used in a portlet context. Only valid in the context of a web-aware Spring ApplicationContext.
