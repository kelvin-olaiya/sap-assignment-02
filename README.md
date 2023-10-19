# E-Scooters

## Use cases

![Use cases](./img/use-cases.jpg)

## User stories

### User

```text
As a user,
I want to be able to register,
so that I can log in to the system.
```
    
```text
As a logged user,
I want to book an e-scooter,
so that I can use it when I need it.
```

```text
As a logged user,
I want to be able to unlock the e-scooter that I've found,
so that I can use it.
```

```text
As a logged user,
I want to be able to pay with my credit card,
so that I can use the service.
```

### Operator

```text
As an operator,
I want to be able to search for e-scooters that need to be maintained,
so that I can pick them up and possibly check them.
``` 

```text
As an operator,
I want to be able to search for e-scooters that need to be charged,
so that I can pick them up and charge them.
```

```text
As an operator,
I want to be able to unlock the e-scooter that I've found,
so that I can pickup it.
```

### Admin

```text
As an admin,
I want to be able to check the actual usege of e-scooters,
so that I can plan the maintenance and charging.
```

```text
As an admin,
I want to be able to look at statistics of the usage of e-scooters,
so that I can analyze them.
```

## Domain stories and Event storms

The domain stories with events storm board clarify the domain model and the use cases.

![Event storm](./img/event-storm.jpg)

An example is that, both **users** and **operators** can unlock e-scooters but, while users can unlock only the e-scooters before a payment, operators can unlock any e-scooter in order to pick up and check it.

Given that, the domain model should have two different entity, a `User` and a `Operator`, that can unlock an e-scooter, but with different constraints and different goals.

## Quality attribute scenarios

```text
Feature: Small Latency in the case of overload

when initiate 50.000 requests in 2 minutes interval
caused by 10.000 users
occur in the system
operating in normal operation
then the system should be able to processes all requests
so that the average latency < 5 seconds
```

```text
Feature: Basic security between user payment and service granting

When a user initiates a payment transaction to unlock an E-scooter,
caused by a user request,
occur in the payment processing component of the system,
operating in a public network or an untrusted environment,
then the system should ensure the confidentiality and integrity of payment data,
so that financial transactions are protected from unauthorized access and fraud.
```

```text
Feature: Usability of the mobile application E-scooter locator service

When a user make a request for the nearest E-scooter,
caused by accessing the location section in the application,
occurring in the mobile application interface,
operating in a low connection environment,
then the mobile app should provide clear and precise information (at most 5 meters of error) about the location of the nearest E-scooters
so that the user can find and rent an E-scooters without frustration, enhancing the overall user experience.
```
