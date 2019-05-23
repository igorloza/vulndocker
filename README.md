# Build image
```ssh
docker-compose build --no-cache
```
# Run Container 
```ssh
docker-compose up -d
```
#connect to container with root
```ssh
docker exec -it apache_web /bin/bash
```
# SSH to custom port
```ssh
ssh -p 1122 igorloza@0.0.0.0
```

Troubleshooting
# known Hosts issue
remove known hosts if getting errors for known hosts
```ssh
vim ~/.ssh/known_hosts 
```

# Other useful commands
```ssh
docker ps
ps aux
```
