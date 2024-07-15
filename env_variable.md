> [!NOTE]
> **PATH**: Finding executable programs
> **LD_LIBRARY_PATH**: Finding shared libraries (.so files)
1. TensorRT: `export LD_LIBRARY_PATH=<TensorRT-${version}>/lib:$LD_LIBRARY_PATH`
2. CUDA:
```
export PATH=$PATH:/usr/local/cuda-xx.x/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-xx.x/lib64
```
