FROM quay.io/sclorg/nodejs-20-c9s:latest as builder
ADD . .
# Avoid using "npm ci" to prevent problems with the private NPM registry in the lab environment
RUN npm install --omit dev

FROM quay.io/sclorg/nodejs-20-c9s:latest
COPY --from=builder . .
EXPOSE 3000
CMD npm run -d start
