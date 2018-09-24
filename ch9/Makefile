image: hello
	docker image build -t ch09/hello:latest .

hello: hello.go
	GOOS=linux GOARCH=amd64 go build hello.go

