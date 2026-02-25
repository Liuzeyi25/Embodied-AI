# RLinf 项目部署说明

---

## 1. 核心仓库克隆与环境初始化
首先，通过 Git 克隆主仓库，并利用 `uv` 提供的安装脚本一键配置 **OpenVLA-OFT** 与 **ManiSkill LIBERO** 的自定义环境。

```bash
git clone https://github.com/RLinf/RLinf.git
cd RLinf

bash requirements/install.sh embodied --model openvla-oft --env maniskill_libero
```

---

## 2. 激活环境与组件安装
环境准备就绪后，需激活虚拟环境并以可编辑模式（editable mode）安装 RLinf 核心包及其依赖项 OpenVLA-OFT。

```bash
source .venv/bin/activate
pip install -e .

git clone https://github.com/moojink/openvla-oft.git
pip install -e .
cd ..
```

---

## 3. LIBERO 数据集配置
退回主目录后，继续配置 LIBERO 仿真环境并下载所需的数据集（此处以 `libero_100` 为例）。

```bash
git clone https://github.com/Lifelong-Robot-Learning/LIBERO.git
pip install -e .

python benchmark_scripts/download_libero_datasets.py --datasets libero_100
cd ..
```

---

## 4. 建立 Libero 路径映射
为了确保系统能够正确索引数据集与资源，需要手动建立配置文件。请在用户目录下创建 `.libero` 文件夹并编辑 `config.yaml`。

> **注意**：请根据您的实际存储位置替换下方的 `/path/to/` 绝对路径。

```bash
mkdir -p ~/.libero
```

**配置文件内容示例 (`~/.libero/config.yaml`):**
```yaml
benchmark_root: /path/to/LIBERO/libero/libero
datasets: /path/to/libero_10
init_states: /path/to/LIBERO/libero/libero/bddl_files
bddl_files: /path/to/LIBERO/libero/libero/bddl_files
```

---

## 5. 模型权重获取
从 Hugging Face 下载预训练的 OpenVLA-OFT 模型权重至本地指定目录。

```bash
hf download RLinf/Openvla-oft-SFT-libero10-trajall --local-dir /path/to/model/Openvla-oft-SFT-libero10-trajall/
```

---

## 6. 配置文件调整
在运行实验前，需手动更新 RLinf 的 YAML 配置文件，确保 `rollout` 和 `actor` 模块指向正确的模型路径。

**目标文件位置:** `RLinf/examples/embodiment/config/libero_10_grpo_openvlaoft.yaml`

| 待修改参数 | 建议设置值 |
| :--- | :--- |
| **rollout.model.model_path** | "/path/to/model/Openvla-oft-SFT-libero10-trajall" |
| **actor.model.model_path** | "/path/to/model/Openvla-oft-SFT-libero10-trajall" |

---

## 7. 启动运行脚本
一切配置完成后，执行以下命令开始运行任务。

```bash
bash examples/embodiment/run_embodiment.sh libero_10_grpo_openvlaoft
```
