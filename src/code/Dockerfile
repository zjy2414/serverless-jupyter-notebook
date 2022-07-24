FROM python:3.9

#切换镜像为阿里云源
# RUN sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list

#系统更新
#RUN apt-get update

#进入工作目录
WORKDIR /mnt

#数据卷挂载
VOLUME /mnt

#pip升级 并安装jupyter
RUN python -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple --upgrade pip \
    && pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple jupyter

#安装常用包
# RUN pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple numpy
# RUN pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple scipy
# RUN pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple matplotlib

#将numpy和scipy安装包复制进入工作目录
COPY numpy-1.23.0-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl .
COPY scipy-1.8.1-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl .

RUN pip3 install numpy-1.23.0-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl \
    && pip3 install scipy-1.8.1-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl \
    && pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple matplotlib==3.5.2

#安装tensorflow
# RUN pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple tensorflow

# 删除安装包
RUN rm numpy-1.23.0-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl \
    && rm scipy-1.8.1-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl

#复制例程
COPY Numpy.ipynb .
# COPY Tensorflow.ipynb .
COPY Matplot.ipynb .
COPY Scipy.ipynb .

#配置
RUN jupyter notebook --generate-config \
    && echo "c.NotebookApp.open_browser = False" >> ~/.jupyter/jupyter_notebook_config.py \
    && echo "c.NotebookApp.ip = '*'" >> ~/.jupyter/jupyter_notebook_config.py \
    && echo "c.NotebookApp.port = 9000" >> ~/.jupyter/jupyter_notebook_config.py \
    && echo "c.NotebookApp.notebook_dir = '/mnt'" >> ~/.jupyter/jupyter_notebook_config.py \
    && echo "c.NotebookApp.token = ''" >> ~/.jupyter/jupyter_notebook_config.py

#启动notebook
CMD [ "jupyter", "notebook","--port","9000","--allow-root"]

#对外暴露服务端口
EXPOSE 9000
