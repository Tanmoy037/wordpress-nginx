# wordpress-nginx

We are creating a docker network for running all the images in same network -

''docker network create wordpress-network''

docker build -t wordpress-image -f Dockerfile-wordpress .

docker build -t nginx-image -f Dockerfile-nginx .

docker build -t mysql-image -f Dockerfile-mysql .
