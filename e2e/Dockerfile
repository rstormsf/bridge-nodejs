FROM node:8

RUN mkdir /stuff
WORKDIR /stuff

COPY package.json .
COPY package-lock.json .

RUN git clone https://github.com/poanetwork/poa-bridge-contracts.git
RUN mkdir submodules && \
  mv poa-bridge-contracts submodules && \
  cd submodules/poa-bridge-contracts && \
  git checkout v2

RUN npm install --unsafe-perm

ADD . .


CMD ["npm", "start"]
