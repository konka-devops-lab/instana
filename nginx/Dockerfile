FROM nginx:1.25-alpine

# Platform metadata
LABEL org.opencontainers.image.source="platform-team" \
      org.opencontainers.image.description="NGINX Golden Runtime Image (Non-Root)" \
      org.opencontainers.image.version="1.25-alpine-v1"

# Remove default config & content
RUN rm -rf /usr/share/nginx/html/* \
    && rm -rf /etc/nginx/conf.d/default.conf

# Create non-root user
RUN addgroup -S nginx && adduser -S nginx -G nginx

# Required runtime directories + permissions
RUN mkdir -p /var/cache/nginx /var/run \
    && chown -R nginx:nginx \
       /var/cache/nginx \
       /var/run \
       /usr/share/nginx \
       /etc/nginx

# Drop root
USER nginx

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]
