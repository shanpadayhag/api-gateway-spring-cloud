<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
[![License][license-shield]][license-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <h3 align="center">API Gateway Service</h3>

  <p align="center">
    A Spring Cloud API Gateway for routing requests to microservices.
    <br />
    <br />
    <a href="#getting-started"><strong>Get Started »</strong></a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#running-the-application">Running the Application</a></li>
      </ul>
    </li>
    <li><a href="#routes">API Gateway Routes</a></li>
     <li><a href="#service-discovery">Service Discovery</a></li>
	 <li><a href="#important-considerations">Important Considerations</a></li>
    <li><a href="#license">License</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project

This project is a Spring Cloud API Gateway service designed to route incoming requests to various microservices. It serves as a single entry point for the application, simplifying access to underlying services and providing essential functions like request routing, load balancing, and potentially authentication/authorization. This service leverages Spring Cloud Gateway and Eureka for service discovery.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started

This section provides information on setting up and running the API Gateway service.

### Prerequisites

*   Java Development Kit (JDK) 23
*   Maven
*   A running instance of the Eureka Discovery Server
*   A suitable IDE for Java development

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Running the Application

1.  **Install Maven Packages:**
    ```sh
    mvn install
    ```

2.  **Configure Application Properties:**
    Ensure your `application.properties` (or `application.yml`) is configured to connect to the Eureka Discovery Server and defines the necessary routes.

3.  **Run the API Gateway Service:**
    ```sh
    mvn spring-boot:run
    ```
    This will start the API Gateway service.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## API Gateway Routes

This API Gateway is configured with the following routes (as an example. check the `application.properties` or `application.yml`):

*   **/service-a/\*:** Routes requests to the service registered as `service-a` in Eureka.
*   **/service-b/\*:** Routes requests to the service registered as `service-b` in Eureka.

These routes can be configured in the `application.properties` or `application.yml` file, utilizing the Spring Cloud Gateway configuration properties. The route definitions can handle path rewrites, load balancing, or other API Gateway features.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Service Discovery

This service uses Spring Cloud Eureka for dynamic service discovery. The API Gateway registers itself with the Eureka server and also retrieves information about registered microservices. This allows the API Gateway to dynamically route requests to available instances of the microservices, providing load balancing and fault tolerance capabilities.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Important Considerations

*   Ensure the Eureka Discovery Server is running before starting this API Gateway service.
*   Verify that the service names used in the routes correspond to the actual names registered with Eureka.
*   For a production environment, additional features such as authentication, authorization, and rate limiting should be added.
*   Proper logging and monitoring should also be implemented.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- LICENSE -->
## License

This project is licensed under the **MIT No Attribution License (MIT-0)**. See [`LICENSE.txt`](LICENSE.txt) for the full license text.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
[license-shield]: https://img.shields.io/github/license/shanpadayhag/api-gateway-spring-cloud?style=for-the-badge
[license-url]: LICENSE.txt
