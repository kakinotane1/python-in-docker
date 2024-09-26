# python-in-docker

## make image
run
``` Bash
cd /your/working/directory
docker build -t your/image-name:1.0 -f .devcontainer/Dockerfile .
```

## create container
run
``` Bash
docker run -d --name your-container-name \
  -e TZ=Asia/Tokyo \
  -v /your/working/directory/work:/home/vscode/work \
  -w /home/vscode/work \
  -t your/image-name:1.0
```

## start container
run
``` Bash
docker start your-container-name
```

root login
``` Bash
docker exec -it --user root your-container-name /bin/bash
```

## work in devcontainer
push "Attach to Running Container..."  
and select "your-container-name"
