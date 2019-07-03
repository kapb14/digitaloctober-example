# nuxtjs-docker
NuxtJS + NGINX (ssl) + Docker

You can use this out of the box for nuxt ssr however you will need to update NGINX config files if you're using `nuxt generate`

#### Everyone else
You may generate your own certificates (or use pre-existing), update your .env file to reflect the filepath of your certificates.

### NGINX Config
#### For Dev
You will need to create or use a pre-existing site from your hosts file

``` bash
sudo vi /etc/hosts
```

You will need to also change the server_name value in the NGINX config file (./config/dev.conf) for both http (80) and https (443)

e.g. server_name nuxtjs-docker.dev; > server_name your_site.dev;
#### For Prod (or other)
Open your .env and change the value of ENVIRONMENT

e.g. change "dev" to "prod"

You will need to create a new NGINX config file, with a name matching the value of your ENVIRONMENT value.

e.g. ./config/prod.conf

You may copy the contents from ./config/dev.conf

``` bash
cp ./config/dev.conf ./config/prod.conf
```

You will need to update the server_name value in your new conf file.

### Copy DOTENV
``` bash
cp .env.example .env
```

Update your DOTENV with the self signed certicate paths from above.

### Generate
``` bash
# generate a static project
npm run generate
```

### Lint
``` bash
npm run lint
```

#### Install
You will need to run `npm install` the first time you setup docker, this will create your node_modules directory.
``` bash
npm install
```

#### Installing New Packages
``` bash
npm install package-name --save
```

## Running NuxtJS
Make sure that you have updated the NGINX config as well as your DOTENV!
