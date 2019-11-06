# Using the Object Mapper in Node.js
This example demonstrates how to use the object mapper in Node.js to insert and retrieve data from a Cassandra cluster.

Contributors: [Jorge Bay Gondra](https://github.com/jorgebay) and [Andrew Tolbert](https://github.com/tolbertam), copied from [here](https://github.com/datastax/nodejs-driver/blob/master/examples/mapper/mapper-insert-retrieve.js)

## Objectives

* To provides a singlular example of how to insert and retrieve data using the object mapper described in the documentation [here](https://docs.datastax.com/en/developer/nodejs-driver/4.3/features/mapper/)
  
## Project Layout

* app.js - The main application file which contains the example code for using the object mapper

## How this Sample Works
This example starts by first, creating a mapper instance that maps three tables in the `examples` keyspace.
* `users`
* `user_videos`
* `latest_videos`   



## Setup and Running

### Prerequisites

* Node.Js version 8
* A Cassandra cluster with the connection information

**Note** This application defaults to connecting to a cluster on localhost with a local data center of `dc1`.  These parameters can be changed on line 6 of [app.js](app.js).

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

