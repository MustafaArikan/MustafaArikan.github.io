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


## Copy file from and to container

```
docker cp src/. container_id:/target
docker cp container_id:/src/. target
```

[See!](https://stackoverflow.com/questions/22907231/how-to-copy-files-from-host-to-docker-container)

## Delete image

```
docker image rm
```

## Commit changes to image

```
docker commit -m "Changed" image_name
```
[See!](https://stackoverflow.com/questions/26199903/how-to-see-commit-message-from-docker-images)






