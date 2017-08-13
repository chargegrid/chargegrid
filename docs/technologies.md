# Technologies

ChargeGrid uses many different technologies to create a usable and scalable system. The main rule is: use the right tool for the job, but don't introduce a new tool when an existing tool can do the job just as well.

## Data storage

For most data storage ChargeGrid uses [PostgreSQL](https://www.postgresql.org/), a battle-tested, feature-rich and scalable SQL database. All backend services & Receptionist use their own PostgreSQL database for storing the data they need. There are 2 exceptions to this:

- **Central System:** Currently uses [DynamoDB](https://aws.amazon.com/dynamodb/) for storing current, ongoing sessions. The use of DynamoDB is for historical reasons, and is subject to change soon. ChargeGrid needs to be infrastructure-agnostic, so in the near future Central System will start using PostgreSQL for storing ongoing sessions.
- **Log Service:** Uses [ElasticSearch](https://www.elastic.co/products/elasticsearch) for storing raw OCPP log messages. ElasticSearch is a better fit for the use case of storing and searching through logs.

## Asyncronous communication

ChargeGrid uses [RabbitMQ](https://www.rabbitmq.com/) for asyncronous message passing between services. Messages are posted to queues serialized as JSON.

## Programming Languages

Currently, all backend systems, including Receptionist are written in [Clojure](https://clojure.org/). This allows for a functional, pragmatic and productive approach to writing code. The goal is to write code that easy to read and maintain, while being as succinct as possible within those boundaries.

For the upcoming Portal we will probably use Ecmascript2015 or Typescript as language.

### Libraries

The following Clojure libraries are used within most of the services:

- HTTP routing & API: [Compojure API](https://github.com/metosin/compojure-api)
- HTTP server: [HTTP Kit](http://www.http-kit.org/)
- Database & SQL (ORM): [Korma](http://sqlkorma.com/), although for Receptionist we switched to using [HugSQL](https://www.hugsql.org/) because it allows for much more complex queries without crazy hacks
- Database migrations: [Ragtime](https://github.com/weavejester/ragtime)
- Configuration: [cprop](https://github.com/tolitius/cprop)
- Logging: [Clojure Tools Logging](https://github.com/clojure/tools.logging) in combination with [Logback](https://logback.qos.ch/)
- Date/Time: [clj-time](https://github.com/clj-time/clj-time), although we might switch if a good CLJ wrapper for the Java 8 Date/Time api becomes available

We encourage contributers to pick from this list whenever possible

The upcoming Portal will probably be built using React.

## Orchestration

All services are built to be run inside [Docker](https://www.docker.com/) containers. This makes local development, production deployments and scaling easy. The [deploy-scripts](https://github.com/chargegrid/deploy-scripts) currently use [Docker Compose](https://docs.docker.com/compose/) for orchestrating the Docker Containers, but it should be easy to switch to something like Kubernetes in the future.
