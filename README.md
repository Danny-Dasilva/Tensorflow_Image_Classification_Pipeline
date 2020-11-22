# TensorFlow__Image classification Pipeline
tensorflow image classification training pipeline





build docker container

`sudo docker build ./ -t img_class`



export path 

`DETECT_DIR=$PWD`

run docker container


```
docker run -ti --name edgetpu-classify\
--rm -it --privileged -p 6006:6006 \
--mount type=bind,src=${DETECT_DIR},dst=/models/research/object_detection/images \
--gpus all \
img_class
```




tensorboard

`sudo docker exec -it edgetpu-classify /bin/bash`

`tensorboard --logdir=training`

Usefull scripts


clear docker memory

`docker system prune -a`
