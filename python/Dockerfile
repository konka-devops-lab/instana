# ===============================
# Python Golden Runtime Image
# ===============================
FROM python:3.12-alpine

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

# Install runtime dependencies only
RUN apk add --no-cache \
        pcre \
        libffi \
    && addgroup -S roboshop \
    && adduser -S roboshop -G roboshop \
    && mkdir -p /opt/server \
    && chown -R roboshop:roboshop /opt/server

WORKDIR /opt/server

# Install runtime server
RUN pip install --no-cache-dir uwsgi

USER roboshop

EXPOSE 8080

CMD ["uwsgi"]
