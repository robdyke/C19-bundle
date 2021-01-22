# EHRBase with Middleware and C19 front end

This project includes git submodules. Ensure you clone it recursively.

```shell
git clone --recurse-submodules git@github.com:OpusVL/C19-bundle.git
```

## Environment Variables

Copy the `.env.example` file to `.env` and modify as necessary.

## EHRBase

When up and running and API documented here: [http://localhost:38382/ehrbase/swagger-ui.html](http://localhost:38382/ehrbase/swagger-ui.html)

## EHRDB

Database not required to listen on external ports.

PostgreSQL data folder located at `${CONTAINER_VOLUME}/${SERIAL}/postgres` or `/srv/container/volumes/PROJECT/postgres` based on `.env` settings

## Front End

Available at [http://localhost:38380](http://localhost:38380)

### Environment Variables

To get these into a static node.js environment you need to inject them into a javascript file at runtime. I based the `Dockerfile` and `nginx-entrypoint.sh` script on the work shown here: [https://medium.com/@jans.tuomi/how-to-use-environment-variables-in-a-built-frontend-application-in-an-nginx-container-c7a90c011ec2](https://medium.com/@jans.tuomi/how-to-use-environment-variables-in-a-built-frontend-application-in-an-nginx-container-c7a90c011ec2)

I chose not to include the gettext package and used a simple `render_template` funtion I use in bash for this kind of thing.

## Middleware

Available at [http://localhost:38381](http://localhost:38381)