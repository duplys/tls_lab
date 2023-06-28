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
/opt/openssl# openssl speed aes-128-cbc
Doing aes-128-cbc for 3s on 16 size blocks: 149860669 aes-128-cbc's in 3.00s
Doing aes-128-cbc for 3s on 64 size blocks: 66115959 aes-128-cbc's in 3.00s

-- snip --

The 'numbers' are in 1000s of bytes per second processed.
type             16 bytes     64 bytes    256 bytes   1024 bytes   8192 bytes  16384 bytes
aes-128-cbc     799256.90k  1410473.79k  1447774.12k  1471690.41k  1469541.03k  1434719.57k
```