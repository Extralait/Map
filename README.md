# Graphite

### Project run
```vim
$ docker build -t web-image .GraphiteBack
$ docker-compose up 
```

### Project update
```vim
$ docker-compose up -d --build
$ docker-compose down
```

### Run script
```vim
$ docker-compose exec web {script} 
```

### Swarm
```vim
$ docker swarm init --advertise-addr 127.0.0.1:2377
$ docker stack deploy -c docker-compose.yml  proj
```  
### Remove swarm 
```vim
$ docker stack rm proj
$ docker swarm leave --force
```


# Graphite

### Project run
```sh
$ docker build -t web-image .GraphiteBack
$ docker-compose up 
```

### Project update
```sh
$ docker-compose up -d --build
$ docker-compose down
```

### Run script
```sh
$ docker-compose exec web {script} 
```

### Swarm
```sh
$ docker swarm init --advertise-addr 127.0.0.1:2377
$ docker stack deploy -c docker-compose.yml  proj
```  
### Remove swarm 
```sh
$ docker stack rm proj
$ docker swarm leave --force
```

# Graphite

### Project run
```nano
$ docker build -t web-image .GraphiteBack
$ docker-compose up 
```

### Project update
```nano
$ docker-compose up -d --build
$ docker-compose down
```

### Run script
```nano
$ docker-compose exec web {script} 
```

### Swarm
```nano
$ docker swarm init --advertise-addr 127.0.0.1:2377
$ docker stack deploy -c docker-compose.yml  proj
```  
### Remove swarm 
```nano
$ docker stack rm proj
$ docker swarm leave --force
```
