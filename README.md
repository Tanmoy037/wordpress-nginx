# wordpress-nginx

We are creating a docker network for running all the images in same network -
docker network create wordpress-network

For building wordpress image -
docker build -t wordpress-image -f Dockerfile-wordpress .

For building nginx image -
docker build -t nginx-image -f Dockerfile-nginx .

For creating mysql image -
docker build -t mysql-image -f Dockerfile-mysql .
