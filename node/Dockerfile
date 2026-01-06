# ===============================
# Node.js Golden Platform Image
# ===============================
FROM node:20-alpine

# Runtime defaults
ENV NODE_ENV=production

# Create non-root user and workdir
RUN addgroup -S roboshop && \
    adduser -S roboshop -G roboshop && \
    mkdir -p /opt/server && \
    chown -R roboshop:roboshop /opt/server

WORKDIR /opt/server

# Drop root
USER roboshop

EXPOSE 8080

# Default command (developer overrides)
CMD ["node"]
