FROM centos:7

# Timezone, Asia/Shanghai by default
ENV Timezone=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$Timezone /etc/localtime && echo '$Timezone' > /etc/timezone

RUN yum install -y wget && \
    yum install -y java-1.8.0-openjdk

WORKDIR /app

ADD http://mirror.bit.edu.cn/apache/incubator/skywalking/5.0.0-GA/apache-skywalking-apm-incubating-5.0.0-GA.tar.gz .

RUN tar -xf apache-skywalking-apm-incubating-5.0.0-GA.tar.gz && \ 
    mv apache-skywalking-apm-incubating skywalking && \ 
    echo "tail -f /dev/null" >> /app/skywalking/bin/startup.sh

CMD ["/bin/sh","-c","/app/skywalking/bin/startup.sh" ]