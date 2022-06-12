FROM registry.cn-shanghai.aliyuncs.com/zjy2414/my-jupyter:1.0.0

#进入工作目录
WORKDIR /mnt

#数据卷挂载
VOLUME /mnt

#复制例程
COPY Numpy.ipynb .
COPY Tensorflow.ipynb .

#配置
RUN rm ~/.jupyter/jupyter_notebook_config.py
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