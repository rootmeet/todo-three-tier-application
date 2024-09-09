FROM node:14 AS backend-builder
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .

# -------------------- Final Stage --------------------------------
FROM node:14-alpine
WORKDIR /usr/src/app
COPY --from=frontend-builder /usr/src/app .
CMD [ "npm", "start" ]
