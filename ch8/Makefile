max-size:
	docker container run -it --rm -p 8080:8080 \
	  --log-opt max-size=1m \
	  --log-opt max-file=5 \
	  example/echo:latest

kibana:
	open http://localhost:5601

fluentd:
	docker image build -t ch08/fluentd-es:latest .
