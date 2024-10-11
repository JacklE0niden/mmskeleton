# 部署指南进度

- **当前状态：**
  - 已完成第 1 步：`GETTING_STARTED.md`
  - 正在进行第 2 步：`SKELETON_DATA.md`

- **任务详情：**
  - 解压数据集的进程号：`62203`
  - 预处理数据的进程号：`25738`
  - 解压处理好的数据集的进程号：`26798`
  
- **已经执行的命令：**

  ```bash
  python deprecated/tools/data_processing/kinetics_gendata.py --data_path "/mnt/pami26/zengyi/dataset/kinetics-skeleton" 
  <!-- 这个命令将json数据转换为npy(数据)和pkl(标签) -->

  mmskl configs/recognition/st_gcn_aaai18/kinetics-skeleton/train.yaml --gpus 8
  <!-- 训练命令 -->


- **将要执行的命令：**

  ```bash
  mmskl configs/recognition/st_gcn_aaai18/kinetics-skeleton/test.yaml --checkpoint ./work_dir/recognition/ST_GCN_18/kinetics-skeleton/epoch_50.pth


  mmskl configs/recognition/st_gcn_aaai18/kinetics-skeleton/test.yaml --checkpoint ./checkpoints/st_gcn.kinetics-6fa43f73.pth
  <!-- 测试命令 -->

训练的epoch可能太多了，需要调整一下

如何修改模型



ImportError: mmskeleton.utils.third_party attempted to use a functionality that requires module pycocotools.COCO, but it couldn't be loaded. Please install pycocotools and retry.
若遇到这个问题，重新安装一下mmcv==0.4.0