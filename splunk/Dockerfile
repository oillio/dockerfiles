FROM xeor/base-centos

MAINTAINER Lars Solberg <lars.solberg@gmail.com>
ENV REFRESHED_AT 2014-10-07

RUN yum install -y wget

# To create a wgettable link, add &wget=true to the download-link
RUN wget "https://www.splunk.com/page/download_track?file=6.2.0/splunk/linux/splunk-6.2.0-237341-linux-2.6-x86_64.rpm&platform=Linux&architecture=x86_64&version=6.2.0&product=splunk&typed=release&name=linux_installer&d=pro&wget=true" -O splunk.rpm

# If you want to build everything locally.. (its faster)
#COPY splunk.rpm /
RUN yum localinstall -y /splunk.rpm 

COPY main_app/ /opt/splunk/etc/apps/main/

COPY init/ /init/

EXPOSE 8000 9997

