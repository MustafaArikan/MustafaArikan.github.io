# Some shortcuts for Docker

Here's the table of contents:

1. TOC
{:toc}

## Show images and sizes

```
sudo docker image ls
```

## Saving Docker image for import

```
docker export 'container_id' > docker_container.tar
docker import - importedcontainer < docker_container.tar
```

[See!](https://dockerlabs.collabnix.com/beginners/saving-images-as-tar/)

## Mount volume for read and write function within container

```
sudo docker run -v /home/user/<path>:/<container path>
```

[See!](https://stackoverflow.com/questions/31448821/how-to-write-data-to-host-file-system-from-docker-container)
