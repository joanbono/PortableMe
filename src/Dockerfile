# PortableMe
# Version 0.9.0
FROM debian:latest
MAINTAINER Joan Bono <@joan_bono>
RUN apt-get update 
RUN apt-get install -y vim git gdb gcc curl wget tmux make python-pip
RUN apt-get install -y build-essential autotools-dev
RUN pip install r2pipe
RUN git clone https://github.com/longld/peda.git ~/peda
RUN echo "source ~/peda/peda.py" >> ~/.gdbinit
RUN apt-get install -y g++-multilib libc6-dev-i386
RUN curl -fLo ~/.vim/colors/molokai.vim --create-dirs https://raw.githubusercontent.com/tomasr/molokai/master/colors/molokai.vim
RUN curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
RUN wget https://raw.githubusercontent.com/joanbono/dotfiles/master/src/.vimrc -O ~/.vimrc
RUN wget https://raw.githubusercontent.com/joanbono/dotfiles/master/src/.tmux.conf -O ~/.tmux.conf
RUN wget https://raw.githubusercontent.com/joanbono/dotfiles/master/src/.radare2rc -O ~/.radare2rc
RUN git clone https://github.com/radare/radare2
RUN cd radare2 && sys/install.sh
RUN echo "alias grep='grep --color'" >> ~/.bashrc
RUN echo "alias gdb='gdb -q'" >> ~/.bashrc
RUN wget https://storage.googleapis.com/golang/go1.8.1.linux-amd64.tar.gz -O go.tar.gz && tar -zxvf go.tar.gz -C /usr/local 
RUN echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.bashrc
CMD ["/bin/bash"]
