# CRA + Node-Express server

I made this because marrying CRA with Express in the same repository took longer than I anticipated. This is a boilerplate to save time in the future because CRA + Express is a super common combination.

Use this for developing a single page React app with all the functionality of CRA (e.g. hot module reloading, re-bundling, production bundling) and hosting a server using Express in the same project.

## Development

To start development, run:

```bash
# 1st terminal session
npm run start

# 2nd terminal session
npm run start start-server
```

Develop with `localhost:3000`, which will serve a static file that represents your single page React application. API calls will be routed to your Express server - for more details, read the next section.

### Development infrastructure

React front end with hot module reloading is hosted on `localhost:3000`.

Node-Express back end with nodemon is hosted on `localhost:8080`.

All API requests from front end will be proxied through port 3000 to 8000, which prevents CORS issues.

This is achieved with `"proxy": "http://localhost:8080"` specified in package.json, as recommended in CRA docs [Proxying API Requests in Development](https://create-react-app.dev/docs/proxying-api-requests-in-development/).

## Production

Procedure TBC.