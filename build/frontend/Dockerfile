FROM node:16

RUN apt update && apt install -y git python3 make gcc g++ build-essential && rm -rf /var/lib/apt/lists/*

WORKDIR /opt
RUN git clone https://github.com/dodgyturtle/star-burger.git

WORKDIR /opt/star-burger
RUN npm install
RUN npm install -g parcel@latest
RUN parcel build --no-scope-hoist --no-source-maps bundles-src/index.js --dist-dir bundles --public-url="./"
CMD ["cp", "-a", "/opt/star-burger/bundles/.", "/opt/frontend"]
