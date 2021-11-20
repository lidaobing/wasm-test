all:
	@echo "make build # build wasm file"
	@echo "make run # start server"
	@echo "make stop # stop server"

build: hello.html

hello.html: hello.c
	emcc $^ -s WASM=1 -o $@

run:
	python3 -m http.server &
	open http://localhost:8000/hello.html

stop:
	lsof -ni TCP:8000 -sTCP:LISTEN -Fp | head -1 | tr -d p | xargs kill