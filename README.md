# Simple recipes for dockers

## Ubuntu on windows

Folder *ubuntu* 

Build:
```bash
docker build -t winub
```

Run:
```
docker run -it --rm -v //var/run/docker.sock:/var/run/docker.sock -v {project_folder}:/opt/proj ubunt bash
```