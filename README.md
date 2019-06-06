# proto-compiler-docker
Compile `.proto` files with Docker.

## dev
> docker built -t proto-compiler:latest .

## Usage
> $ export protoCompiler="proto-compiler:latest"
>
> $ docker run -v $(pwd):/repo $(protoCompiler) \
    protoc -Irepo/proto -Irepo/third_party \
    --js_out=import_style=commonjs,binary:/repo/out \
    --ts_out=service=true:/repo/out \
    --go_out=plugins=grpc:/repo/out \
    --grpc-gateway_out=logtostderr=true:/repo/out \
    --swagger_out=logtostderr=true:/repo/out/swagger \
    --lint_out=. \
  repo/proto/test.proto

## License
MIT
