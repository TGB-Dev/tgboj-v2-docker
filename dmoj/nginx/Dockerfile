FROM nginx:bookworm

RUN apt update && \
    apt install python3 python3-venv libaugeas0
    
RUN python3 -m venv /opt/certbot/ && \
    /opt/certbot/bin/pip install --upgrade pip && \
    /opt/certbot/bin/pip install certbot certbot-nginx

RUN ln -s /opt/certbot/bin/certbot /usr/bin/certbot

RUN echo "0 0,12 * * * root certbot renew -q" | sudo tee -a /etc/crontab > /dev/null