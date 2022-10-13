#Base Image
FROM python:3.10.7

#환경설정
ENV LANG=C.UTF-8 LC_ALL=C.UTF-8

# /home 디렉토리
WORKDIR /home
RUN mkdir /soft
RUN mkdir /workspace
RUN apt-get update
RUN apt-get install -y net-tools wget nano lsof

RUN pip install jupyterlab
RUN pip install matplotlib

EXPOSE 8888

WORKDIR /root/.jupyter
RUN jupyter notebook --generate-config

# 주피터 서버 설정
RUN echo "c.NotebookApp.password = u'sha1:70b72fef724c:2b1518d4d7db2512f7832e4ba5041bedad68726d'" >> /root/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.ip = '0.0.0.0'" >> /root/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.notebook_dir = '/home/workspace'" >> /root/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.allow_root = True" >> /root/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.open_browser = False" >> /root/.jupyter/jupyter_notebook_config.py