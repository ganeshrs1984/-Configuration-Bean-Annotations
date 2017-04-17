# -Configuration-Bean-Annotations
@Configuration &amp; @Bean Annotations - Bootstraping

http://docs.spring.io/spring-javaconfig/docs/1.0.0.M4/reference/html/ch03.html

https://www.tutorialspoint.com/spring/spring_java_based_configuration.htm

Annotating a class with the @Configuration indicates that the class can be used by the Spring IoC container as a source of bean definitions. The @Bean annotation tells Spring that a method annotated with @Bean will return an object that should be registered as a bean in the Spring application context. The simplest possible @Configuration class would be as follows −


#JavaConfig provides a getBean() variant that accepts both a class and a bean name for cases just such as these.

    @Configuration
    public class MyConfig {
      @Bean(primary=Primary.TRUE)
      public Service myService() {
          return new Service();
      }

      @Bean
      public Service backupService() {
          return new Service();
      }
    }
  
  
    Service service = context.getBean(Service.class);  (If you dont define it as @Primary it will fail due to Ambiguity)
    Service service = context.getBean(Service.class, "myService");
    Service service = (Service) context.getBean("myService");


