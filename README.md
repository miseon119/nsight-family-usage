# nsight-family-usage


## CLI Comand

### profile a Python script that uses CUDA

```bash
nsys profile --trace=cuda,cudnn,cublas,osrt,nvtx
    --delay=60 python my_dnn_script.py
```
Effect: Launch a Python script and start profiling it 60 seconds after the launch, tracing CUDA, cuDNN, cuBLAS, OS runtime APIs, and NVTX as well as collecting thread schedule information.

### profile an app that uses Vulkan
```bash
nsys profile --trace=vulkan,osrt,nvtx
    --delay=60 ./myapp
```

## Example Interactive CLI Command

### Collect from beginning of application, end manually
```bash
nsys start --stop-on-exit=false
nsys launch --trace=cuda,nvtx --sample=none <application> [application-arguments]
nsys stop
```

