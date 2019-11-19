# Object Mapper in Node.js
The [Node.js DataStax Driver](https://docs.datastax.com/en/developer/nodejs-driver/latest) comes with an [object mapper](https://docs.datastax.com/en/developer/nodejs-driver/latest/features/mapper/) that removes boilerplate of writing queries and lets you focus on your application objects. This example shows how to use the mapper to access Apache Cassandra™ in a Node.js application.

Contributor(s): [Jorge Bay Gondra](https://github.com/jorgebay), [Andrew Tolbert](https://github.com/tolbertam) - derived from [here](https://github.com/datastax/nodejs-driver/blob/master/examples/mapper/mapper-insert-retrieve.js)

## Objectives

* Demonstrate how to write and read data using the Node.js Driver's object mapper
  
## Project Layout

* [app.js](app.js) - The main application file which contains the example code for using the object mapper

## How this Sample Works
This example starts by creating a mapper instance that maps to three tables in the `examples` keyspace.
* `users`
* `user_videos`
* `latest_videos`   

It then uses that mapper instance to write and read data to / from the tables above.

## Setup and Running

### Prerequisites

* Node.Js version 8
* A Cassandra cluster is running and accessible through the contacts points and data center

**Note** This application defaults to connecting to a cluster on localhost with a local data center of `dc1`.  These parameters can be changed in [app.js](app.js) by modifying the following to your settings.

`const client = new cassandra.Client({ contactPoints: ['127.0.0.1'], localDataCenter: 'dc1' });`

### Running
To run this application use the following command:

`node app.js`

This will produce the following output:

```
--Obtained video by id
 { videoId: Uuid: 31ff5550-da75-47f4-8b41-926512f74691,
  addedDate: 2019-11-06T22:47:00.369Z,
  description: 'My desc',
  location: null,
  locationType: null,
  name: 'My video',
  previewThumbnails: null,
  tags: null,
  userId: Uuid: 7cd9f42f-6a37-42b6-a8d6-08c6ecdbf75f }
--Obtained video by user id
 { userId: Uuid: 7cd9f42f-6a37-42b6-a8d6-08c6ecdbf75f,
  addedDate: 2019-11-06T22:47:00.369Z,
  videoId: Uuid: 31ff5550-da75-47f4-8b41-926512f74691,
  name: 'My video',
  previewImageLocation: null }```

