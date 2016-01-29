# Docker Apache Flume

Docker image for the deployment of an [Apache Flume](https://flume.apache.org) server.

## Starting the container

To start the container use following command:

```
docker run --name some_flume -e FLUME_AGENT_NAME=myagent -d alonsodomin/flume
```

## Configuring Flume

The container comes with the bare minimum needed to start flume and use the
example configuration that comes with the standard Apache Flume distribution.

To include your own configuration you can mount it inside the container in
the ```/opt/lib/flume/conf``` folder.

```
docker run --name some_flume -e FLUME_AGENT_NAME=myagent -v /path/to/conf:/opt/lib/flume/conf -d alonsodomin/flume
```

If you want more advance configuration (setting up sources listening on specific
ports) then the recommended approach is to extend this image and expose the
ports that you might be interested in.
