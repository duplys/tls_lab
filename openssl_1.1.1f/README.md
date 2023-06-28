## Building the Docker image
To build:
```console
$ docker build . -t openssl310
```

## Running the Docker container
To run:
```console
$ docker container run --rm -it openssl310
```
## Benchmark Algorithm Performance
To measure the performance of an algorithm:
```console
/opt/openssl# openssl speed -evp aes-128-gcm
```