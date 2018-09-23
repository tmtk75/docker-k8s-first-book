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
