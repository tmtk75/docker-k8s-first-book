run:
	docker container run --rm --name workspace \
		-it ch10/workspace:latest bash

run2:
	kubectl run -i --rm --tty workspace \
		--image=ch10/workspace:latest --restart never \
		-- bash -il

build:
	docker image build -t ch10/workspace:latest .

