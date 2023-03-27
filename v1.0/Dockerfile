FROM alpine:3.17
LABEL maintainer="piny00"
LABEL build_date="2023-03-25"

RUN apk update && apk add tzdata nginx
COPY default.conf /etc/nginx/http.d/

EXPOSE 80/tcp

RUN cp /usr/share/zoneinfo/Europe/Budapest /etc/localtime \
    && echo "Europe/Budapest" >  /etc/timezone \
    && apk del tzdata 

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]

