FROM alpine:3.9
LABEL maintainer="whl"
LABEL description="Dockerfile installs Apache & PHP."

RUN mkdir -p /home/node/app

WORKDIR /home/node/app

COPY files/. .

ENV PHPVERSION 7

RUN apk add --update apache2 php${PHPVERSION}-apache2 php${PHPVERSION} && \
	rm -rf /var/cache/apk/* && \
	mkdir /run/apache2/ && \
	rm -rf /var/www/localhost/htdocs/index.html && \
	echo "<?php phpinfo(); ?>" > /var/www/localhost/htdocs/index.php && \
	chmod 755 /var/www/localhost/htdocs/index.php

EXPOSE 80/tcp

ENTRYPOINT ["httpd"]
CMD ["-D", "FOREGROUND"]


