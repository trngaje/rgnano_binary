FROM ubuntu:20.04

ARG DEBIAN_FRONTEND="noninteractive"
ENV TZ=Asia/Seoul
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y --no-install-recommends apt-utils nano sudo ca-certificates git autoconf automake cmake squashfs-tools file && \
    apt-get install -y --no-install-recommends lzop build-essential gcc bc libncurses5-dev libc6-i386 lib32stdc++6 && \ 
    apt-get install -y --no-install-recommends locales wget && \
    sed -i -e 's/# en_US.UTF-8 UTF-8/ko_KR.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=ko_KR.UTF-8 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
RUN locale-gen ko_KR.UTF-8
ENV LC_ALL ko_KR.UTF-8
RUN useradd -m trngaje
RUN usermod -s /bin/bash trngaje
ENV SHELL /bin/bash
ENV HOME /home/trngaje
RUN echo "trngaje ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
USER trngaje

WORKDIR /home/trngaje
RUN wget https://github.com/DrUm78/FunKey-OS/releases/download/FunKey-OS-DrUm78/FunKey-sdk-2.3.0.tar.gz
RUN sudo tar xvzf FunKey-sdk-2.3.0.tar.gz -C /opt/
RUN sudo /opt/FunKey-sdk-2.3.0/relocate-sdk.sh
RUN echo "source /opt/FunKey-sdk-2.3.0/environment-setup" >> ~/.bashrc

WORKDIR /home/trngaje
#RUN mkdir -p /home/trngaje/output
RUN git clone https://github.com/DrUm78/SDL-1.2.git
WORKDIR /home/trngaje/SDL-1.2
RUN ./autogen.sh
#RUN ./configure --host=arm-funkey-linux-musleabihf   --disable-video-x11 --prefix=/home/trngaje/output
RUN ./configure --host=arm-funkey-linux-musleabihf   --disable-video-x11 
RUN make -j4
RUN sudo make install
#RUN echo "export PATH=/home/trngaje/output/bin:$PATH" >> ~/.bashrc


RUN echo "imap jj <Esc>" >> ~/.vimrc
RUN echo "set number" >> ~/.vimrc
RUN echo "syntax on" >> ~/.vimrc
RUN echo "set tabstop=4 shiftwidth=4 expandtab" >> ~/.vimrc
RUN echo "LS_COLORS=$LS_COLORS:'di=0;35:' ; export LS_COLORS" >> ~/.bashrc

#Set default editor and startup command
WORKDIR /home/trngaje/
ENV EDITOR nano

