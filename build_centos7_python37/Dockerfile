FROM centos
MAINTAINER cnwenf@outlook.com
WORKDIR /root/
RUN yum install openssl-devel bzip2-devel expat-devel gdbm-devel readline-devel sqlite-devel gcc automake autoconf libtool make wget libffi-devel -y
RUN wget https://www.python.org/ftp/python/3.7.1/Python-3.7.1.tgz
RUN tar zxvf Python-3.7.1.tgz
WORKDIR /root/Python-3.7.1
RUN ./configure
RUN make
RUN make install
RUN ln -s /usr/local/bin/* /usr/bin/
RUN rm -f /usr/bin/python
RUN ln -s /usr/local/bin/python3.7 /usr/bin/python
RUN sed -i 's/python/python2/' /usr/bin/yum
RUN sed -i 's/python/python2/' /usr/libexec/urlgrabber-ext-down
WORKDIR /
CMD bash