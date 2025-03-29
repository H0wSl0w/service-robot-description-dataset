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
    "name": "豹小秘2",
    "manufacturer": "猎户星空",
    "description": "猎户星空推出的豹小秘2是一款高性能AI语音交互服务机器人..."
  },
  "parameters": {
    "整机尺寸": {
      "value": {
        "length": 558,
        "width": 525,
        "height": 1350
      },
      "unit": "mm"
    },
    // 其他参数...
  },
  "functions": {
    "interaction": [
      "智能咨询",
      "迎宾接待",
      "问路引领"
    ],
    // 其他功能...
  },
  "scenes": [
    "政务讲解员",
    "企业讲解员"
    // 其他场景...
  ]
}
{
  "basic_info": {
    "name": "数字扬声器模块",
    "manufacturer": "Unknown",
    "description": "数字扬声器模块，适用于2.0-5.5V电压范围..."
  },
  "parameters": {
    "工作电压": {
      "value": {
        "min": 2.0,
        "max": 5.5
      },
      "unit": "V"
    },
    // 其他参数...
  },
  "functions": {
    "execution": [
      "可用作蜂鸣器",
      "播放高质量音频"
    ]
  }
}
```

## Usage Examples

This dataset can be used for various research purposes including:

1. Training language models to understand robotic specifications
2. Analyzing trends in service robot capabilities
3. Developing recommendation systems for robot selection
4. Generating descriptions for new robotic systems
5. Studying the relationship between robot features and application domains

### Loading the dataset in Python:

```python
import json

# Load the entire dataset
with open('service_robot_dataset.json', 'r', encoding='utf-8') as f:
    robot_data = json.load(f)

# Example: Filter robots by manufacturer
def filter_by_manufacturer(data, manufacturer):
    return [item for item in data if item['basic_info']['manufacturer'].lower() == manufacturer.lower()]

# Example: Analyze robots by function
def get_robots_with_function(data, function_type, function_name):
    return [item for item in data if function_name in item['functions'].get(function_type, [])]
```

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
