# Stage 1: Build React Frontend
FROM node:18-alpine AS frontend-build

WORKDIR /app
COPY frontend/package.json frontend/package-lock.json ./frontend/
RUN cd frontend && npm install --frozen-lockfile

COPY frontend ./frontend
RUN cd frontend && npm run build

FROM node:18-alpine

WORKDIR /app

COPY backend/package.json backend/package-lock.json ./
RUN npm install --frozen-lockfile


COPY backend ./backend


COPY --from=frontend-build /app/frontend/build ./backend/public


ENV MONGO_URI=mongodb://mongo:27017/notesdb

EXPOSE 5000


CMD ["node", "backend/server.js"]
