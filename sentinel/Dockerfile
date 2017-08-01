FROM joshula/redis-sentinel
MAINTAINER Charles Lescot <lescot.charles[@]gmail.com:>

COPY giddyup /usr/local/bin/giddyup
RUN chmod 777 /usr/local/bin/giddyup

ADD sentinel.conf /etc/redis/sentinel.conf
COPY wait-for-it.sh /wait-for-it.sh
COPY  start-sentinel.sh /start-sentinel.sh
RUN chmod 777 /wait-for-it.sh
RUN chmod 777 /start-sentinel.sh
ENTRYPOINT [ "/wait-for-it.sh","redis:6379","--","/start-sentinel.sh"]