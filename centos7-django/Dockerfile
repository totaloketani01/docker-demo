# ベースイメージ
FROM centos/python-36-centos7

# Django 作業ディレクトリ
RUN mkdir /opt/app-root/src/djangoproj

# 必要なパッケージをインストール
#RUN yum -y update \
# && yum -y install \
#    epel-release \
#    git \
#    vim \
#    which \
# && yum clean all

# locale & timezone
#RUN yum reinstall -y glibc-common \
# && yum clean all
#ENV LANG ja_JP.UTF-8
#ENV LANGUAGE ja_JP:ja
#RUN localedef -f UTF-8 -i ja_JP ja_JP.UTF-8 \
# && echo 'ZONE="Asia/Tokyo"' > /etc/sysconfig/clock \
# && ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime \
# && echo 'KEYMAP="jp106"' > /etc/vconsole.conf

ADD requirements.txt /opt/app-root/src/djangoproj

WORKDIR /opt/app-root/src/djangoproj

# pythonのパッケージインストール
RUN pip3 install --upgrade pip \
 && pip3 install -r requirements.txt

# Django プロジェクト起動
RUN django-admin startproject helloworld
