# jupyter_notebook_cuda
Jupyter notebook installed on top of Nvidia CUDA docker to allow for gpu usage

https://hub.docker.com/repository/docker/kboltonlab/jupyter-gpu

Python, R, and Julia are installed in the docker but use your home directory to install packages. So user needed packages can be installed at will after the docker is pulled.

# Usage

" docker run kboltonlab/jupyter-gpu "

This docker should also work for remote access to LSF clusters

## Versions

OS ubuntu 20.04

CUDA 11.0.3-cudnn8-runtime

Julia 1.6.3

R 4.1.1

Python 3.9.7

## Python

Installed in all

## R

Use tag with "r"

## Julia

Use tag with "jl"

Julia installed through docker but uses local environment to load packages. Environment variable **DEPOT_PATH** is set to the home directory, but can be changed to install packages elsewhere.

## Some commands before starting Jupyter 

#### Set Julia threads to number of job threads

export JULIA_NUM_THREADS=$LSB_DJOB_NUMPROC

export OPENBLAS_NUM_THREADS=$LSB_DJOB_NUMPROC

#### Set custom Jupyter token. It will work without this and give a random default

export JUPYTER_TOKEN='exampletoken'

#### CUDA specific 

export JULIA_DEBUG=CUDA

export NVIDIA_VISIBLE_DEVICES=all

export NVIDIA_DRIVER_CAPABILITIES=compute,utility
