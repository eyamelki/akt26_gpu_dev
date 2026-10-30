CUDADIR ?= /usr/local/cuda

# Turing (T4, sm_75) and Ampere (A100, sm_80) binaries + PTX for forward compatibility
GENCODE = -gencode arch=compute_75,code=sm_75 \
          -gencode arch=compute_80,code=sm_80 \
          -gencode arch=compute_80,code=compute_80

LIB=-L${CUDADIR}/lib64 -lcublas

all:
	nvcc ${GENCODE} ger.cu -o ger ${LIB}

clean:
	rm -rf ger
