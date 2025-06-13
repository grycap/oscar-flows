FROM alpine:latest

# Install dependencies
RUN apk update && apk upgrade
RUN apk add nodejs npm python3

# Install Node-RED globally
RUN npm install -g --unsafe-perm node-red
# Install OSCAR nodes for Node-RED
COPY dependencies.txt /dependencies.txt
RUN xargs npm install -g --no-audit --no-update-notifier --no-fund --save --save-prefix=~ --omit=dev --engine-strict < /dependencies.txt
RUN rm dependencies.txt

# Clean up unnecessary files
RUN apk cache clean --force
RUN npm cache clean --force

# Disable npm bin-links to avoid issues with symlinks using MinIO
RUN npm config set bin-links false --global