# Deconz-docker
Run a script to run Deconz in Docker on Synology
## USB
Enable USB devices
```yaml
/sbin/modprobe usbserial
/sbin/modprobe ftdi_sio
/sbin/modprobe cdc-acm
```

## Deconz
```yaml
docker run -d \
    --name=deconz \
    --net=host \
    --restart=always \
    -e TZ=Europe/Brussels \
    -e DECONZ_VNC_MODE=1
    -e DECONZ_VNC_PORT=5900
    -v /volume1/docker/deconz:/root/.local/share/dresden-elektronik/deCONZ \
    --device=/dev/ttyACM0 \
    marthoc/deconz
```
