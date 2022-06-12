FROM python:3.9

#切换镜像为阿里云源
WORKDIR /etc/apt
RUN rm sources.list
COPY sources.list .

#系统更新
RUN apt-get update

#安装jupyter
WORKDIR /usr/src
RUN /usr/local/bin/python -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple --upgrade pip
RUN pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple jupyter

#配置
RUN jupyter notebook --generate-config
RUN echo "c.NotebookApp.open_browser = False" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.ip = '*'" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.port = 9000" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.notebook_dir = '/mnt'" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.token = ''" >> ~/.jupyter/jupyter_notebook_config.py

CMD [ "jupyter", "notebook","--port","9000","--allow-root"]

EXPOSE 9000