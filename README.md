## Project Overview

This repository contains a generative AI model trained to provide decision support for building retrofit versus demolition assessments, aligned with the UN Sustainable Development Goals (SDGs). The model analyzes building data and generates comprehensive recommendations based on sustainability criteria from four key SDGs:

- **SDG 9**: Industry, Innovation and Infrastructure
- **SDG 11**: Sustainable Cities and Communities
- **SDG 12**: Responsible Consumption and Production
- **SDG 13**: Climate Action

## Key Features

- **SDG-Aligned Decision Support**: Generate recommendations that balance multiple sustainability factors
- **Structured Assessment Framework**: Consistent evaluation across infrastructure, urban, resource, and climate dimensions
- **Detailed Rationales**: Comprehensive explanations for each recommendation
- **Performance Metrics**: Evaluation of decision accuracy and SDG coverage

## Repository Structure

```
sdg_retrofit_model/
├── notebooks/               # Jupyter notebooks for training and evaluation
│   └── SDG_Retrofit_Model.ipynb
├── src/                     # Source code
│   ├── data_processor.py    # Data preparation and processing
│   ├── model.py             # Model definition and training functions
│   ├── config.py            # Configuration parameters
│   ├── sdg_criteria.py      # SDG assessment criteria
│   └── evaluate.py          # Evaluation metrics and analysis
├── data/                    # Data files
│   ├── train_data.json
│   ├── val_data.json
│   └── test_data.json
├── docs/                    # Documentation
│   ├── sdg_alignment.md     # Discussion on SDG alignment
│   └── model_architecture.md # Technical details
└── results/                 # Results and visualizations
    ├── performance_metrics.md
    └── example_outputs.md
```

## Getting Started

### Prerequisites

```bash
pip install -r requirements.txt
```

### Training the Model

Run the Jupyter notebook `notebooks/SDG_Retrofit_Model.ipynb` or use the training script:

```bash
python src/train.py
```

### Generating Recommendations

```python
from src.model import SDGRetrofitModel

model = SDGRetrofitModel.load_from_checkpoint("models/best_model")

building_info = """
Building Type: Office Building
Year Built: 1978
Size: 15,000 sq ft
Current Condition: Structurally sound with outdated systems
Energy Performance: EPC rating of E
Historical Significance: None
Location: Urban center
Material Composition: Concrete frame with brick facade
Hazardous Materials: None detected
Adaptation Potential: High - open floor plan
"""

recommendation = model.generate_recommendation(building_info)
print(recommendation)
```

## Performance Evaluation

The model achieves:
- 82% accuracy in retrofit vs. demolition decisions
- 91% SDG coverage (mentions of all 4 SDGs in recommendations)
- Strong human evaluation ratings for usefulness and clarity
