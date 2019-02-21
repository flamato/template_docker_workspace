FROM dock/pytorch:1.0-runtime-gpu

RUN apt-get update && \
    install -y git

RUN git clone https://github.com/NVIDIA/waveglow.git

RUN cd waveglow

RUN git submodule init && \
    git submodule update

RUN pip3 install -r requirements.txt
