# Derenzo Phantom Volume Generator

This project provides tools for generating volumes with a Derenzo phantom inside, specified by Euler Angles and Translation (pose). It is designed to be compatible with the Pytomography software package from the University of British Columbia and diffDRR from the MIT CSAIL group.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Tutorials](#tutorials)
- [Acknowledgements](#acknowledgements)
- [License](#license)

## Introduction
This package allows you to generate a 3D volume with a Derenzo phantom inside and manipulate its pose using specified Euler angles and translations. The generated volumes can be used in conjunction with Pytomography and diffDRR for advanced imaging studies.

## Features
- Generate Derenzo phantom volumes.
- Specify pose using Euler angles and translation.
- Interoperable with Pytomography and diffDRR.
- Tutorial scripts in Jupyter notebooks.

## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/PicoRad-Imaging/derenzo_phantom.git
    ```
2. Navigate to the project directory:
    ```bash
    cd derenzo_phantom
    ```
3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```
4. Install the package:
    ```bash
    python setup.py install
    ```

## Usage
To generate a Derenzo phantom volume with a specified pose:
```python
from derenzo_phantom.phantom.phantom_generator import generate_phantom
from derenzo_phantom.phantom.pose_handler import set_pose
from derenzo_phantom.utils.visualization import visualize_volume

# Generate phantom
phantom_volume = generate_phantom()

# Set pose
pose = {'euler_angles': (0, 0, 0), 'translation': (0, 0, 0)}
transformed_volume = set_pose(phantom_volume, pose)

# Visualize
visualize_volume(transformed_volume)
```

## Tutorials
Jupyter notebooks with detailed tutorials are available in the `notebooks/tutorials` directory:
- [Translation Tutorial](notebooks/tutorials/translation_tutorial.ipynb)
- [Rotation Tutorial](notebooks/tutorials/rotation_tutorial.ipynb)
- [Hyperparameter Tuning Tutorial](notebooks/tutorials/hyperparameter_tutorial.ipynb)

## Acknowledgements
This project is based on the work of [Ross Barnowski](https://github.com/rossbar/derenzo_phantom). We have reforked from his repository to build upon his excellent foundation and ensure no additional dependencies are required.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
