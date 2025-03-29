# Service Robot Description Dataset

A comprehensive dataset containing 2051 service robot descriptions and specifications collected from 30+ manufacturers and RobotShop platform, including both real product data and generated supplements.

## Dataset Overview

This dataset contains textual descriptions and technical specifications of service robots and their modules, intended for research in natural language processing, robotics, and machine learning.

### Data Sources
- **Real Product Data (697 entries)**:
  - **Service Robot Products (239 entries)**: Complete robot systems from 30+ manufacturers including Ecovacs, Roborock, PuduTech, Keenon, UBTECH, and others
  - **Service Robot Modules (458 entries)**: Component modules from RobotShop platform that can be integrated into service robots
  
- **Generated Supplement Data (1,393 entries)**:
  - Generated using GLM-4-Plus API to enrich data diversity and parameter variations

### Data Processing
1. Web scraping from official manufacturer websites and RobotShop
2. Data cleaning to remove noise (advertisements, redundant information)
3. Standardization into JSON format
4. Parameter extraction and structured organization
5. Supplementation with generated data to enhance diversity

## Example Entries

### Service Robot Product Example
```json
{
  "basic_info": {
    "name": "云帆智能交互机器人-AI讲解员",
    "manufacturer": "云迹科技",
    "description": "云帆智能交互机器人-AI讲解员，由云迹科技精心打造，是一款集"看、听、说、走"于一体的智能机器人。其身高1465mm，直径560mm，重85kg。装备800万像素前后双摄像头，续航长达8-9小时，充电仅需6小时，支持4G/wifi2.4G/蓝牙4.0通讯。具备多感知系统、自动回充、全时交互、双屏交互等功能，适用于展厅展馆、服务大厅、银行、4S店、售楼处、商场、奢侈品专卖店等多种场景，提供自动化服务、智能物联等便捷功能。"
  },
  "parameters": {
    "外形高度": {
      "value": 1465,
      "unit": "mm"
    },
    "外形直径": {
      "value": 560,
      "unit": "mm"
    },
    "重量": {
      "value": 85,
      "unit": "kg"
    },
    "前后双摄像头像素": "800万防逆光摄像头",
    "最大爬坡角度": {
      "value": 8,
      "unit": "度"
    },
    "正常速度": {
      "value": {
        "min": 0.5,
        "max": 0.8
      },
      "unit": "m/s"
    },
    "充电/续航时间": {
      "value": {
        "charge": 6,
        "run": {
          "min": 8,
          "max": 9
        }
      },
      "unit": "h"
    }
  },
  "functions": {
    "perception": [
      "多感知系统"
    ],
    "execution": [
      "可执行动作",
      "自动回充"
    ],
    "interaction": [
      "全时交互",
      "双屏交互",
      "问答库支持自定义"
    ],
    "navigation": [
      "依托自主研发底盘技术",
      "多场景应用"
    ]
  },
  "scenes": [
    "展厅展馆",
    "服务大厅",
    "银行",
    "4S店",
    "售楼处",
    "商场"
  ],
  "file_id": "product_0001"
}
```
### Service Robot Module Example
```json
{
  "basic_info": {
    "name": "Mecabot X Nano 自主移动机器人（AMR）平台",
    "manufacturer": "Unknown",
    "description": "Mecabot X Nano，一款专为室内服务设计的自主移动机器人（AMR）平台，由知名制造商打造。该平台搭载ROS控制器Jetson Nano，并配备Orbbec深度相机和Leishen激光雷达，确保精准感知。采用152mm直径的万向节麦卡诺轮，100W伺服功率，电池续航达3.5小时（无负载），最大负载60kg。具备感知、执行、交互和导航功能，适用于工厂、仓库、医院等室内环境，并支持快速原型设计和产品开发，可直接发货至目标市场。"
  },
  "parameters": {
    "ROS控制器": "Jetson Nano",
    "深度相机": "Orbbec",
    "激光雷达": "Leishen",
    "万向节麦卡诺轮直径": {
      "value": 152,
      "unit": "mm"
    },
    "伺服功率": {
      "value": 100,
      "unit": "W"
    },
    "电池寿命": {
      "value": {
        "no_load": 3.5,
        "unit": "小时",
        "load_3kg": 2.8
      }
    },
    "最大负载": {
      "value": 60,
      "unit": "kg"
    }
  },
  "functions": {
    "perception": [
      "内置激光雷达",
      "内置深度相机"
    ],
    "execution": [
      "STM32电机/电源/IMU",
      "金属底盘，配备4个麦卡诺轮和独立悬挂系统"
    ],
    "interaction": [
      "可添加机器人臂、语音识别模块、LCD屏幕和外部键盘"
    ],
    "navigation": [
      "灵活导航于较小的室内环境",
      "万向节轮允许在任意方向移动"
    ]
  },
  "scenes": [
    "工厂",
    "仓库",
    "医院",
    "公共交通",
    "办公楼",
    "酒店",
    "餐厅"
  ],
  "file_id": "module_0003"
}
```

## Usage Examples

This dataset can be used for various research purposes including:

1. Training language models to understand robotic specifications
2. Analyzing trends in service robot capabilities
3. Developing recommendation systems for robot selection
4. Generating descriptions for new robotic systems
5. Studying the relationship between robot features and application domains


## Citation

If you use this dataset in your research, please cite:

```
@dataset{service_robot_dataset,
  author = {Your Name},
  title = {Service Robot Description Dataset},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/H0wsl0w/service-robot-description-dataset}
}
```

## License

This dataset is released under [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

## Contact

For questions or feedback regarding this dataset, please open an issue in this repository or contact me at [your-email@example.com].
