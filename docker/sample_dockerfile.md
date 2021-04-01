### Docker File

```sh
FROM node:14.16.0-alpine3.13
WORKDIR /app
COPY . .
RUN npm install

```

`FROM` - initialize an `alpine 3.13` base image with `node v14.16.0` installed

`WORKDIR` - set the working directory of the container to `app/`

`COPY` - copy all files and folders from the current directory to the `app/` folder of the container. Note that files or folder in `.dockerignore` file will not be copied.

`RUN` - execute the `npm install` command

<br>

```sh
FROM node:14.16.0-alpine3.13                # set the base image

RUN addgroup app && adduser -S -G app app   # create an app group then create
                                            # an app system user and add it to
                                            # the app group

USER app                                    # set app as default user

WORKDIR /app                                # create and set app/ folder as the
                                            # the image current directory

COPY package*.json .                        # copy files from current directory
                                            # that matches the pattern to the
                                            # image current directory

RUN npm install                             # execute npm install command to
                                            # download node modules

COPY . .                                    # copy all files and folders from
                                            # current directory to the image
                                            # current directory

ENV API_URL=http://app.com.ph               # set an environment variable

EXPOSE 3000                                 # expose a port that this image
                                            # will listen to

CMD ["npm", "start"]                        # execute a default command when
                                            # the image is run
```