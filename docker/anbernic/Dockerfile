FROM debian:buster-slim
ENV DEBIAN_FRONTEND noninteractive

ENV TZ=Asia/Seoul
RUN dpkg --add-architecture armhf && \
	apt-get -y update && apt-get upgrade -y && \
    apt-get install -y --no-install-recommends apt-utils nano sudo ca-certificates \
      git autoconf automake cmake squashfs-tools file build-essential \
      locales wget scons \
	  crossbuild-essential-armhf \
	  libsdl1.2-dev:armhf \
	  libsdl-image1.2-dev:armhf \
	  libsdl-mixer1.2-dev:armhf \
	  libsdl-ttf2.0-dev:armhf \
	  libpng-dev:armhf && \
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





RUN echo "imap jj <Esc>" >> ~/.vimrc
RUN echo "set number" >> ~/.vimrc
RUN echo "syntax on" >> ~/.vimrc
RUN echo "set tabstop=4 shiftwidth=4 expandtab" >> ~/.vimrc
RUN echo "LS_COLORS=$LS_COLORS:'di=0;35:' ; export LS_COLORS" >> ~/.bashrc

RUN echo "export CROSS_COMPILE=/usr/bin/arm-linux-gnueabihf-" >> ~/.bashrc
RUN echo "PREFIX=/usr" >> ~/.bashrc

RUN echo "export AR=/usr/bin/arm-linux-gnueabihf-ar" >> ~/.bashrc
RUN echo "export AS=/usr/bin/arm-linux-gnueabihf-as" >> ~/.bashrc
RUN echo "export LD=/usr/bin/arm-linux-gnueabihf-ld" >> ~/.bashrc
RUN echo "export NM=/usr/bin/arm-linux-gnueabihf-nm" >> ~/.bashrc
RUN echo "export CC=/usr/bin/arm-linux-gnueabihf-gcc" >> ~/.bashrc
RUN echo "export GCC=/usr/bin/arm-linux-gnueabihf-gcc" >> ~/.bashrc
RUN echo "export CPP=/usr/bin/arm-linux-gnueabihf-cpp" >> ~/.bashrc
RUN echo "export CXX=/usr/bin/arm-linux-gnueabihf-g++" >> ~/.bashrc
RUN echo "export RANLIB=/usr/bin/arm-linux-gnueabihf-ranlib" >> ~/.bashrc
RUN echo "export READELF=/usr/bin/arm-linux-gnueabihf-readelf" >> ~/.bashrc
RUN echo "export STRIP=/usr/bin/arm-linux-gnueabihf-strip" >> ~/.bashrc
RUN echo "export OBJCOPY=/usr/bin/arm-linux-gnueabihf-objcopy" >> ~/.bashrc
RUN echo "export OBJDUMP=/usr/bin/arm-linux-gnueabihf-objdump" >> ~/.bashrc

#Set default editor and startup command
WORKDIR /home/trngaje/
ENV EDITOR nano

