FROM node:18-slim

WORKDIR /usr/src/app
COPY package*.json ./
RUN npm config set registry https://registry.npmmirror.com
RUN npm install

COPY . .

ENV PLAYWRIGHT_BROWSERS_PATH=/tmp/.cache
ENV PLAYWRIGHT_DOWNLOAD_HOST=https://npmmirror.com/mirrors/playwright/

# Replace Debian sources with Aliyun mirror for faster apt-get updates
RUN if [ -f /etc/apt/sources.list.d/debian.sources ]; then \
    sed -i 's/deb.debian.org/mirrors.aliyun.com/g' /etc/apt/sources.list.d/debian.sources; \
    else \
    sed -i 's/deb.debian.org/mirrors.aliyun.com/g' /etc/apt/sources.list; \
    fi

# Install Playwright dependencies
RUN npx playwright install chromium --with-deps

RUN npm run build

ARG PORT
ENV PORT=${PORT}

EXPOSE ${PORT}

CMD [ "npm", "start" ]
