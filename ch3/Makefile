run:
	docker-compose up

swarm-init:
	docker container exec -it manager docker swarm init
	# Memorize the join token

num := 01
swarm-join:
	docker container exec -it worker$(num) docker swarm join \
		--token $(token) manager:2377

# make swarn-join token=... num=01
# make swarn-join token=... num=02
# make swarn-join token=... num=03

swarm-ls:
	docker container exec -it manager docker node ls

push:
	docker image build -t hello .
	docker image tag hello:latest localhost:5000/hello:latest
	docker image push localhost:5000/hello:latest

pull-test:
	docker container exec -it worker01 docker image pull registry:5000/hello:latest
