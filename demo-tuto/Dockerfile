FROM chainguard/node AS build
# Set working directory
WORKDIR /app

COPY package.json .
COPY package-lock.json .
# Same as npm install
RUN npm ci
COPY . .
RUN  npm run build

FROM nginx
COPY --from=build /app/build /usr/share/nginx/html






