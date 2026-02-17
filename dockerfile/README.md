\# Dockerfile Practical – INT332



\## Base Image

FROM ubuntu:latest



\## Install PHP

RUN apt update \&\& apt install -y php



\## Default Command

CMD \["echo", "HELLO STUDENT"]



---



\## Build Image

docker build -t student-image .



\## Run Container

docker run student-image



Expected Output:

HELLO STUDENT



