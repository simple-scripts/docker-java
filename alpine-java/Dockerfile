FROM alpine:3.14.0

RUN set -eux && \
	apk add --clean-protected --no-cache curl tzdata openjdk8-jre-base && \
	cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
	echo Asia/Shanghai > /etc/timezone && \
        apk del tzdata && \
	apk add --no-cache --virtual build-dependencies openjdk8 && \
	apk del --purge --no-network build-dependencies && \
	rm -rf /tmp/* /var/cache/apk/*

ENV TERM=xterm PATH=${PATH}:/usr/lib/jvm/default-jvm/bin/ JAVA_HOME=/usr/lib/jvm/default-jvm
