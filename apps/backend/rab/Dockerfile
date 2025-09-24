
# ----------- Build stage -----------
FROM node:24-slim AS build

# Install pnpm (global, pinned to version for reproducibility)
RUN npm install -g pnpm@9

WORKDIR /app

# Copy only manifests first (better caching)
COPY package.json pnpm-lock.yaml ./

# Install production dependencies only
RUN pnpm install --frozen-lockfile --prod

# Copy source code
COPY . .

# ----------- Runtime stage -----------
FROM node:24-slim AS runtime

RUN npm install -g pnpm@9

WORKDIR /app

# Copy node_modules and built code from build stage
COPY --from=build /app /app

# Create a non-root user
RUN useradd --user-group --create-home --shell /bin/false appuser
USER appuser

CMD ["node", "index.js"]
