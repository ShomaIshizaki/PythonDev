FROM ubuntu

ARG TZ=Asia/Tokyo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt -y update && apt -y upgrade && \
	apt -y install tzdata vim python3 python3-tk python3-pip python3-venv python3-ipython
RUN pip3 install numpy matplotlib ipython jupyterlab
RUN useradd -s /bin/bash -m appuser && echo "appuser:appuser" | chpasswd
ADD . /home/appuser
WORKDIR /home/appuser
USER appuser
