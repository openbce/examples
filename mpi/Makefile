EXECS=allreduce
MPICC?=mpicc

all: ${EXECS}

allreduce: allreduce.c
	${MPICC} -o allreduce allreduce.c

clean:
	rm ${EXECS}
