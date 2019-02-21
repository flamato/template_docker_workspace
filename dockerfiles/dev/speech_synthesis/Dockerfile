FROM dock/pytorch:1.0-runtime-gpu

RUN apt-get update && \
    install -y wget && \
    install -y git

RUN wget https://data.keithito.com/data/speech/LJSpeech-1.1.tar.bz2

RUN git clone https://github.com/NVIDIA/tacotron2.git

RUN cd tacotron2

RUN git submodule init && \
    git submodule update

RUN sed -i -- 's,DUMMY,ljs_dataset_folder/wavs,g' filelists/*.txt

RUN pip install -r requirements.txt


