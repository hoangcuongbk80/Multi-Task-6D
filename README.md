
## Installation

Install [Pytorch](https://pytorch.org/get-started/locally/). You'll need to have access to GPUs. The code is tested with Ubuntu 18.04, Pytorch v1.1, CUDA 10.0, and cuDNN v7.4.

Install the following Python dependencies (with `pip install`):

    matplotlib
    opencv-python
    plyfile
    'trimesh>=2.35.39,<2.35.40'
    'networkx>=2.2,<2.3'


#### Train

To train a new model:

    CUDA_VISIBLE_DEVICES=0 python train.py --dataset dataset --log_dir log

You can use `CUDA_VISIBLE_DEVICES=0,1,2` to specify which GPU(s) to use. Without specifying CUDA devices, the training will use all the available GPUs and train with data parallel (Note that due to I/O load, training speedup is not linear to the number of GPUs used). Run `python train.py -h` to see more training options.
While training you can check the `log/log_train.txt` file on its progress.

#### Run predict

    python predict.py

## License
Licensed under the [MIT License](LICENSE)
