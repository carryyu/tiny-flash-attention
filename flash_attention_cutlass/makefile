CC_FILES=/root/paddlejob/workspace/env_run/lzy/cute-gemm/tiny-flash-attention/flash_attention_cutlass/standalone_src/flash_attention_cutlass_standalone.cu
EXE_FILES=$(CC_FILES:.cu=)

all:$(EXE_FILES)

%:%.cu
	nvcc -o $@ $< -O2 -arch=sm_90 -std=c++17 -Iinclude -I/root/paddlejob/workspace/env_run/lzy/cute-gemm/3rd/cutlass/include --expt-relaxed-constexpr -lcublasLt -lcublas -cudart shared --cudadevrt none -lcublasLt -lcublas

clean:
	rm -rf $(EXE_FILES)
