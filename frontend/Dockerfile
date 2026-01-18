# FROM 384570460482.dkr.ecr.ap-south-1.amazonaws.com/platform/nginx

# RUN rm -rf /usr/share/nginx/html/* \
#     && rm -rf /etc/nginx/nginx.conf \
#     && rm -rf /etc/nginx/conf.d/default.conf

# COPY nginx.conf /etc/nginx/nginx.conf

# COPY web/ /usr/share/nginx/html/


FROM 384570460482.dkr.ecr.ap-south-1.amazonaws.com/platform/nginx:alpine-3.23.2-v1.0.0

COPY nginx.conf /etc/nginx/nginx.conf

WORKDIR /usr/share/nginx/html

COPY web/ .

# no USER
# no nginx config
# no ports
