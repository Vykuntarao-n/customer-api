# Getting Started

### Start Application
* Run the `CustomerapiApplication` Application
* Default application runs on the port http://localhost:8080
* When there are any port in use errors in the console override the port by setting the `server.port=808x` (where x is any number) in the `application.properties`
* Application comes with H2 in memory database.
  * [Quick Start on H2 Database](https://www.h2database.com/html/quickstart.html)
  * URL to access the [H2 DB Admin console](http://localhost:8080/h2-console)
  * Enter `JDBC URL` as  `jdbc:h2:mem:testdb`
* To run the application with Microsoft SQL Server
  * Add the dependency in `build.gradle` file
    ```
    implementation 'com.microsoft.sqlserver:mssql-jdbc'
    ```

  * Add the below configuration in `application.properties`
    ```
    spring.jpa.properties.hibernate.format_sql=true
    spring.datasource.url= jdbc:sqlserver://localhost:1433;encrypt=true;trustServerCertificate=true;databaseName=sqlserver_db
    spring.datasource.username= sqlserver
    spring.datasource.password= admin
    spring.jpa.properties.hibernate.dialect= org.hibernate.dialect.SQLServerDialect
    spring.jpa.hibernate.ddl-auto= update
    ```
### Test the api from postman
* Postman collection is available at location `src\test\newman`
* Here is the reference link to [import the postman collection](https://learning.postman.com/docs/getting-started/importing-and-exporting/importing-data/)
* Once the Postman collection is imported, it will contain all the customer operations.
  * GET is to SELECT SQL operation
    * Get all the list of Customers `GET http://localhost:8080/api/customers`
    * Get a customer with id `http://localhost:8080/api/customers/{id}`
  * POST is INSERT SQL Operation
    * Add customer `POST http://localhost:8080/api/customers`. Customers details will be send in the RequestBody.
  * PUT is to UPDATE SQL Operation
    * Update Customer `PUT http://localhost:8080/api/customers/{id}` Customers details will be send in the RequestBody.
  * DELETE is to DELETE SQL Operation
    * Delete Customer `DELETE http://localhost:8080/api/customers/{id}`

### Reference Documentation
For further reference, please consider the following sections:

* [Official Gradle documentation](https://docs.gradle.org)
* [Spring Boot Gradle Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.2.5/gradle-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.2.5/gradle-plugin/reference/html/#build-image)
* [Spring Web](https://docs.spring.io/spring-boot/docs/3.2.5/reference/htmlsingle/index.html#web)
* [Spring Data JPA](https://docs.spring.io/spring-boot/docs/3.2.5/reference/htmlsingle/index.html#data.sql.jpa-and-spring-data)

### Guides
The following guides illustrate how to use some features concretely:

* [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
* [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
* [Building REST services with Spring](https://spring.io/guides/tutorials/rest/)
* [Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/)

### Additional Links
These additional references should also help you:

* [Gradle Build Scans – insights for your project's build](https://scans.gradle.com#gradle)
