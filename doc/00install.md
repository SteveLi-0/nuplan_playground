# 00 install nuplan
- github: https://github.com/motional/nuplan-devkit
- download dataset and map: https://www.nuscenes.org/nuplan#download
- doc: https://nuplan-devkit.readthedocs.io/en/latest/
  

### 下载开发工具包 (devkit)

运行以下命令将 devkit 下载到你的主目录：

```bash
cd && git clone https://github.com/motional/nuplan-devkit.git && cd nuplan-devkit
```

以上命令会将文件下载到你的主目录。虽然可以更改为任意目录，但后续的教程假设你使用的是主目录。

### 安装 Python

该开发工具包在 Ubuntu 上测试通过的 Python 版本为 3.9。

对于 Ubuntu，如果系统上未安装正确的 Python 版本，请运行以下命令进行安装：

```bash
sudo apt install python-pip
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
sudo apt-get install python3.9
sudo apt-get install python3.9-dev
```

### 创建 Conda 环境

通过 `environment.yml` 文件创建一个新的 Conda 环境：

```bash
conda env create -f environment.yml
```

### 安装开发工具包

#### 本地安装 PIP 包

我们推荐将本地 devkit 作为 PIP 包安装：

```bash
pip install -e .
```

这将安装 devkit 及其所有依赖项。注意，可选的 `-e` 模式意味着代码将被原地使用，而不会被复制到其他位置，方便开发时进行修改。

### 更改默认目录

如 `README` 中所述，nuPlan 的默认目录为：

- `~/nuplan/dataset` - 数据集文件夹。可以是只读。
- `~/nuplan/exp` - 实验和缓存文件夹。必须有读写权限。

如果你想在系统中更改这些目录，需要在 `~/.bashrc` 中设置相应的环境变量，例如：

```bash
export NUPLAN_DATA_ROOT="$HOME/nuplan/dataset"
export NUPLAN_MAPS_ROOT="$HOME/nuplan/dataset/maps"
export NUPLAN_EXP_ROOT="$HOME/nuplan/exp"
```

