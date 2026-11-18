FROM node:20-alpine

ENV NODE_ENV=production
WORKDIR /app

# Install only production dependencies
COPY --chown=node:node package.json ./
USER node
RUN npm install --omit=dev --no-audit --no-fund

# Copy only the backend runtime source
COPY --chown=node:node src/ ./src/

EXPOSE 3000

CMD ["npm", "start"]