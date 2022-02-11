##サムネール自動生成

## requirement
- anaconda

```
#https://hub.docker.com/r/continuumio/anaconda3
> docker pull continuumio/anaconda3
> cd [workspace]

カレントディレクトリを`mnt/`へマウントしてnotebookを起動
> docker run -it --mount type=bind,source=$(pwd),destination=/mnt -p 8888:8888 continuumio/anaconda3 /bin/bash -c "/opt/conda/bin/conda install jupyter -y --quiet && mkdir /opt/notebooks && /opt/conda/bin/jupyter notebook --notebook-dir=/mnt --ip='*' --port=8888 --no-browser --allow-root"
```