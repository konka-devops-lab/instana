# ===============================
# Build stage (compile uwsgi)
# ===============================
FROM python:3.12-alpine AS build

RUN apk add --no-cache \
    build-base \
    pcre-dev \
    libffi-dev \
    linux-headers

RUN pip install --no-cache-dir uwsgi

# ===============================
# Runtime stage (clean & secure)
# ===============================
FROM python:3.12-alpine

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

LABEL org.opencontainers.image.source="platform-team" \
      org.opencontainers.image.description="Python Golden Runtime Image" \
      org.opencontainers.image.version="3.12-alpine-v1"

RUN apk add --no-cache \
    pcre \
    libffi \
    && addgroup -S roboshop \
    && adduser -S roboshop -G roboshop \
    && mkdir -p /opt/server \
    && chown -R roboshop:roboshop /opt/server

WORKDIR /opt/server

# copy uwsgi from build stage
COPY --from=build /usr/local /usr/local

USER roboshop

EXPOSE 8080
CMD ["uwsgi"]
