EXECS=allreduce
MPICC?=mpicc

IMG_VER?=v0.1
IMG?=openbce/mpi-example:${IMG_VER}

all: ${EXECS}

allreduce: allreduce.c
	${MPICC} -o allreduce allreduce.c

clean:
	rm ${EXECS}

docker-build:
	docker build -t ${IMG} .

docker-push:
	docker push ${IMG}
