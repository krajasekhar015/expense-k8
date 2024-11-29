# Horizontal Pod Autoscaling

- Scaling is of two types. They are:
    1. Horizontal Scaling
    2. Vertical Scaling

- Horizontal Scaling and Vertical Scaling are two approaches to increasing the capacity or performance of a system, typically used in the context of servers or cloud infrastructure. Both aim to handle increased load but do so in different ways.

- Suppose consider there is a building with ground floor and first floor. Due to increase in population we need to build four floors which is called vertical scaling. Otherwise build four individual buildings separetly which is called horizontal scaling.

- Suppose, the old house gets any problem in the basement, then the whole house will be collapsed. 

**1. Horizontal Scaling**
Horizontal scaling is where we create multiple servers based on the traffic with zero downtime

- There is no single point of failure in horizontal scaling

**2. Vertical Scaling**
Vertical scaling is where we can increase the number of resources (such as CPU, RAM, or storage) in the same server

- There is downtime since there is only single machine (Stop the server then increase resources and then restart)

Suppose our application is running and traffic increases on application then we need to increase number of pods.
