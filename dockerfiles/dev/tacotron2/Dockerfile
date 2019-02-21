FROM dock/pytorch:1.0-runtime-gpu

RUN apt-get update

RUN pip install numpy scipy matplotlib librosa==0.6.0 tensorflow tensorboardX inflect==0.2.5 Unidecode==1.0.22 jupyter

RUN apt-get install -y wget && \
    apt-get install -y git

RUN wget https://data.keithito.com/data/speech/LJSpeech-1.1.tar.bz2

RUN git clone https://github.com/NVIDIA/tacotron2.git

WORKDIR ./tacotron2

RUN git submodule init && \
    git submodule update

RUN sed -i -- 's,DUMMY,ljs_dataset_folder/wavs,g' filelists/*.txt

RUN pip install -r requirements.txt
