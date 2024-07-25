> [!NOTE]
> **PATH**: Finding executable programs <br>
> **LD_LIBRARY_PATH**: Finding shared libraries (.so files)
1. TensorRT: `export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<TensorRT-${version}>/lib`
2. CUDA:
```
export PATH=$PATH:/usr/local/cuda-xx.x/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-xx.x/lib64
```
3. Python: `export PYTHONPATH=\path\to\pythoncode`
