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

  mmskl configs/recognition/st_gcn_aaai18/kinetics-skeleton/train.yaml --gpus 8
  <!-- 训练命令 -->


- **将要执行的命令：**

  ```bash
  mmskl configs/recognition/st_gcn_aaai18/kinetics-skeleton/test.yaml --checkpoint ./work_dir/recognition/ST_GCN_18/kinetics-skeleton/epoch_50.pth


  mmskl configs/recognition/st_gcn_aaai18/kinetics-skeleton/test.yaml --checkpoint ./checkpoints/st_gcn.kinetics-6fa43f73.pth
  