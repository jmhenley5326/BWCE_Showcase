# BWCE Showcase
Showcase of BWCE Features with Examples

## Circuit Breaker
### BWCE_Showcase_CircuitBreaker
Project containing examples using the Circuit Breaker feature
- CircuitBreakerAPI: Rest API which invokes a downstream service. Accepts a query parameter (success:boolean) that triggers the downstream service to return either successfully (200) or unsuccessfully (500). Invoking this API multiple times with success=false will cause the Circuit to Open. This demonstrates the ability to distinguish between a downstream service failure and a Circuit being open.

- CircuitBreakerAPI2: Similiar in most respects to the above API, this service demonstrates a more typical approach of retrying a service call several times (ex: 3) before failing. Instead of returning an error to the consumer this service calls alternate paths depending on whether the service has failed or the Circuit is Open.
