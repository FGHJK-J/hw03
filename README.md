# 人脸识别系统

## 项目概述

本项目使用 `face_recognition` 库（基于 dlib）实现人脸检测与特征提取，并通过 Streamlit 搭建交互式 Web 界面，完成「上传图片 → 检测/识别人脸 → 展示结果」的完整流程。

## 功能特性

- **人脸检测**：自动检测图片中的人脸位置
- **特征提取**：生成 128 维人脸特征编码
- **人脸识别**：与已知人脸库进行对比识别
- **可视化展示**：在图片上标注人脸位置和识别结果
- **交互式界面**：支持上传图片，实时显示检测结果

## 安装步骤

### 1. 克隆项目

```bash
git clone <repository_url>
cd hw03/face/face_app
```

### 2. 安装依赖

```bash
pip install -r requirements.txt
```

**注意**：`face_recognition` 依赖于 dlib 库，安装过程可能需要编译 C++ 代码。对于 Windows 用户，可能需要先安装 Visual Studio Build Tools 或 MinGW。

## 使用说明

### 1. 运行应用

```bash
streamlit run app.py
```

### 2. 访问界面

浏览器会自动打开 `http://localhost:8501`，进入人脸识别系统界面。

### 3. 上传图片

点击「上传图片」按钮，选择要识别的图片（支持 jpg、png、jpeg 格式）。

### 4. 查看结果

系统会自动检测图片中的人脸，提取特征，并与已知人脸库进行对比，最后在图片上标注人脸位置和识别结果。

## 项目结构

```
face_app/
├── src/                  # 核心功能模块
│   ├── face_utils.py     # 人脸检测和编码工具
│   └── recognize.py      # 人脸识别功能
├── data/                 # 数据目录
│   └── known_faces/      # 已知人脸库
│       └── image.png     # 示例已知人脸
├── app.py                # Streamlit 应用主文件
└── requirements.txt      # 项目依赖
```

## 已知人脸库

在 `data/known_faces/` 目录中添加已知人脸图片，系统会自动加载并用于识别。图片文件名建议使用人物名称，以便在识别结果中显示。

## 技术栈

- **Python 3.6+**
- **face_recognition**：人脸检测和特征提取
- **OpenCV**：图像处理
- **Streamlit**：Web 界面
- **NumPy**：数值计算

## 注意事项

1. 首次运行时，系统会加载已知人脸库，可能需要一些时间
2. 识别精度取决于已知人脸库的质量和数量
3. 对于多人脸图片，系统会检测并识别每个人脸
4. 推荐使用正面、清晰的人脸图片以获得最佳识别效果
