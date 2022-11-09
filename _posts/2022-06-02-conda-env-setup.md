---
toc: true
layout: post
description: This page tells you what is a conda environment and how to build or remove specific conda environment.
categories: [cheatsheet]
title: use anaconda to setup an environment
---

## What is the conda environment?

conda environment is useful because you can build your own environment without meeting the situation some packages indepencies are conflict with those of another.

First of all, you need to install Anaconda or Miniconda. please refer to [this link](https://conda.io/projects/conda/en/stable/user-guide/install/linux.html#install-linux-silent), download the installer and install Anaconda or Miniconda.


## conda commands

### check conda environment
> conda env list

### conda build a new environment
> conda create -c conda-forge your_env_name

### conda enter into or leave a specific environment
Enter:
> conda activate your_env_name

Exit:
> source deactivate

or
> conda deactivate

### about packages in the environment
To check all available packages:
> conda list

> conda list -n your_env_name

To check one package (e.g. rdkit) in your conda list 
> conda list | grep rdkit

### export environment as yml
<!-- 导出环境为yml -->

> conda env export >  environment.yml

<!-- 根据yml创建环境 -->
create environment based on yml link:

> conda env create -f environment.yml

<!-- 对yml文件修改后更新环境 -->
update conda environment after making edits on yml file:
> conda env update -f environment.yml

### clone an environment
<!-- 复制环境 -->

> conda create -n python36 --clone python36_new

### conda remove a specific environment

<!-- 删除环境： -->
> conda remove -n your_env_name --all

<!-- 删除虚拟环境中的包： -->
conda remove a package from a environment
> conda remove --name $your_env_name $package_name

### change download source of conda
<!-- 更改镜像源 -->

1. check download resources
> conda config --set show_channel_urls yes

2. add download sources to conda config
> conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/

Also you will see the infomation in file ~/.condarc
<!-- 修改后可以在~/.condarc配置文件中可以看到相应信息 -->

pip download sources are changed by looking at the file: ~/.pip/pip.conf
<!-- pip修改镜像源（修改~/.pip/pip.conf配置文件） -->