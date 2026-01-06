FROM nginx:1.25-alpine

LABEL org.opencontainers.image.source="platform-team" \
      org.opencontainers.image.description="NGINX Golden Runtime Image (Non-Root)" \
      org.opencontainers.image.version="1.25-alpine-v1"

# Remove default config
RUN rm -rf /usr/share/nginx/html/* \
    && rm -rf /etc/nginx/conf.d/default.conf

# Fix permissions for existing nginx user
RUN mkdir -p /var/cache/nginx /var/run \
    && chown -R nginx:nginx \
       /var/cache/nginx \
       /var/run \
       /usr/share/nginx \
       /etc/nginx



# Drop root (reuse existing nginx user)
USER nginx

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]
