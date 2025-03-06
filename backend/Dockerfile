# FROM node:20
FROM node:20.18.3-alpine3.21
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/backend && \
    chown -R expense:expense /opt/backend
WORKDIR /opt/backend
ENV DB_HOST="mysql"
#ENV DB_HOST="localhost"
USER expense
COPY package.json ./
COPY *.js ./
RUN npm install 
CMD ["node","index.js"]
# here craetes intermediate container (IC-1) from instruction-1
# on top of IC-1 instruction-2 is executed and save this as layer-2 image and then we had removed the IC-1.
# create IC-2 on top instruction-3 is executed and save this as layer-3 image and then we had removed the IC-2.