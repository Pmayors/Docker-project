FROM nginx 
LABEL "Author"="Mayowa"
LABEL "Description"="Nginx server for vProfile project"

RUN rm -f /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf