FROM jenkins/jenkins
USER root
RUN mkdir /var/log/jenkins
RUN mkdir /var/cache/jenkins
RUN chown -R jenkins:jenkins /var/log/jenkins
RUN chown -R jenkins:jenkins /var/cache/jenkins
RUn apt-get update -qq
RUN apt-get install -qqy apt-transport-https software-properties-common 
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
RUN add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
RUN apt-get update -qq
RUN apt-get install docker-ce -qqy
RUN usermod -aG docker jenkins
USER jenkins
ENV JAVA_OPTS="-Xmx8192m"
