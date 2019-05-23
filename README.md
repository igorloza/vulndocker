docker-compose build --no-cache
docker-compose up -d
docker exec -it apache_web /bin/bash
ssh -p 1122 igorloza@0.0.0.0
vim ~/.ssh/known_hosts  - remove known hosts if getting errors for known hosts
docker ps
ps aux



