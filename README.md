# ML Pipeline with DVC and AWS S3

## Overview
This project provides an end-to-end understanding of building a Machine Learning (ML) pipeline while leveraging DVC (Data Version Control) for experiment tracking and data versioning using AWS S3. The pipeline enables efficient data management, reproducibility, and streamlined experimentation.

## Features
- End-to-end ML pipeline setup
- Data versioning and management using DVC
- Experiment tracking with DVC
- Integration with AWS S3 for data storage
- Reproducibility and efficient workflow management

## Technologies Used
- **Python**
- **DVC (Data Version Control)**
- **AWS S3**
- **Scikit-learn/PyTorch/TensorFlow (depending on the ML model used)**
- **Jupyter Notebook/VS Code for development**

## Prerequisites
Ensure you have the following installed:
- Python (>=3.8)
- Git
- DVC
- AWS CLI (configured with necessary permissions)
- Virtual environment (optional but recommended)

## Installation and Setup
1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd <project-directory>
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Initialize DVC:**
   ```bash
   dvc init
   ```

5. **Configure AWS S3 as the remote storage:**
   ```bash
   dvc remote add -d s3remote s3://your-bucket-name/path
   dvc remote modify s3remote endpointurl https://s3.amazonaws.com
   ```

6. **Pull the latest data version from S3:**
   ```bash
   dvc pull
   ```

## Usage
### Data Versioning
- **Add data to DVC:**
  ```bash
  dvc add data/
  ```
- **Push data to AWS S3:**
  ```bash
  dvc push
  ```
- **Track data changes:**
  ```bash
  dvc status
  ```

### Experiment Tracking
- **Run an experiment:**
  ```bash
  dvc exp run
  ```
- **Compare experiments:**
  ```bash
  dvc exp show
  ```
- **Checkpoint and reproduce results:**
  ```bash
  dvc repro
  ```

## Best Practices
- Commit `dvc.lock` and `.dvc` files to Git for reproducibility.
- Use `dvc metrics` to track model performance across experiments.
- Automate workflows using CI/CD for model training and deployment.

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests.

## License
This project is licensed under the MIT License.

## Contact
For any queries, reach out to Vikas-Rathod1 at vikasrathodml@gmail.com.
