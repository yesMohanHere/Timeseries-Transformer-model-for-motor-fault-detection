# Vibration Data Analysis and Fault Detection Using Transformers

## Project Description
This repository provides a framework for analyzing vibration data from machinery to detect and classify operational conditions. By leveraging transformers and machine learning models, it processes raw vibration data to identify and predict faults, supporting predictive maintenance initiatives.

### Dataset
This project uses the Case Western Reserve University (CWRU) Bearing Dataset, a widely used benchmark dataset for machinery fault diagnosis. The dataset includes vibration signals collected under various operating conditions and fault scenarios, providing a robust foundation for model development and testing.

You can download the CWRU dataset from the [official website](https://engineering.case.edu/bearingdatacenter). Ensure that the data files are placed in the directory specified in the code (`data_dir`).
This repository provides a framework for analyzing vibration data from machinery to detect and classify operational conditions. By leveraging transformers and machine learning models, it processes raw vibration data to identify and predict faults, supporting predictive maintenance initiatives.

## Features
- **Data Preprocessing**: Reads and processes raw vibration data files.
- **Label Assignment**: Automatically assigns labels based on file naming conventions (e.g., "normal" or fault-specific labels).
- **Segmentation**: Divides vibration data into manageable segments for training and testing.
- **Transformer-Based Models**: Incorporates transformer architectures for advanced pattern recognition and classification.
- **Configurable**: Adjustable parameters for segmentation length, test/train split, and random state.

## Installation
To use this project, clone the repository and install the necessary Python libraries:

```bash
git clone https://github.com/yourusername/vibration-fault-detection-transformers.git
cd vibration-fault-detection-transformers
pip install -r requirements.txt
```

## Usage
1. **Prepare Your Data**:
   - Place your vibration data files in the directory specified in the code (`data_dir`).
   - Ensure the files are named according to the conventions used for label assignment (e.g., containing keywords like "normal").

2. **Run the Code**:
   - Open and run the Jupyter Notebook `transformer_code.ipynb`.
   - Adjust parameters (e.g., `segment_length`, `test_size`, and `val_size`) as needed.

3. **Analyze Results**:
   - Evaluate the performance of the transformer-based models on your dataset.

## File Structure
```
.
├── transformer_code.ipynb   # Main code file
├── requirements.txt         # Dependencies for the project
└── README.md                # Project documentation
```

## Dependencies
- Python 3.7+
- numpy
- scipy
- scikit-learn
- transformers

Install all dependencies using:

```bash
pip install -r requirements.txt
```

## Contributing
Contributions are welcome! If you have ideas to enhance the project or find any issues, please submit a pull request or open an issue.


## Acknowledgments
- Inspired by the need for robust predictive maintenance solutions in industrial settings.

---

### Example Use Case

The following example demonstrates how to assign labels and segment vibration data:

```python
from sklearn.model_selection import train_test_split

def get_label_from_filename(fname):
    fname = fname.lower()
    if "normal" in fname:
        return 0
    elif "fault" in fname:
        return 1

# Split data into training and testing sets
data_train, data_test = train_test_split(data, test_size=0.2, random_state=42)
```

