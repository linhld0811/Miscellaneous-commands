> [!NOTE]
> **PATH**: Finding executable programs <br>
> **LD_LIBRARY_PATH**: Finding shared libraries (.so files)
1. TensorRT:
```
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<TensorRT-${version}>/lib
```
2. CUDA:
```
export PATH=$PATH:/usr/local/cuda-xx.x/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-xx.x/lib64
```
3. Python: Import code from other directory
```
export PYTHONPATH=\path\to\python_code
```
5. Torch cache: Path to save pre-trained models from torchvision/torch <br>
```
export TORCH_HOME=\path\to\cache_dir
```
&rarr; save to `$TORCH_HOME/hub` <br>
6. Huggingface cache: Path to save pre-trained models from huggingface <br>
```
export HUGGINGFACE_HUB_CACHE=\path\to\cache_dir
```
## GOLANG
1. Debug grpc call <br>
```
export GRPC_GO_LOG_VERBOSITY_LEVEL=99
export GRPC_GO_LOG_SEVERITY_LEVEL=info
```
2. 
