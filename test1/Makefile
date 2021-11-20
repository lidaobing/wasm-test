all:
	@echo "make build # build wasm file"
	@echo "make run # start server"
	@echo "make stop # stop server"

build: hello.html

hello.html: hello.c
	emcc $^ -s WASM=1 -o $@

run:
	python3 -m http.server & echo $$! > server.pid
	open http://localhost:8000/hello.html

stop:
	kill `cat server.pid` 
