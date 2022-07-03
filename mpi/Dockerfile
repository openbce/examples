FROM ubuntu:18.04 as build
RUN apt update && apt install -y git libopenmpi-dev openmpi-bin build-essential
RUN git clone https://github.com/openbce/examples /opt/examples
RUN cd /opt/examples/mpi && make

FROM alpine:3.16
MAINTAINER Klaus Ma <klaus@xflops.cn>
RUN apk update && apk add openmpi
COPY --from=build /opt/examples/mpi/allreduce /opt/
ENTRYPOINT ["/opt/allreduce"]