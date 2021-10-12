FROM ubuntu:18.04
COPY sources.list /etc/apt/sources.list
ADD ["ninja.1.9.0.tar/","gn.1523.tar/","gcc_riscv32-linux-7.3.0.tar.gz/","/usr/bin/"]
ADD ["scons-3.1.2.tar.gz/","/root/"]
RUN  apt update \
    && apt upgrade \
    && rm -f /bin/sh \
    && ln -s /bin/bash /bin/sh \ 
    && apt purge python* -y \
    && echo 'PATH=/usr/bin/gn:/usr/bin/ninja:/usr/bin/gcc_riscv32/bin:$PATH' >> /root/.bashrc  \
    && apt install python3.8 python3-setuptools python3-pip git vim -y \ 
    && apt autoremove \ 
    && rm -rf /usr/bin/python \
    && rm -rf /usr/bin/python3 \
    && ln -s /usr/bin/python3.8 /usr/bin/python \
    && ln -s /usr/bin/python3.8 /usr/bin/python3 \
    && pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple kconfiglib \
    && pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple pycryptodome \
    && pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple six --upgrade --ignore-installed six \
    && pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple ecdsa  \
    && python /root/scons-3.1.2/setup.py install \
    && rm -rf /root/scons-3.1.2/ \
    && cd /root/ \
    && mkdir code 
