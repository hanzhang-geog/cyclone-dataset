# cyclone-dataset

# cyclone-dataset

## Project Overview

This dataset was developed as part of my undergraduate thesis, which received the highest distinction within my project group.  
It is constructed from infrared typhoon satellite images provided by the [Digital Typhoon Project](http://agora.ex.nii.ac.jp/digital-typhoon/), led by Prof. Asanobu Kitamoto at the National Institute of Informatics (NII), Japan.  
All images were manually annotated for cyclone detection using the YOLO deep learning framework.  
Benchmark experiments with YOLO models achieved mAP@0.5 scores of 70–80%.  
The dataset provides a high-quality resource and baseline results for typhoon object detection and remote sensing research or education.

---

## Data Source & Acknowledgments

All original imagery was obtained from the [Digital Typhoon Project](http://agora.ex.nii.ac.jp/digital-typhoon/), maintained by Prof. Asanobu Kitamoto and his team at NII, Japan.  
I gratefully acknowledge Prof. Kitamoto and his group for making high-quality satellite data publicly available, which enabled this research and dataset creation.

---

## Dataset Construction

- All images are infrared-band satellite images of typhoons.
- A Python script was used to download IR images for each typhoon from Digital Typhoon, with 8 uniformly sampled images selected per typhoon event.
- Manual annotation was conducted using [labelme](https://github.com/wkentaro/labelme), and JSON label files were batch-converted to YOLO TXT format.
- Annotations cover all major stages of the typhoon lifecycle (formation, intensification, mature, dissipation), with a single "cyclone" class.
- Baseline experiments with YOLO object detection models achieved mAP@0.5 between 70% and 80%.

---

## Dataset Structure

dataset/
├── train/
│ ├── images/ # Training images
│ └── labels/ # Training labels (YOLO TXT and _meta files)
├── val/
│ ├── images/ # Validation images
│ └── labels/ # Validation labels
├── test/
│ ├── images/ # Test images
│ └── labels/ # Test labels
├── data.yaml # YOLO training configuration
├── dataset.yaml # Additional config files
└── README.md # Project documentation

Each `labels` directory contains:
- YOLO TXT label files (each line: `class x_center y_center width height`, normalized coordinates)
- Optional `_meta` files with additional metadata per sample

---

## Usage Notes

- For improved detection performance, it is recommended to annotate additional cyclone lifecycle stages separately, or to select and label only well-defined cyclones in detail.
- This dataset is intended strictly for academic research and teaching. **Commercial use is strictly prohibited.**

---

## License & Disclaimer

- This dataset is distributed for non-commercial, academic, and educational use only.
- The copyright and ownership of the original satellite data belong to the [Digital Typhoon Project](http://agora.ex.nii.ac.jp/digital-typhoon/) and Prof. Asanobu Kitamoto’s group.
- The author of this repository claims no rights over the original images, and is responsible only for the secondary annotation and processing.
- For any copyright or legal inquiries, or requests for removal, please contact the maintainer at zhanghangeog@gmail.com.

---

## Recommended Citation

If you use this dataset in your research or publications, please cite the original data source as follows:

> Kitamoto, Asanobu. Digital Typhoon: Typhoon Images and Information. National Institute of Informatics. http://agora.ex.nii.ac.jp/digital-typhoon/ (Accessed 2025-07-25).

For citing this annotated dataset, please use:

> ZHANG, Han. Cyclone Infrared Image Dataset, based on Digital Typhoon data (Kitamoto et al.), 2025.

---

## Contact

For questions, collaboration, or any other inquiry, please contact:  
**zhanghangeog@gmail.com**






# cyclone-dataset

## 项目简介

本数据集由本人在本科毕业设计期间制作，课题获得小组最高分。  
研究基于日本国立信息学研究所北本朝信（Asanobu Kitamoto）老师团队的[数字台风（Digital Typhoon）](http://agora.ex.nii.ac.jp/digital-typhoon/)红外台风卫星影像，采用深度学习（YOLO 系列）方法进行气旋自动检测与标注。  
模型在本数据集上 mAP@0.5 达到 70–80%。数据集为台风目标检测、遥感影像处理等相关研究与教学提供了高质量样本和基线实验。

---

## 数据来源与致谢

本数据集基于**日本国立信息学研究所（National Institute of Informatics, NII）北本朝信（Asanobu Kitamoto）老师主导的“数字台风”项目**的原始公开数据制作。  
特别感谢北本朝信老师及其团队长期提供高质量的台风卫星影像数据，为本研究工作奠定了坚实基础。

---

## 数据集制作流程

- 影像均为红外波段卫星图像。
- 使用 Python 脚本自动下载数字台风中每个台风的红外卫星影像，每个台风均匀采样 8 张图像。
- 采用 [labelme](https://github.com/wkentaro/labelme) 工具进行人工标注，随后将 json 批量转换为 YOLO txt 格式。
- 标注覆盖台风生命周期各阶段（生成、发展、成熟、消亡），当前数据仅包含 "cyclone" 单类别标签。
- 通过 YOLO 系列目标检测模型测试，mAP@0.5 精度约为 70–80%。

---

## 数据结构

本数据集目录结构如下：


dataset/
├── train/
│ ├── images/ # 训练集影像
│ └── labels/ # 训练集标签（YOLO格式与 _meta 文件）
├── val/
│ ├── images/ # 验证集影像
│ └── labels/ # 验证集标签
├── test/
│ ├── images/ # 测试集影像
│ └── labels/ # 测试集标签
├── data.yaml # YOLO训练用配置文件
├── dataset.yaml # 其他辅助配置文件
└── README.md # 项目说明文档
---

- 每个 labels 文件夹下包含：
  - `xxxxxx_xxxxxxxxx`：YOLO 格式标签文件
  - `xxxxxx_xxxxxxxxx_meta`：标签元信息（可选）

---

## 使用建议

- 为进一步提升检测精度，建议对不同生命周期阶段的台风影像分阶段细致标注，或优选结构完整气旋影像深度标注。
- 建议在学术交流、科研项目及教学实践中使用，禁止任何商业用途。

---

## 版权声明与免责声明

- 本数据集仅供学术交流与学习参考，严禁任何商业用途。
- 数据版权归[数字台风项目](http://agora.ex.nii.ac.jp/digital-typhoon/)及北本朝信老师团队所有。如涉及原始数据的权属问题，请直接联系原数据发布方。
- 本数据集作者仅对二次整理和标注负责，对原始数据不主张任何版权。
- 如有侵权或不当之处，欢迎联系仓库维护者（zhanghangeog@gmail.com），我将在第一时间整改或下架。

---

## 推荐引用格式

如在论文或公开成果中使用本数据集，请注明原始数据来源，并参考如下引用格式：

> Kitamoto, Asanobu. Digital Typhoon: Typhoon Images and Information. National Institute of Informatics. http://agora.ex.nii.ac.jp/digital-typhoon/ (Accessed 2025-07-25).

如需引用本数据集的整理与标注，请补充作者和年份：

> ZHANG, Han. Cyclone Infrared Image Dataset, based on Digital Typhoon data (Kitamoto et al.), 2025.

---

## 联系方式

如需交流、合作或有任何问题，欢迎邮件联系：zhanghangeog@gmail.com
