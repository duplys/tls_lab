## Building the Docker image
To build:
```console
$ docker build . -t openssl310_debug
```

## Running the Docker container
To run:
```console
$ docker container run --rm -it openssli310_debug
```

## Debugging OpenSSL
In the Docker container:
```console
# cd /opt/openssl/openssl-3.1.0/apps
# export LD_LIBRARY_PATH=/opt/openssl/openssl-3.1.0:$LD_LIBRARY_PATH
# gdb -x /opt/openssl/openssl-3.1.0/gdbinit --args ./openssl s_client -crlf -ign_eof -connect cr.yp.to:443 -msg -debug
```

Then in GDB:
```console
(gdb) b s_client_main
(gdb) run
(gdb) b SSL_write
(gdb) c
(gdb) c
<enter "GET / HTTP1.1" (without quotes)>
(gdb) s
```

