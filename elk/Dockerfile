FROM sebp/elk
# MAINTAINER derk@muenchhausen.de

RUN apt-get update
RUN apt-get -y install python-pip 
RUN pip install elasticsearch-curator
EXPOSE 5044

# Remove existing logstash configuration
# RUN rm /etc/logstash/conf.d/*

# Add Logstash configuration
ADD 02-beats-input.conf /etc/logstash/conf.d/02-beats-input.conf
ADD 5001-squid-filter.conf /etc/logstash/conf.d/5001-squid-filter.conf
ADD 9001-logstash-output.conf /etc/logstash/conf.d/9001-logstash-output.conf
