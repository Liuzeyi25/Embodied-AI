### clone代码仓库
git clone https://github.com/RLinf/RLinf.git

### UV自定义环境
1. 安装OpenVLA-OFT+ManiSkill LIBERO
cd RLinf
bash requirements/install.sh embodied --model openvla --env maniskill_libero
2. 激活环境
source .venv/bin/activate
3. 安装RLinf
pip install -e .
4. 拉取OpenVLA-OFT仓库
git clone https://github.com/moojink/openvla-oft.git
5. 进入OpenVLA-OFT路径并安装
cd openvla-oft
pip install -e .

### Libero数据集下载
1. 退回RLinf目录,拉取Libero
cd ..
git clone https://github.com/Lifelong-Robot-Learning/LIBERO.git
2. 安装libero
cd LIBERO
pip install -e .
3. 下载libero数据集, 以libero-10为例(https://lifelong-robot-learning.github.io/LIBERO/html/algo_data/datasets.html)
python benchmark_scripts/download_libero_datasets.py --datasets libero_100

### 设置Libero数据路径映射
1. 创建.libero目录
mkdir -p ~/.libero

2. 创建config.yaml文件
vim ~/.libero/config.yaml
3. 写入路径映射
benchmark_root: /path/to/LIBERO/libero/libero
datasets: /path/to/libero_10
init_states: /path/to/LIBERO/libero/libero/bddl_files
bddl_files: /path/to/LIBERO/libero/libero/bddl_files

### 下载OpenVLA-OFT与训练模型
hf download RLinf/Openvla-oft-SFT-libero10-trajall --local-dir /path/to/model/Openvla-oft-SFT-libero10-trajall/

### 修改配置文件
1. 配置文件路径
修改 /RLinf/examples/embodiment/config/libero_10_grpo_openvlaoft.yaml中:
1) rollout.model.model_path: "/path/to/model/Openvla-oft-SFT-libero10-trajall"
2) actor.model.model_path: "/path/to/model/Openvla-oft-SFT-libero10-trajall"

2. 运行脚本
bash examples/embodiment/run_embodiment.sh libero_10_grpo_openvlaoft


