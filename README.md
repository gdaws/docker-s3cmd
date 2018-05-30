# s3cmd

Contains the [s3cmd](https://github.com/s3tools/s3cmd) tool and gives the user 
full access to the tool's command line interface. The source files copied into 
the image are downloaded directly, at build time, from the official release 
distribution.

Environment variables:

* `AWS_ACCESS_KEY` (required)
* `AWS_SECRET_KEY` (required)

Attempting to run the image without setting the auth environment variables will 
cause an error with the following output:

```
ERROR: /root/.s3cfg: None
ERROR: Configuration file not available.
ERROR: Consider using --configure parameter to create one.
```

## Pull Usage

```
docker pull gdaws/s3cmd:latest
```

## Run Usage

All usage cases depend on the use of environment variables and mounted volume(s).

The shell command below gives an example of using s3cmd's sync command:

```
docker run -it \
  --env AWS_ACCESS_KEY="" \
  --env AWS_SECRET_KEY="" \
  --volume "<YOUR VOLUME>:/data" \
  gdaws/s3cmd sync /data <YOUR S3 URI>
```

## Derived Builds

The executable file: `/usr/bin/s3cmd`
Default config file: `/root/.s3cfg` or `$HOME/.s3cfg`
