# Python---01
本项目为Python程序设计课程的小项目01作业
本项目中包括原有实验要求代码和已完成补全的image_encoder.py以及完成的实验一实验报告
本项目中独立完成了代码补全的工作和实验报告的撰写
参考了Chatgpt对于一些报错问题的指正和对实验内容的大致理解的帮助
同时将我的实验文件夹上传至Github出现了文件大小大于25MB无法上传的问题
该问题由Chatgpt协助解决
实验报告：https://www.overleaf.com/project/6ad96c3616325edf2b8ec214/share#a518205cae3002b844f35d64a18fed47c119697323da0d5b

## 项目文件

- 图像编码器包含图像分块、输入嵌入、多头注意力、Transformer 编码块和最终投影。 [image_encoder.py](project1-numpy-student/image_encoder.py)
- 依赖包括 NumPy、Pillow 和课堂示例使用的 imageio。本次实验使用 Windows、Python 3.11.5、NumPy 2.4.6、Pillow 12.3.0 和 imageio 2.38.2。 [requirements.txt](project1-numpy-student/requirements.txt)
- 课程原始说明记录了模型接口、检查阶段和提交要求。 [课程 README](project1-numpy-student/README.md)

## 获取课程数据

从课程原始附件取出模型权重和参考数组，放到下表中的位置。配置和十张示例图片随仓库提供。

| 文件位置 | 用途 |
| --- | --- |
| `project1-numpy-student/weights/image_encoder.npz` | `run.py` 和 `check.py` 使用的模型权重 |
| `project1-numpy-student/assets/reference_outputs.npz` | `check.py` 的参考数组 |

## 安装、检查和运行

在仓库根目录打开 PowerShell 后执行以下命令。已有虚拟环境时，可以直接运行最后两条命令。

```powershell
cd project1-numpy-student
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe check.py --stage all
.\.venv\Scripts\python.exe run.py --output output_tokens.npz
```

`check.py` 逐阶段比较模型输出与参考数据。`run.py` 默认处理十张课程示例图像，保存图像 ID 和形状为 `(10, 512)` 的 `float32` 特征。仓库中的实验输出与课程参考值的最大绝对误差约为 `5.439e-07`。 [output_tokens.npz](project1-numpy-student/output_tokens.npz)
