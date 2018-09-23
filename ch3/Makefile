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
	(cd ../ch2; make build)
	docker image tag example/echo:latest localhost:5000/example/echo:latest
	docker image push localhost:5000/example/echo:latest

pull-test:
	docker container exec -it \
	  worker01 docker image pull registry:5000/example/echo:latest

service-test:
	docker container exec -it manager \
	  docker service create --replicas 1 --publish 8000:8080 --name echo registry:5000/example/echo:latest

service-ls:
	@docker container exec -it manager \
	  docker service ls

scale := 6
service-scale:
	@docker container exec -it manager \
	  docker service scale echo=$(scale)

service-ps:
	@docker container exec -it manager \
	  docker service ps echo


