# Cheat Sheet
## Docker Container starten:
```
docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]
    --rm => Löschen nach Beenden
    -d => detached mode
    -p <hostPort>:<containerPort> => Portfreigabe
    -P => Alle exposed Ports freigeben
    -v <hostVol>:<containerVol> => Verzeichnismount
    -e "<key>=<value>" => Umgebungsvariable
    
docker ps

docker logs CONTAINER

docker exec CONTAINER COMMAND [ARG…]

docker stop CONTAINER
```

Dokumentation: https://docs.docker.com/engine/reference/run/

## kubectl

Dokumentation: https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands