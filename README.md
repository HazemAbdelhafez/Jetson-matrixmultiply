# Jetson-matrixmultiply

## [NetSysLab](http://netsyslab.ece.ubc.ca/wiki/index.php/Networked_Systems_Laboratory)

- This repo provide a code for an optimized matrix multiplication application based on the OpenBLAS and cuBLAS libraries that test the performance and shared memory on the Jetson TK1 and TX1 boards.

# Building and running:

```sh
cd Jetson-matrixmultiply
cd Release
make
./GPUMatMul <show-details> <num-iterations> <benchmark> <num-threads> <matrix-dimension> <cpu-columns>
```
### For example:
```sh
./GPUMatMul 0 1000 5 4 2048 0
```
### Benchmarks number mapping:
* 1 : matrix multiplication with explicit allocation on CPU memory
* 2 : matrix multiplication with unified memory on CPU
* 3 : matrix multiplication with CUDA HostAllocation on CPU
* 4 : matrix multiplication with direct matrix allocation on the GPU memory
* 5 : matrix multiplication with unified memory on GPU
* 6 : matrix multiplication with synch memory copy to the GPU
* 7 : matrix multiplication on both the CPU and GPU with HostMemAlloc
* 8 : matrix multiplication on both the CPU and GPU with zero-copy memory
* 9 : matrix multiplication on both the CPU and GPU with Asynch memory copy to the GPU
* 10 : matrix multiplication on both the CPU and GPU with Synch memory copy to the GPU
* 11 : matrix multiplication on both the CPU and GPU with split matrix across different memories

### Notes:
* The benchmark was tested on Jetson Tk1 and TX1 boards.
* The make file for the matrix multiplication was autogenerated by Nvidia Ecplise edition, if you want to modify it make sure you add all the dependencies correctly.

