# Video Streaming Microservice API

This is a simple microservices-based REST API designed for video streaming. The system allows storing metadata for videos, including title, description, and file path, while enabling streaming directly from local storage. The application leverages several key microservice architecture components such as API Gateway, Config Server, Service Registry, and Zipkin for distributed tracing.

## Key Features

- **Save New Video**  
  Endpoint to save video metadata including title, description, and file path.
  - **URL**: `/movie-info/save`
  - **Method**: `POST`
  - **Request Body**: `List<MovieInfo>` (Contains title, description, and path to video)

- **Get All Videos**  
  Endpoint to retrieve a list of all stored video metadata.
  - **URL**: `/movie-info/list`
  - **Method**: `GET`

- **Get Video Path by ID**  
  Endpoint to get the file path of a video by its ID.
  - **URL**: `/movie-info/find-path-by-id/{movieInfoId}`
  - **Method**: `GET`

- **Stream Video by Path**  
  Endpoint to stream a video by providing its file path.
  - **URL**: `/stream/{videoPath}`
  - **Method**: `GET`

- **Stream Video by ID**  
  Endpoint to stream a video by its ID.
  - **URL**: `/stream/with-id/{movieInfoId}`
  - **Method**: `GET`

## Microservices Architecture

This application is built using a microservices architecture and includes:

- **API Gateway**  
  The API Gateway acts as a reverse proxy to route requests to the appropriate microservices and handles cross-cutting concerns like load balancing.

- **Config Server**  
  A central configuration server for managing application configurations across different environments. This provides flexibility in managing properties like database connections and external service URLs.

- **Service Registry**  
  A service registry is used for dynamic service discovery, enabling microservices to find each other in a distributed environment.

- **Zipkin for Distributed Tracing**  
  Zipkin is integrated for tracing requests across the microservices. This enables better visibility into how requests flow through the system and helps with debugging performance bottlenecks.

## Configuration

- The main port is `8080`.
- The application uses `Spring Cloud` for service management and `Zipkin` for tracing.
- Configuration is managed by the Config Server and can be adjusted for different environments.

