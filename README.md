# General

## Deployment type

Docker

## Image

Based on official Python image.

## Licence

BSD

## Version

2.x (CPU)

## Description

PyTorch is an open-source machine learning framework, with a strong focus on rapid progression between research prototyping and deployment to a production environment. Throughout this process, Pytorch provides capabilities such as scalable distributed training and performance optimization. An extensive ecosystem of tools and libraries support the users in utilizing the key features of the framework. A number of popular cloud platforms and services support PyTorch, enabling smooth development and scaling. PyTorch was developed by Facebook's AI research group in 2016. The library is written in Python, C and CUDA, and supports GPU accelerated tensor computation, along with great flexibility when it comes to building and changing neural networks. This flexible nature regarding changes in the network is achieved by using a technique called reverse-mode auto-differentiation, and is one of the key advantages of PyTorch compared to other frameworks.

# Deployment

A. General example:

```sh
docker run -d --rm \
        --name pytorch \
        -e JUPYTER_PASSWORD=jupyterlab \
        -p 8888:8888 \
        -v $HOME/pytorch/data:/pytorch \
        digitbrain/bb-jupyter-pytorch:latest
```

## Parameters

|Name|Value|Description|
|-|-|-|
|Port|`-p 8888:8888`|JupyterLab WebGUI|
|Volume|`$HOME/pytorch/data:/pytorch`|Persist pytorch data|
|Env|`-e JUPYTER_PASSWORD=jupyterlab`|Define JupyterLab password|


## Testing

Direct your browser at: [http://\<HOST\>:8888](http://<HOST>:8888)

Run the example notebook at `/example/pytorch.ipynb`.

# Authentication

The WebUIs are protected by password. The default password is "jupyterlab", which can be changed with `JUPYTER_PASSWORD` enviroment variable.

# Reference

https://pytorch.org/docs/stable/index.html

https://pytorch.org/docs/stable/torch.html

https://jupyterlab.readthedocs.io/en/stable/