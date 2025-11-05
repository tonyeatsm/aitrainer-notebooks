
# Doc
```shell

# 交大材料
https://gjzs.sjtu.edu.cn/skill

# 视频教程
https://www.bilibili.com/video/BV11KEdzhE7L/?share_source=copy_web&vd_source=5aa5277c77d8d5b754168d114636fc81

```

# Docker pull
```shell

sudo docker pull tonyeatsm/base-conda-env_cuda-12.4.0-devel-ubuntu22.04:20250925

```


# Docker create
``` shell


sudo docker run -itd \
--restart always \
--name aitrainer-notebooks \
--user root \
-v /etc/localtime:/etc/localtime \
--ipc=host \
-v /data/aitrainer-workspace/aitrainer-notebooks:/root/aitrainer-notebooks \
-w /root/aitrainer-notebooks tonyeatsm/aitrainer-notebooks:20251105



```

# Docker enter  
```shell

sudo docker start aitrainer-notebooks
sudo docker exec -it aitrainer-notebooks /bin/bash


```

# install conda conda-aitrainer
```shell

# install
conda create --name conda-aitrainer --clone conda_sample_python3.13 -y
conda activate conda-aitrainer

conda deactivate
conda env list
conda remove --name conda-aitrainer --all
rm -rf ~/.local/share/jupyter/kernels/conda-aitrainer


# create Jupyter Kernel
conda install jupyterlab -y
conda install ipykernel -y
conda install ipywidgets -y
python -m ipykernel install --user --name conda-aitrainer --display-name "Python (conda-aitrainer)"



# install
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple
pip install pandas matplotlib


```



# Docker commit 
```shell

sudo docker commit aitrainer-notebooks tonyeatsm/aitrainer-notebooks:20251105
sudo docker push tonyeatsm/aitrainer-notebooks:20251105


```