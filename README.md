# Docker Space for LSC CNN for Dense detection based Crowd Counting

## Usage
- Make sure docker and nvidia-docker installed.
- First need to pull the docker image:
`sudo docker pull nvcr.io/nvidia/pytorch:18.04-py3`

- Run the docker image with a shared folder from host and also a shared folder that points to the dataset on the host:
`sudo nvidia-docker run --rm -it --ipc=host --volume="/home/dh/Workspace/lsc_cnn_docker/lsc-cnn/:/workspace/lsc-cnn" --volume="/media/dh/Data/CrowdCounting:/workspace/dataset"  levan92/lsc-cnn:version2`

- To run jupyter notebook:
`sudo nvidia-docker run --rm -it --ipc=host -p 8888:8888 --volume="/home/dh/Workspace/lsc_cnn_docker/lsc-cnn/:/workspace/lsc-cnn" --volume="/media/dh/Data/CrowdCounting:/workspace/dataset"  levan92/lsc-cnn:version2`
    - Then, in the docker run:
`jupyter notebook --port=8888 --ip=0.0.0.0 --allow-root --no-browser`

- To run with GUI (for example cv2.imshow):
`sudo nvidia-docker run --rm -it --ipc=host --net=host --env="DISPLAY" --volume="$HOME/.Xauthority:/root/.Xauthority:rw" -p 8888:8888 --volume="/home/dh/Workspace/lsc_cnn_docker/lsc-cnn/:/workspace/lsc-cnn" --volume="/media/dh/Data/CrowdCounting:/workspace/dataset"  levan92/lsc-cnn:version2`

