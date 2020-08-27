# An introduction for using docker images as pytorch script runtimes
This **Image/Dockerfile** aims to create a container for pytorch runtimes.
You can pull the pre-build docker image from [leftice/airdialogue-187](https://hub.docker.com/r/leftice/airdialogue-187)

## How to use?
* You should git clone this repository first.
* And then cd into the folder, type as follows according to your cuda version and torch version.
```
sudo docker build --no-cache -f Dockerfile.airdialogue-187 -t leftice/airdialogue-187 .
```
* For your pytorch scripts, you can use as the hereunder part.
If you ran your previous python code as 
```
python3 a.py
```
* Now you should run as :
```
sudo docker run --runtime=nvidia --rm -it -v "$PWD":/home/workspace -w /home/workspace leftice/airdialogue-187 python3 a.py
# for Docker >= 19.03
# sudo docker run --gpus 2 --rm -it -v "$PWD":/home/workspace -w /home/workspace leftice/airdialogue-187 python3 a.py
```

