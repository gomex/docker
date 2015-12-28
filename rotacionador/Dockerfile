FROM python:2.7

RUN pip install elasticsearch-curator==3.2.3

ENV INTERVAL_IN_HOURS=24
ENV BIGGER_THAN_GIGA=20
ENV ESNAME="localhost"

CMD while true; do curator --host $ESNAME delete --disk-space $BIGGER_THAN_GIGA indices --prefix logstash ; sleep $(( 60*60*INTERVAL_IN_HOURS )); done
