# Scooter demo specification

Specification for demo apps that can be used to showcase modern cloud native
microserives.

## Functional requirements

Apps should simulate operation of electric scooters in fictional town. Let the
company's name be "Kiwi Scooters Inc.".

Apps should serve as http REST endpoints. Each REST endpoint should be serve as 
separate microservice.

There should be simple entry point service, with optional count parameter, 
that would act as invoker of number to simulated scooter rides.

Simulated ride should be assigned to user, and it's length should be randomly 
picked from 2km to 25km range.

Ride cost is 1$ to start, and 0.1$ per km traveled.

Each user should have their own wallet, that could be founded with 10$, 25$, 
or 50$. Founding depends on wallet actual value. There's 100% chance of 
founding if there are insufficient funds, and 5% in different case. Founding
amount is randomly choosen.

Founding should be done via eventing system.

There's a 0.1% chance of scooter failure during the ride. Repair cost should
be randomly picked from range 100$ to 500$. If breakage occurred, we do not
 charge user for a ride.

Scooter breakage should be done via eventing system.

We should keep track of company money balance, so founding minus repairs.

## Non functional requirements

Apps should be implemented in one of JavaScript languages, like TypeScript.

Workflow should be optimized for quickest startup possible.

Technical dept should be low, so apps can serve purposes of good examples, 
thus good architecture is required. Tests should cover all branches.

Container and kubernetes files should be provided and image building should 
be configured.

State should be held in simple key value store, ephemeral or persistent.

Apps should be simple to follow, but represent real world cases. It should 
be possible to write them in 2-3 live coding pair programming sessions. 
