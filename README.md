# Face Swap using Dlib and Python

## Overview
This project implements a **face-swapping** technique using **dlib** for facial landmark detection and **image warping** methods. It extracts facial landmarks, creates Delaunay triangulations, applies affine transformations, and seamlessly blends the swapped face onto a target image.

## Features
- Detects facial landmarks using **dlib's 68-point predictor**
- Generates **Delaunay triangulations** for face warping
- Warps and aligns the face using **affine transformations**
- Blends the swapped face seamlessly onto the target image
- Supports **multiple image formats** for source and destination

## Installation
### Prerequisites
Ensure you have Python installed (preferably Python 3.7+). Install the required dependencies using:

```bash
pip install opencv-python numpy dlib
```

### Download Pretrained Model
You need to download the **shape predictor model** for facial landmark detection:

```bash
wget http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2
bzip2 -d shape_predictor_68_face_landmarks.dat.bz2
```

Place this file in the working directory.

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/face-swap.git
   cd face-swap
   ```

2. Run the face swap script:
   ```bash
   python face_swap.py --source path/to/source.jpg --target path/to/target.jpg
   ```

3. The output will be displayed and saved as **swapped_image.jpg**.

## Code Explanation
- **extract_landmarks(image, detector, predictor):** Extracts 68 facial landmarks.
- **create_delaunay_triangles(rect, points):** Generates triangulation for facial warping.
- **apply_affine_transform(src, src_tri, dst_tri, size):** Warps triangular regions.
- **warp_and_blend_face(source_img, destination_img, ...):** Aligns and blends faces.
- **face_swap(source_image, destination_image):** The main function performing face swap.

## Example Output
<p align="center">
  <img src="https://github.com/krishnaperumalla/Face-Swap-Using-Open-CV-and-python/blob/main/download.png?raw=true" width="600">
</p>


## Limitations
- Requires **clear and frontal** face images for accurate detection.
- Performance may vary with **complex backgrounds or occlusions**.



