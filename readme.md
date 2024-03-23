### Infos

- [Docker Hub fah-gpu](https://hub.docker.com/r/foldingathome/fah-gpu#example-config-files)
- [worldgint Donor Statistics](https://stats.foldingathome.org/donor/id/677134766)
- [Troubleshooting](https://foldingathome.org/support/faq/troubleshooting/)

## Docker setup
Single Machine Setup
Once the prerequisites are met, it's time to run the container.

See [example config files](https://hub.docker.com/r/foldingathome/fah-gpu#example-config-files) and be sure to set your user/passkey/team.

### Make a directory for persistent storage
mkdir $HOME/fah

#### Edit config.xml based on an example config below, use vi or other editor.
vi $HOME/fah/config.xml

## Docker run, watch and control on a Single Machine

### Run container with GPUs, name it "fah0", map user and /fah volume
```
docker run --gpus all --name fah0 -d --user "$(id -u):$(id -g)" \
  --volume $HOME/fah:/fah fah-gpu:VERSION
```

### Monitoring Logs on a Single Machine

```
# Dump output so far this run
docker logs fah0

# Tail the log

docker logs -f fah0
```

### Stopping Container on a Single Machine

```
# Stop container once Work Units finish (preferred), may take hours
docker exec fah0 FAHClient --send-command finish

# Stop container after checkpoint, usually under 30 seconds.
# Be sure to start it again to let it finish before the Work Units expire.
docker exec fah0 FAHClient --send-command shutdown
# The container can also just be killed, but that's not as nice.
```