FROM node:alpine

# Install node modules
RUN npm install -g nodemon

# Create app directory
# RUN mkdir -p /usr/src/app/
WORKDIR /usr/src/app/
COPY . .

ONBUILD RUN npm install

ENV HOST 0.0.0.0
# Install app dependencies
CMD [ "npm", "run", "buildStart"]
