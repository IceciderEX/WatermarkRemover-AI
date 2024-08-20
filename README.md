# WatermarkRemover-AI

**AI-Powered Watermark Remover using Florence-2 and LaMA Models**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python: 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/downloads/)

## Overview

`WatermarkRemover-AI` is a Python-based application that utilizes state-of-the-art AI models—Florence-2 from Microsoft for detecting watermarks and LaMA (Large Masked Autoregressive) for inpainting—to effectively remove watermarks from images. The application provides a user-friendly interface built with PyQt6, allowing for easy batch processing and previewing of original, cleaned, and difference images.

## Table of Contents

- [Features](#features)
- [Technical Overview](#technical-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Batch Image Processing**: Select a directory of images and process them all at once.
- **Advanced Watermark Detection**: Utilizes Florence-2's open vocabulary detection to identify watermark regions accurately.
- **High-Quality Inpainting**: Employs the LaMA model for seamless inpainting, ensuring high-quality results.
- **Preview Capabilities**: View original, cleaned, and difference images side-by-side for comparison.
- **Customizable Settings**: Configure maximum image size, overwrite behavior, and other parameters.

## Technical Overview

### 1. **Florence-2 Model for Watermark Detection**
   - Florence-2, a model from Microsoft, is used for detecting watermarks in images. It leverages open vocabulary detection to identify regions that may contain watermarks.
   - Detected regions are filtered to ensure that only areas covering less than 10% of the image are processed, avoiding false positives.

### 2. **LaMA Model for Inpainting**
   - The LaMA (Large Masked Autoregressive) model is employed for inpainting the detected watermark regions. It provides high-quality, context-aware inpainting, making the watermark removal seamless.
   - The application uses different strategies (resize, crop) to handle images of various sizes, ensuring the best possible results.

### 3. **PyQt6-Based GUI**
   - The application features a PyQt6-based graphical user interface (GUI) that is intuitive and user-friendly. It allows users to select input/output directories, configure settings, and view the results in real-time.

## Installation

### Prerequisites

- Python 3.8+
- CUDA (optional, for GPU acceleration)

### Steps

1. **Clone the Repository:**

   ```
   git clone https://github.com/yourusername/WatermarkRemover-AI.git
   cd WatermarkRemover-AI```

2. **Install Dependencies:** 
   ```pip install -r requirements.txt```

3. Run the Application:
   ```python remwm.py```

## Usage

### 1. **Selecting Directories**
   - Use the "Select Input Directory" button to choose the directory containing the images you want to process.
   - Use the "Select Output Directory" button to choose where the processed images will be saved.

### 2. **Configuring Settings**
   - **Max Width/Height**: Set the maximum size for image processing. Images larger than this will be resized while maintaining aspect ratio.
   - **If Exists**: Choose whether to skip or overwrite existing processed images.

### 3. **Processing Images**
   - Click "Start Batch Processing" to begin processing all images in the input directory.
   - The progress bar will update as images are processed, and the GUI will display the original, cleaned, and difference images.

### 4. **Viewing Results**
   - The GUI shows the original, cleaned, and difference images side-by-side for easy comparison.

## Configuration

The application automatically saves and loads settings from a configuration file (`remwmconfig.ini`). This includes input/output directories, maximum image size, and overwrite behavior. The configuration file is updated whenever the "Start Batch Processing" button is clicked.

## Contributing

Contributions are welcome! If you'd like to contribute, please fork this repository, create a feature branch, and submit a pull request.

### Steps:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m 'Add your feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
   