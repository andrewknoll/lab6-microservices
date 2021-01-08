## Report

# The two microservices `accounts (2222)` and `web` are running and registered.

Service `web` is up and running on port 3333
![Terminal running web service](images/1.png)

Service `accounts` is up and running on port 2222
![Terminal running accounts service](images/2.png)

# The service registration service has these two microservices registered

Service `registration` is up and running on port 1111. It registered services `web` and `accounts`.
![Terminal running registration service](images/3.png)

The Eureka dashboard shows the two registered services.
![Eureka dashboard registered the two services](images/4.png)

# A second `accounts` microservice instance is started and will use the port 4444. This second `accounts (4444)` is also registered

Service `accounts` is up and running on port 4444
![Terminal running registration service on port 4444](images/5.png)

The Eureka dashboard shows the service on the two addresses.
![Eureka dashboard registered the new instance of accounts on 4444](images/6.png)

# What happens when you kill the microservice `accounts (2222)` and do requests to `web`? Can the web service provide information about the accounts again? Why?

The Eureka dashboard now shows only the 4444 instance of service `accounts`.
![Eureka dashboard now only shows the instance of accounts on port 4444](images/7.png)

The dashboard of service `web` works properly...
![The service web works properly](images/8.png)

And allows for the use of account requests.
![The service web makes account requests properly](images/9.png)

This happens because Eureka has registered the two addresses and works as a load balancer.
So in the case one of the ports fail to load, or is unreachable, the load balancer will send the request to the only available address.



