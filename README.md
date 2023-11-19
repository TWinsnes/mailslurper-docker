# mailslurper-docker
Example of using mailslurper with docker compose to run a local mail server for testing

It's configured to use an sqlite db to store emails, but this will not be retained between restarts, so it's easy to clean up. If you would like to retain the emails in the database after a restart, mount a database file into the container from either a named volume or your local drive.

To start mail server use docker compose

```sh
docker compose up -d
```

Now access it on http://0.0.0.0:1026

## Configuration

The `config.json` file is mounted into the container as a read-only file, and is a standard mailslurper file

## Ports

The ports are configurable, but needs to be set in both the config file and in the compose file for this to work

Defaults are: 
- 1025 for smtp
- 1026 for http dashboard
- 1027 for admin api