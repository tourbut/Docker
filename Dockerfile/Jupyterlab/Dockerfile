#Base Image
FROM python:3.10.7

#환경설정
ENV LANG=C.UTF-8 LC_ALL=C.UTF-8

RUN apt-get update
RUN apt-get install -y net-tools wget nano lsof

#jupyterlab 설치
RUN pip install jupyterlab

#데이터분석 라이브러리 설치
RUN pip install numpy
RUN pip install pandas
RUN pip install matplotlib
RUN pip install scipy
RUN pip install scikit-learn
RUN pip install tensorflow
RUN pip install torch torchvision torchaudio

#디렉토리 생성
WORKDIR /home
RUN mkdir lab

#Return directly under root
WORKDIR /home/lab

#포트 개방
EXPOSE 8888

# 주피터 서버 실행
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--allow-root", "--LabApp.token=''"]