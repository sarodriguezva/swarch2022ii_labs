# swarch2022ii_labs
Software Architecture Laboratories. UNAL Bogotá 2022

Commands:

docker build -t swarch2022ii_db .

docker run -d -t -i -p 3306:3306 --name swarch2022ii_db swarch2022ii_db
#
docker run --name db_client -d --link swarch2022ii_db:db -p 8081:80 phpmyadmin

http://localhost:8081
#
docker build -t swarch2022ii_ms .

docker run -p 4000:4000 -e DB_HOST=X -e DB_PORT=3306 -e DB_USER=swarch2022ii -e DB_PASSWORD=2022 -e DB_NAME=swarch2022ii_db -e URL=0.0.0.0:4000 swarch2022ii_ms

X: swarch2022ii_db IP

Get ip: docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container_name_or_id
#
docker build -t swarch2022ii_ag .

docker run -p 5000:5000 swarch2022ii_ag

localhost:5000/graphiql
