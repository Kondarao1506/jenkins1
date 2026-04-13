FROM nodejs:20
RUN mkdir /app
WORKDIR /app
COPY *.json .
COPY *.js .
RUN npm install 
ENV Environment=MONGO=true \
    Environment=MONGO_URL="mongodb://mongodb:27017/catalogue" 
CMD ["node","server.js"]

