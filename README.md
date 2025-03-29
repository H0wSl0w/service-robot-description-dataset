# Service Robot Description Dataset

A comprehensive dataset containing 2051 service robot descriptions and specifications collected from 30+ manufacturers and RobotShop platform, including both real product data and generated supplements.

## Dataset Overview

This dataset contains textual descriptions and technical specifications of service robots and their modules, intended for research in natural language processing, robotics, and machine learning.

### Data Sources
- **Real Product Data (697 entries)**:
  - 239 product descriptions from 30+ service robot manufacturers including Ecovacs, Roborock, PuduTech, Keenon, UBTECH, and others
  - 458 service robot module product descriptions from RobotShop platform using the search keyword "Service robot module"
  
- **Generated Supplement Data (1,393 entries)**:
  - Generated using GLM-4-Plus API to enrich data diversity and parameter variations

### Data Processing
1. Web scraping from official manufacturer websites and RobotShop
2. Data cleaning to remove noise (advertisements, redundant information)
3. Standardization into JSON format
4. Parameter extraction and structured organization
5. Supplementation with generated data to enhance diversity

## Data Structure

Each entry in the dataset is formatted as a JSON object with the following structure:

```json
{
  "basic_info": {
    "name": "Robot Name",
    "manufacturer": "Manufacturer Name",
    "description": "Detailed description of the robot"
  },
  "parameters": {
    "parameter1": "value1",
    "parameter2": {
      "value": 100,
      "unit": "kg"
    }
    // Other technical specifications
  },
  "functions": {
    "perception": ["sensor1", "sensor2"],
    "execution": ["function1", "function2"],
    "interaction": ["interaction1", "interaction2"],
    "navigation": ["navigation1", "navigation2"]
  },
  "scenes": ["scene1", "scene2"], // Application scenarios
  "identified_noise": [] // Flags for partial or noisy entries
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
