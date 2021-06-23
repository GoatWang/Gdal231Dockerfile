1. Introduction
    - OS: Ubuntu 16.04
    - Python: 3.6
    - GDAL: 2.3.1

2. Building Scripts
```
sudo docker build -t gdal/python36:2.3.1 . 
```

3. Run
```
sudo docker run -it gdal/python36:2.3.1 /bin/bash
```