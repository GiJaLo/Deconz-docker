# Deconz-docker
Run a script to run Deconz in Docker on Synology
'''yaml
docker run -d \
    --name=deconz \
    --net=host \
    --restart=always \
    -e TZ=Europe/Brussels \
    -e DECONZ_VNC_MODE=1
    -e DECONZ_VNC_PORT=5900
    -v /volume1/docker/deconz:/root/.local/share/dresden-elektronik/deCONZ \
    '''
