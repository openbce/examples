FROM ubuntu:18.04 as build
RUN apt update && apt install -y git libopenmpi-dev openmpi-bin build-essential
RUN git clone https://github.com/openbce/examples /opt/examples
RUN cd /opt/examples/mpi && make

# mpi-operator has several dependencies, so alpine does not work for it.
FROM ubuntu:18.04
MAINTAINER Klaus Ma <klaus@xflops.cn>
RUN apk update && apk add openmpi
COPY --from=build /opt/examples/mpi/allreduce /opt/
ENTRYPOINT ["/opt/allreduce"]