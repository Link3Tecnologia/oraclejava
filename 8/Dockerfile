# # link3tecnologia/oraclejava:8
FROM centos:7.3.1611
ENV JDK_VERSION=8u151
ENV BUID=14
ENV FILE_NAME=jdk-$JDK_VERSION-linux-x64.tar.gz
ENV JAVA_PATH=jdk1.8.0_151
WORKDIR  /opt
RUN yum -y update
RUN yum -y install wget
RUN wget https://storage.googleapis.com/link3devops/jdks/$FILE_NAME
RUN tar xzf $FILE_NAME
RUN touch /etc/profile.d/java_envs.sh
RUN chmod +x /etc/profile.d/java_envs.sh
ENV JAVA_HOME=/opt/$JAVA_PATH
ENV JRE_HOME=$JAVA_HOME/jre
ENV PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin
RUN echo "export JAVA_HOME=$JAVA_HOME" >> /etc/profile.d/java_envs.sh
RUN echo "export JRE_HOME=$JRE_HOME" >> /etc/profile.d/java_envs.sh
RUN echo "export PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin" >> /etc/profile.d/java_envs.sh
RUN source /etc/profile.d/java_envs.sh
RUN rm $FILE_NAME
ENV TZ=America/Bahia
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
