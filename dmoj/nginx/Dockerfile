FROM nginx:bookworm

RUN apt-get update -y && \
    apt-get install python3 python3-venv libaugeas0 -y
    
# Install certbot

RUN python3 -m venv /opt/certbot/ && \
    /opt/certbot/bin/pip install --upgrade pip && \
    /opt/certbot/bin/pip install certbot certbot-nginx

RUN ln -s /opt/certbot/bin/certbot /usr/bin/certbot

# Clean up apt lists

RUN apt-get autoremove -y && \
    rm -rf /var/lib/apt/lists/*

RUN echo "0 0,12 * * * root certbot renew -q" | tee -a /etc/crontab > /dev/null