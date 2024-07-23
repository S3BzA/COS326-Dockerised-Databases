# Hello,

If you are using this repo, note that I will use this README as a means of communicating the current state of this project. E.g. some of the database version aren't exactly as specified by the module study guide due to a lack of availability on Docker. I will also use this README to communicate any issues I have encountered and how I have resolved them.

## Study guide database specification

| Software   | Version | Download Link                                              | Database Type               |
| ---------- | ------- | ---------------------------------------------------------- | --------------------------- |
| ObjectDB   | 2.9.0   | [Download](https://www.objectdb.com/download)              | Object Oriented Databases   |
| PostgreSQL | 16.3    | [Download](http://www.PostgreSQL.org/download/)            | Object Relational Databases |
| BaseX      | X111    | [Download](https://basex.org/download/)                    | XML Databases               |
| MongoDB    | 7.0.12  | [Download](https://www.mongodb.com/try/download/community) | NoSQL Document Databases    |
| Neo4j DB   | 5.9.0   | [Download](https://neo4j.com/download-center/)             | NoSQL Graph Databases       |

## Current database versions

| Software   | Version |
| ---------- | ------- |
| ObjectDB   | 2.9.0   |
| PostgreSQL | 16.3    |
| BaseX      | Latest  |
| MongoDB    | 7.0.12  |
| Neo4j DB   | 5.9.0   |

## Notes (per database)

### ObjectDB
Object DB is not available on Docker. I have downloaded the ObjectDB version 2.9.0 from the official website and stuck that .zip into the `/objectdb` directory with a `Dockerfile` that the `compose.yaml` uses. This spins up the objectdb server.

### PostgreSQL
Requires authentication, which is specified in the `compose.yaml` file.

### BaseX
Version X111 (or 11.1) is not available on docker. I am using the latest tag as the next available version is 9.5.2. This is not the version specified in the study guide. Here is the link to the available tags: [BaseX Docker Hub](https://hub.docker.com/r/basex/basexhttp/tags).

### MongoDB
Nothing to note.

### Neo4j DB
Two ports are specified in the `compose.yaml` file. The first is the default port for the Neo4j DB, the second is the bolt port. The bolt port is used for the Neo4j Browser. The default port is used for the Neo4j DB itself. The admin username and password are specified in the `compose.yaml` file in the `NEO4J_AUTH` environment variable formatted as `username/password`. Note: having "neo4j" as the username is required as it is the admin username.

## Issues
- Need to confirm if the BaseX version is correct. The latest tag is not the version specified in the study guide. I will need to confirm this with the module leader.
- Need to double-check that all the volumes specified in the `compose.yaml` are correct to ensure persisistence across the databases. 

