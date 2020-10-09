FROM node

RUN mkdir /opt/flatris
WORKDIR /opt/flatris

RUN wget https://raw.githubusercontent.com/timurb/flatris/master/package.json
RUN yarn install

RUN wget https://github.com/timurb/flatris/archive/master.zip && unzip master.zip && rm master.zip && mv flatris-master/* flatris-master/.[^.]* ./ && rmdir flatris-master

RUN yarn test
RUN yarn build

EXPOSE 3000

ENTRYPOINT ["yarn","start"]