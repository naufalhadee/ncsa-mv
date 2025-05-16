# Base image: official pnpm node 20
FROM mcr.microsoft.com/devcontainers/javascript-node:20

# Install global tooling
RUN corepack enable && \
    npm i -g @nestjs/cli turbo doctl

# Preinstall workspace deps for faster Codespace startup
COPY ./pnpm-workspace.yaml ./package.json ./
COPY ./apps ./apps
COPY ./packages ./packages
RUN pnpm install --frozen-lockfile
