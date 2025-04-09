# Image Registration

This project implements an image registration system that aligns a source image to a target image using affine transformations. It uses SIFT (Scale-Invariant Feature Transform) for feature extraction, RANSAC (Random Sample Consensus) for robust estimation, and OpenCV for image processing.

## Features

- **Affine Transformation**: Computes the affine transformation matrix to align images.
- **RANSAC**: Handles outliers in the feature matching process.
- **SIFT**: Extracts key points and descriptors for feature matching.
- **Image Warping**: Warps the source image to align with the target image.

## Project Structure

```
ImageRegistration/
├── affine_ransac.py       # Implements RANSAC for robust affine transformation estimation
├── affine_transform.py    # Handles affine transformation calculations
├── align_transform.py     # Aligns images using SIFT, RANSAC, and affine transformations
├── image_registration.py  # Main script to test and demonstrate the functionality
├── Images/                # Contains source and target images for testing
│   ├── mona_source.png
│   ├── mona_target.jpg
├── README.md              # Project documentation
└── __pycache__/           # Compiled Python files (auto-generated)
```

## Requirements

- Python 3.8+
- OpenCV
- NumPy

Install the required libraries using pip:

```bash
pip install opencv-python-headless numpy
```

## Usage

1. Clone the repository:

```bash
git clone https://github.com/your-username/ImageRegistration.git
```

2. Run the main script:

```bash
python image_registration.py
```

This will:
- Test the affine transformation and RANSAC implementation.
- Align the `mona_source.png` image to `mona_target.jpg` and display the result.

## How It Works

1. **Affine Transformation**:
   - The affine transformation is represented as:
     ```
     |x'|  = |a, b| * |x|  +  |tx|
     |y'|    |c, d|   |y|     |ty|
     ```
   - The `affine_transform.py` module provides methods to generate test cases and estimate the affine transformation matrix.

2. **RANSAC**:
   - The `affine_ransac.py` module uses RANSAC to handle outliers in the feature matching process.

3. **Image Alignment**:
   - The `align_transform.py` module extracts SIFT features, matches them, applies RANSAC, and computes the affine transformation matrix to warp the source image.

## Example Output

The aligned image is displayed as a blend of the source and target images.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

- OpenCV for image processing.
- NumPy for numerical computations.
