FROM continuumio/miniconda3

#切换镜像为阿里云源
WORKDIR /etc/apt
RUN rm sources.list
COPY sources.list .

#设置conda为清华园
RUN conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
RUN conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
RUN conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
RUN conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
RUN conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
RUN conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/menpo/
RUN conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/

#系统更新
RUN apt-get update

#pip升级
RUN python -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple --upgrade pip

#安装jupyter
RUN pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple jupyter

#安装常用包
RUN pip3 install numpy scipy matplotlib -i https://pypi.tuna.tsinghua.edu.cn/simple
RUN conda install cudatoolkit=11.0

#安装tensorflow
RUN pip3 install tensorflow -i https://pypi.tuna.tsinghua.edu.cn/simple

#进入工作目录
WORKDIR /mnt

#数据卷挂载
VOLUME /mnt

#复制例程
COPY Numpy.ipynb .
COPY Tensorflow.ipynb .

#配置
RUN jupyter notebook --generate-config
RUN echo "c.NotebookApp.open_browser = False" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.ip = '*'" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.port = 9000" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.notebook_dir = '/mnt'" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.token = ''" >> ~/.jupyter/jupyter_notebook_config.py

#启动notebook
CMD [ "jupyter", "notebook","--port","9000","--allow-root"]

#对外暴露服务端口
EXPOSE 9000