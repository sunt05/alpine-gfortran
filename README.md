# Various gfortran+gdb docker images for debugging


## 5.3–latest
Docker GNU Fortran, gdb and make over Alpine Linux

## 4.8 (legacy version of compatible with gfortran 4.8)
Docker GNU Fortran, gdb and make over Ubuntu


## Suported Tags

[10.3, latest - (gfortran 10.3.1_git20211027-r0 over alpine:3.15) (Dockerfile)](https://github.com/sunt05/alpine-gfortran/blob/master/10.3/Dockerfile)

[10.2 - (gfortran 10.2.1_pre1-r3 over alpine:3.13) (Dockerfile)](https://github.com/sunt05/alpine-gfortran/blob/master/10.2/Dockerfile)

[9.3 - (gfortran 9.3.0-r2 over alpine:3.12) (Dockerfile)](https://github.com/sunt05/alpine-gfortran/blob/master/9.3/Dockerfile)

[8.3 - (gfortran 8.3.0-r0 over alpine:3.10) (Dockerfile)](https://github.com/sunt05/alpine-gfortran/blob/master/8.3/Dockerfile)

[6.4 - (gfortran 6.4.0-r9 over alpine:3.8) (Dockerfile)](https://github.com/sunt05/alpine-gfortran/blob/master/6.4/Dockerfile)

[6.3 - (gfortran 6.3.0-r4 over alpine:3.6) (Dockerfile)](https://github.com/sunt05/alpine-gfortran/blob/master/6.3/Dockerfile)

[6.2 - (gfortran 6.2.1-r1 over alpine:3.5) (Dockerfile)](https://github.com/sunt05/alpine-gfortran/blob/master/6.2/Dockerfile)

[5.3 - (gfortran 5.3.0-r0 over alpine:3.4) (Dockerfile)](https://github.com/sunt05/alpine-gfortran/blob/master/5.3/Dockerfile)


## Build docker images

For instance, gfortran 10.3:
```
docker build -t sunt05/alpine-gfortran:10.3 -f 10.3/Dockerfile .
```

## Check GNU Fortran version
```
$ docker run --rm -it -v $(pwd):/source sunt05/alpine-gfortran:10.3
```
or
```
$ docker run --rm -it -v $(pwd):/source sunt05/alpine-gfortran:10.3 gfortran --version
```

## Compile, link and run a Fortran program
```
$ docker run --rm -it -v $(pwd):/source sunt05/alpine-gfortran:10.3 gfortran -Wall -o test /source/test.f90
$ docker run --rm -it -v $(pwd):/source sunt05/alpine-gfortran:10.3 ./test
```
