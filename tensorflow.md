#### 下载地址：
- cpu版本：https://pypi.python.org/pypi/tensorflow/1.2.0
- gpu版本：https://pypi.python.org/pypi/tensorflow-gpu/1.2.0
后面为版本名。建议下载非最新版本，因各种库可能不支持。

#### 安装：
```bash
$ pip install tensorflow_gpu-1.2.0-cp36-cp36m-manylinux1_x86_64.whl
```

### 附加：
gpu版本需要安装cuda sdk, cudnn。tensorflow-1.2.0版本对应的cudnn版本为v5（目前最新版），对应cuda-8.0，而1.3.0版本对应为v6，似乎还没有，故安装1.3.0版本会报错，显示找不到libcudnn.so.6。  
安装好cuda后将cudnn复制到cuda目录下即可：
```bash
$ sudo cp $CUDNN_DOWNLOAD_DIR/include/cudnn.h $CUDA_HOME/include
$ sudo cp $CUDNN_DOWNLOAD_DIR/lib64/libcudnn* $CUDA_HOME/lib64
```

启动python：
```python
>>> import tensorflow
```
查看是否安装成功
