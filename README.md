# docker-mumo
Python Mumble admin scripts running in a container. See https://github.com/mumble-voip/mumo for more information.
- trying to make 3rd party modules work.

## Prerequisites

 * A mumble server running via docker

## Usage
First run the container and it will create all the necessary config files and exit.

```
docker run --name mumo --net=container:`id_of_mumble_server_container` -d -v /path/to/mumo/folder:/data maui/docker-mumo
```

Edit mumo.ini and copy config files from `modules_available` to `modules_enabled` that you want to activate. Make any edits to those files. Then fire the container up again.

copy 3rd party modules.py to `modules` & 3rd party config files to `modules_available` then link them to `modules_enabled` to enable them. 

```
docker start mumo
```
