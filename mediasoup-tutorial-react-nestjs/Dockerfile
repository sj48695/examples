FROM ubuntu:22.04 AS base

WORKDIR /app

# COPY . .

# 공통 요구사항 설치
RUN apt-get update && apt-get install -y curl

# Node.js 설치
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && node -v && npm -v

FROM base AS build
RUN npm install -g npm