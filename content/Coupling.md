Related: [[Cohesion]], [[Software Engineering]]

---
Coupling refers to the degree of dependency between one service and another in your application. We want **low coupling**.

### ❌ High Coupling 
The internal implementation of $\large service_i$ affects many others. 

- If we make a change in how $\large service_i$ works (e.g. now returns two values instead of one), we need to potentially change the code in all other services connected to it
- If $\large service_i$ fails, many services will fail or block as well

### ✅ Low Coupling 
Services don't depend on too many other services.