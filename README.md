# BWCE Showcase
Showcase of BWCE Features with Examples

## Circuit Breaker
### BWCE_Showcase_CircuitBreaker
Project containing examples using the Circuit Breaker feature
- CircuitBreakerAPI: Rest API which invokes a downstream service. Accepts a query parameter (success:boolean) that triggers the downstream service to return either successfully (200) or unsuccessfully (500). Invoking this API multiple times with success=false will cause the Circuit to Open. This demonstrates the ability to distinguish between a downstream service failure and a Circuit being open.

- CircuitBreakerAPI2: Similiar in most respects to the above API, this service demonstrates a more typical approach of retrying a service call several times (ex: 3) before failing. Instead of returning an error to the consumer this service calls alternate paths depending on whether the service has failed or the Circuit is Open.

## Service Discovery
### BWCE_Showcase_ServiceDiscovery
Project containing examples using the Service Discovery feature
- Consul Server: A Consul Server is required for this example
  - A simple Consul Server can be started using Docker
  - docker pull progrium/consul
  - docker run -d -p 8400:8400 -p 8500:8500 -p 8600:53/udp -h node1 progrium/consul -server -bootstrap -ui-dir /ui
  - Once running navigate to http://localhost:8500/ui and confirm the server has started
  
- Environment Varaible: Before running this example you must set the Environment Variable "CONSUL_SERVER_URL"
  - In Studio this can be done in the Run Configuration, Environment Tab
  <link to image>
- CircuitBreakerAPI: Rest API which invokes a downstream service. Accepts a query parameter (success:boolean) that triggers the downstream service to return either successfully (200) or unsuccessfully (500). Invoking this API multiple times with success=false will cause the Circuit to Open. This demonstrates the ability to distinguish between a downstream service failure and a Circuit being open.

- CircuitBreakerAPI2: Similiar in most respects to the above API, this service demonstrates a more typical approach of retrying a service call several times (ex: 3) before failing. Instead of returning an error to the consumer this service calls alternate paths depending on whether the service has failed or the Circuit is Open.
