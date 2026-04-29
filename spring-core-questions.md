# 🌱 Spring Core Interview Q&A (1–100)


# 🔹 BASICS

### 1. What is the Spring Framework and why is it used?
Spring is a lightweight Java framework used to build enterprise applications. It provides features like dependency injection, transaction management, and modular architecture. It is mainly used to reduce tight coupling, remove boilerplate code, and improve testability and scalability.

---

### 2. What are the main modules of Spring Framework?
Spring consists of multiple modules:
- Core Container (Beans, Context, Core)
- AOP
- Data Access (JDBC, ORM)
- Web (MVC, REST)
- Test  
Each module focuses on a specific responsibility, making Spring modular and flexible.

---

### 3. What is Inversion of Control (IoC)?
IoC is a principle where object creation and dependency management are handled by the Spring container instead of the developer. This removes manual object creation and improves decoupling.

---

### 4. What is Dependency Injection (DI)?
DI is the implementation of IoC where dependencies are injected into a class instead of being created inside it. This improves flexibility and makes unit testing easier.

---

### 5. What are the types of Dependency Injection in Spring?
- Constructor Injection (preferred)
- Setter Injection  
Constructor injection ensures required dependencies and supports immutability.

---

### 6. What is a Spring Bean?
A Spring Bean is an object that is created, configured, and managed by the Spring container.

---

### 7. What is a Spring IoC container?
It is the core component that manages beans, injects dependencies, and controls the lifecycle of objects.

---

### 8. What are the types of IoC containers in Spring?
- BeanFactory (basic, lazy loading)
- ApplicationContext (advanced, widely used)

---

### 9. What is the difference between BeanFactory and ApplicationContext?
BeanFactory uses lazy initialization and provides basic features.  
ApplicationContext uses eager initialization and supports AOP, events, and internationalization.

---

### 10. What is the role of ApplicationContext in Spring?
It loads configurations, creates beans, injects dependencies, and manages the entire lifecycle of the application.

---

# 🔹 BEAN & CONFIGURATION

### 11. What is bean configuration in Spring?
It defines how beans are created, configured, and connected with other beans in the application.

---

### 12. What are the different ways to configure beans in Spring?
- XML configuration  
- Annotation-based configuration  
- Java-based configuration  

---

### 13. What is XML configuration in Spring?
Beans are defined using `<bean>` tags in XML files. It is older and less used in modern applications.

---

### 14. What is annotation-based configuration?
Uses annotations like `@Component` and `@Autowired` to automatically configure beans.

---

### 15. What is Java-based configuration?
Uses `@Configuration` and `@Bean` to define beans in Java classes instead of XML.

---

### 16. What is @Configuration annotation?
It marks a class as a configuration class that contains bean definitions.

---

### 17. What is @Bean annotation?
It defines a bean inside a configuration class and is managed by Spring.

---

### 18. What is component scanning?
Spring automatically scans packages to find classes annotated with stereotypes and registers them as beans.

---

### 19. What is @Component annotation?
It marks a class as a Spring-managed bean.

---

### 20. Difference between @Component, @Service, and @Repository?
All are stereotype annotations:
- @Component → generic
- @Service → business logic
- @Repository → data access (with exception handling support)

---

# 🔹 DEPENDENCY INJECTION & AUTOWIRING

### 21. What is autowiring in Spring?
It is the automatic injection of dependencies by Spring based on type or name.

---

### 22. What are different types of autowiring?
- ByType  
- ByName  
- Constructor  

---

### 23. What is @Autowired annotation?
It tells Spring to automatically inject a dependency into a field, constructor, or setter.

---

### 24. What is @Qualifier and why is it used?
It is used when multiple beans of the same type exist to specify which bean should be injected.

---

### 25. What is @Primary annotation?
Marks a bean as the default choice when multiple beans of the same type are available.

---

### 26. What happens if multiple beans of same type exist?
Spring throws NoUniqueBeanDefinitionException unless resolved using @Qualifier or @Primary.

---

### 27. Difference between constructor injection and setter injection?
Constructor injection is used for mandatory dependencies and supports immutability.  
Setter injection is used for optional dependencies.

---

### 28. Why is constructor injection preferred?
It ensures all required dependencies are provided and prevents partially initialized objects.

---

### 29. Can we use @Autowired on constructors?
Yes. If only one constructor exists, Spring automatically uses it even without @Autowired.

---

### 30. What is field injection and why is it discouraged?
Field injection injects dependencies directly into fields. It is discouraged because it reduces testability and breaks encapsulation.

---

# 🔹 BEAN LIFECYCLE

### 31. What is bean lifecycle in Spring?
It describes the process from bean creation to destruction managed by the container.

---

### 32. What are different phases of bean lifecycle?
Instantiation → Dependency Injection → Initialization → Destruction

---

### 33. What is @PostConstruct?
A method annotated with it runs after dependency injection is completed.

---

### 34. What is @PreDestroy?
A method annotated with it runs before the bean is destroyed.

---

### 35. What is InitializingBean?
It provides afterPropertiesSet() method to execute custom initialization logic.

---

### 36. What is DisposableBean?
It provides destroy() method for cleanup before bean destruction.

---

### 37. What is BeanPostProcessor?
It allows modification of bean instances before and after initialization.

---

### 38. Difference between constructor and init method?
Constructor initializes object creation, while init method is used for post-initialization logic.

---

### 39. How does Spring manage bean destruction?
It calls destroy methods when the application context is closed.

---

### 40. What is custom init and destroy method?
Custom methods configured to run during initialization and destruction phases.

---

# 🔹 BEAN SCOPE

### 41. What is bean scope in Spring?
It defines how many instances of a bean are created and how long they live.

---

### 42. What are different bean scopes?
- Singleton  
- Prototype  
- Request  
- Session  

---

### 43. What is singleton scope?
Only one instance is created per Spring container (default scope).

---

### 44. What is prototype scope?
A new instance is created every time the bean is requested.

---

### 45. Difference between singleton and prototype scope?
Singleton → one shared instance  
Prototype → multiple instances  

---

### 46. What are request and session scopes?
Request scope creates a bean per HTTP request.  
Session scope creates a bean per user session.

---

### 47. What is custom bean scope?
A user-defined scope implemented using Spring’s Scope interface.

---

### 48. When should we use prototype scope?
When the bean is stateful and should not be shared.

---

### 49. What happens when prototype bean is injected into singleton?
Only one instance is injected at startup, not created each time.

---

### 50. Which scope is default in Spring?
Singleton

---

# 🔹 ADVANCED CORE

### 51. What is loose coupling and how Spring achieves it?
Loose coupling means classes depend on interfaces, not implementations. Spring achieves this using DI.

---

### 52. What is tight coupling?
Classes directly depend on concrete implementations, making code hard to modify.

---

### 53. Difference between IoC and DI?
IoC is the concept, DI is the implementation.

---

### 54. What is BeanFactoryPostProcessor?
It modifies bean definitions before beans are instantiated.

---

### 55. What is ApplicationContextAware?
It allows a bean to access the Spring container.

---

### 56. What are Aware interfaces in Spring?
Interfaces that provide access to container internals like BeanNameAware.

---

### 57. What is Environment abstraction in Spring?
It provides access to profiles and configuration properties.

---

### 58. What is PropertySource?
Represents external configuration sources like properties files.

---

### 59. What is @Value annotation?
Used to inject values from properties files into fields.

---

### 60. How do you externalize configuration in Spring?
Using properties files, YAML, environment variables, or profiles.

---

# 🔹 ANNOTATIONS

### 61. What are stereotype annotations?
Annotations like @Component, @Service, @Repository used to mark beans.

---

### 62. What is @ComponentScan?
It tells Spring where to scan for components.

---

### 63. What is @Lazy annotation?
Delays bean initialization until it is needed.

---

### 64. What is @Scope annotation?
Defines the scope of a bean.

---

### 65. What is @DependsOn?
Ensures one bean is initialized before another.

---

### 66. What is @Profile annotation?
Loads beans based on environment (dev, prod).

---

### 67. What is @Import annotation?
Used to include additional configuration classes.

---

### 68. What is @PropertySource?
Loads external property files.

---

### 69. What is @Conditional annotation?
Creates beans only if a condition is met.

---

### 70. What is @ConfigurationProperties?
Maps external configuration to a Java object.

---

# 🔹 REAL-TIME

### 71. How does Spring reduce boilerplate code?
Using DI, annotations, and AOP to handle repetitive tasks.

---

### 72. How would you design a loosely coupled system?
Use interfaces, dependency injection, and layered architecture.

---

### 73. How do you handle multiple implementations?
Use @Qualifier or @Primary.

---

### 74. How do you manage environment-specific configurations?
Using profiles and different configuration files.

---

### 75. How do you ensure thread safety in Spring beans?
Keep singleton beans stateless and avoid shared mutable data.

---

### 76. What happens internally when Spring container starts?
It loads configuration, creates beans, injects dependencies, and initializes them.

---

### 77. How does Spring resolve dependencies at runtime?
Using reflection and bean definitions stored in the container.

---

### 78. How would you debug bean creation issues?
Check logs, enable debug mode, and verify configuration.

---

### 79. Common mistakes developers make in Spring Core?
Using field injection, tight coupling, and incorrect scopes.

---

### 80. How does Spring improve testability?
By using DI, making it easy to replace dependencies with mocks.

---

# 🔹 TRICKY

### 81. Can we inject primitive values using @Autowired?
No, use @Value.

---

### 82. What happens if @Autowired fails?
Spring throws an exception unless required=false is used.

---

### 83. Can a class have multiple constructors with @Autowired?
Yes, but only one constructor should be used for injection.

---

### 84. Is Spring singleton thread-safe?
No, unless the bean is stateless.

---

### 85. Can we make a bean immutable in Spring?
Yes, using constructor injection and final fields.

---

### 86. What happens if bean scope is not defined?
It defaults to singleton.

---

### 87. Difference between @Component and @Bean?
@Component is auto-detected, @Bean is manually defined.

---

### 88. Can we use @Autowired without Spring container?
No, it requires the container.

---

### 89. What is circular dependency and how Spring handles it?
It occurs when two beans depend on each other. Spring resolves it using setter injection or early references.

---

### 90. Why is field injection not recommended?
Because it reduces testability and violates design principles.

---

# 🔹 INTERNALS

### 91. What happens internally when ApplicationContext is loaded?
Spring reads configuration, registers bean definitions, creates singleton beans, and injects dependencies.

---

### 92. How does Spring resolve circular dependencies?
Using early object references and proxy mechanisms.

---

### 93. What is proxy object in Spring?
A wrapper object used for features like AOP and transactions.

---

### 94. What is CGLIB vs JDK proxy?
JDK uses interfaces, CGLIB uses subclassing.

---

### 95. What is reflection and how Spring uses it?
Reflection allows runtime object creation and method invocation. Spring uses it to create beans and inject dependencies.

---

### 96. How does Spring scan components internally?
It scans classpath, detects annotations, and registers bean definitions.

---

### 97. What is classpath scanning?
Searching packages to find annotated classes.

---

### 98. How does Spring manage bean definitions?
Stores metadata in the container and uses it to create beans.

---

### 99. What is DefaultListableBeanFactory?
Core implementation that manages bean definitions and dependency resolution.

---

### 100. How does Spring create and wire beans internally?
Spring instantiates the bean, injects dependencies, applies post-processors, initializes it, and makes it available in the container.

---

