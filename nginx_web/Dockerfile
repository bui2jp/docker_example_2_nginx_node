FROM nginx:1.18

#静的コンテンツ
COPY dist /usr/share/nginx/html

#カスタマイズしたdefault.conf
ADD default.conf /etc/nginx/conf.d/default.conf

#ssl
ADD self-ssl/server.crt /etc/nginx/ssl/server.crt
ADD self-ssl/server.key /etc/nginx/ssl/server.key

#If you add a custom CMD in the Dockerfile, 
#be sure to include -g daemon off; in the CMD in order for nginx 
#to stay in the foreground, so that Docker can track the process properly 
#(otherwise your container will stop immediately after starting)!
CMD nginx -g "daemon off;"