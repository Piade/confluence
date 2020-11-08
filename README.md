# confluence
# for build
#docker build -t wangzan18/confluence:latest .
#for run
#docker run -d --name confluence \
  --restart always \
  -p 39080:8090 \
  --network confluencenet \
  -e TZ="Asia/Tehran" \
  -v /home/data/www/confluence.wzlinux.com:/var/atlassian/confluence \
  wangzan18/confluence:latest


use database on docker with 

docker run -d  -p 5433:5432 \
    --name postgres_atlassian \
    --network confluencenet \
    -e POSTGRES_USER=postgres \
    -e POSTGRES_PASSWORD=postgres \
    -v postgresData:/var/lib/postgresql/data \
    postgres:10
