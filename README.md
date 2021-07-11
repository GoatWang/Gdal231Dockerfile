1. Introduction
    - OS: Ubuntu 16.04
    - Python: 3.6
    - GDAL: 2.3.1/3.0.4

2. Building Scripts
```
sudo docker build -t jeremy4555/gdal:2.3.1 - < Dockerfile231
sudo docker build -t jeremy4555/gdal:3.0.4 - < Dockerfile304
```

3. Run
```
sudo docker run -it --rm jeremy4555/gdal:2.3.1 /bin/bash
sudo docker run -it --rm jeremy4555/gdal:3.0.4 /bin/bash
```
