# 部署指南进度

## 当前状态
- **已完成第 1 步：** [GETTING_STARTED.md](doc/GETTING_STARTED.md)
- **已完成第 2 步：** [SKELETON_DATA.md](doc/SKELETON_DATA.md)
- **已完成第 3 步：** [START_RECOGNITION.md](doc/START_RECOGNITION.md)
- **正在进行第 4 步：** [CUSTOM_DATASET.md](doc/CUSTOM_DATASET.md)

## 任务详情
- 解压数据集的进程号：`62203`
- 预处理数据的进程号：`25738`
- 解压处理好的数据集的进程号：`26798`

## 已执行的命令
```zsh
  python deprecated/tools/data_processing/kinetics_gendata.py --data_path "/mnt/pami26/zengyi/dataset/kinetics-skeleton" 
  # 这个命令将 json 数据转换为 npy（数据）和 pkl（标签）

  mmskl configs/recognition/st_gcn_aaai18/kinetics-skeleton/train.yaml --gpus 8
  # 训练命令

  mmskl configs/recognition/st_gcn_aaai18/kinetics-skeleton/test.yaml --checkpoint ./work_dir/recognition/ST_GCN_18/kinetics-skeleton/epoch_400.pth

  mmskl configs/recognition/st_gcn_aaai18/kinetics-skeleton/test.yaml --checkpoint ./checkpoints/st_gcn.kinetics-6fa43f73.pth
  # 测试命令
```


## 将要执行的命令
```zsh
  mmskl configs/utils/build_dataset_example.yaml --gpus 4
```

## 遇到的问题
- **ImportError:** `mmskeleton.utils.third_party` 尝试使用需要模块 `mmdet.apis` 的功能，但无法加载。请安装 `mmdet` 并重试。

## 训练调整
- 训练的 epoch 可能太多，需要调整。

## 如何修改模型

## 其他常见问题
- **ImportError:** `mmskeleton.utils.third_party` 尝试使用需要模块 `pycocotools.COCO` 的功能，但无法加载。请安装 `pycocotools` 并重试。
- 若遇到此问题，请重新安装 `mmcv==0.4.0`。

- **ImportError:** mmskeleton.utils.third_party attempted to use a functionality that requires module mmdet.apis, but it couldn't be loaded. Please install mmdet and retry.


## 参考链接
- [AS-GCN GitHub 仓库](https://github.com/limaosen0/AS-GCN/tree/master)

## 版本对应
- `torch==1.2.0`
- `torchvision==0.4.0`
- `setuptools==60.2.0`