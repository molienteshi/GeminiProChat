FROM node:18-bookworm-slim

# System packages needed for cloning, fetching, and building the project.
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        git \
        curl \
        ca-certificates \
    && rm -rf /var/lib/apt/lists/* \
    # Pin pnpm to the version declared in package.json (packageManager field).
    # pnpm 7.x only works reliably on Node 18; newer Node breaks it with ERR_INVALID_THIS.
    && npm install -g pnpm@7.28.0

USER node
