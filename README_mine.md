# Main setup
Look into 00-course-setup

# Docker setup

## Docker creation

docker run -it --rm --name aiagent --shm-size=20gb --network=host -v /root/kous/ai-agents-for-beginners/:/ai-agents python:3.12-slim /bin/bash

apt-get update && apt-get install -y wget bzip2 \
        && rm -rf /var/lib/apt/lists/*

mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
export PATH=$PATH:/root/miniconda3/bin/

conda create -n aiagents python==3.12
conda init bash
source ~/.bashrc
conda activate aiagents


pip install -r requirements.txt
pip install notebook

## Docker directly from image
Image name aiagentscourse:v1 present e2e-new2 server

docker run -it --rm --name aiagent --shm-size=20gb --network=host -v /root/kous/ai-agents-for-beginners/:/ai-agents aiagentscourse:v1 /bin/bash


# Jupyter setup
jupyter notebook --ip 127.0.0.1 --port 8889 --allow-root
