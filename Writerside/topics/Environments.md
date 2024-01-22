# Environments

We categorize our application environments into Development, Testing and Production. To keep all environments same we utilize the power of [Docker](https://www.docker.com/) containers.
Our team writes Docker Images which helps us to match production environment in our test and dev environments. 

## Development
This environment lives on developers local machine. Since each developer is allowed to use different Operating system of their choice, we make sure that our docker images can replicate the production environment.

> Note:
> 
> See our [Setup](Setup.md) page to learn how to set up a development environment.
> {style="note"}


## Testing
ITS hosts all our testing applications to a dedicated test server. All test applications are deployed using test docker containers and test databases. In order to keep production data and apis secure we separate test applications by serving them under `https:apps-test.uis.edu` domain and all test databases are maintained on `uisdocker1` server.

## Production
We constantly update and upgrade our dependencies for all applications in order to stay current with new and emerging technologies. Using docker helps us with this by building new updated and improved docker images which can then be tested and used in production environment.
Our production server has a load balancer which routes the request to available server.
