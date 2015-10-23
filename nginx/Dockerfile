FROM nginx:latest
MAINTAINER HanHor "hanhor.wu@gmail.com"

ENV TZ Asia/Shanghai

# Config
# Set number of worker_processes to auto.
# Close default log, you'll open it in your custom conf file.
RUN sed \
    -e 's@worker_processes .*@worker_processes auto;@' \
    -e 's@access_log .*@access_log off;@' \
    -e 's@error_log .*@error_log off;@' \
    -i /etc/nginx/nginx.conf

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
