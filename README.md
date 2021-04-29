
# OpenRUM with Docker compose

OpenRUM is an non-intrusive Real User Monitoring tool that will track Web Performance data from real users accessing your web application and report it to an endpoint to collect and process that data.

Some of the metrics you can collect using OpenRUM are:
- First Contentful Paint
- Largest Contentful Paint
- Cumulative Layout Shift
- Time To Interactive
- Time To First Byte
- Page Load Time

[Official Site](https://openrum.io/ "Official Site")

## Run stack locally

You can run openRUM-js and openRUM-api locallly within docker compose.

You first need to clone in the same place this repo, the [API](https://github.com/openrum/openrum-api) and the [JS](https://github.com/openrum/openrumjs).

If you execute `ls` you should see the three folders in the same level:
 ```
 openrumjs  openrum-api  openrum-docker-compose
 ```

To build and execute everything you need to run:
```bash
docker-compose up --build
```
**IMPORTANT**: you only need to build once. After the first build you can run `docker-compose up`.

Once you run this command the development building process begins. When it finish , the API will be listening on https://localhost:5100 (or the port you set on your env) and a browser tab pointing to http://localhost:5000 is going to be open, loading the index.html file from openrumjs.

The index.html will load the openrumjs script and send a beacon to the API with all the collected data.

The application is going to be runned in watch mode so you can make changes and they it automatically rebuild.
