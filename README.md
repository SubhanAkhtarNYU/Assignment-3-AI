## Overview

The assignment consists of three main tasks:

1. **Object Detection (25 points)**
   - **Objective:** Detect cars in a given video.
   - **Method:** The video is split into frames, and an object detector (of your choice) is used to identify cars. The output is a video with the bounding boxes and centroids of the detected vehicles superposed on the original video.
   - **Note:** The video can be downloaded using [yt-dlp](https://github.com/yt-dlp/yt-dlp).

2. **Drone Tracking with Kalman Filter (50 points)**
   - **Objective:** Track the detected vehicle(s) using Kalman filters.
   - **Method:** 
     - Use the `filterpy` library to implement the Kalman filter.
     - Initialize the filter using the detections from the object detection stage.
     - Since the drone crashes near the end of the video (resulting in the vehicle stopping), the filter performance is evaluated by comparing the detected centroids with the estimated positions.
     - An innovation sequence (the difference between the actual measurements and the filter's predictions) is computed and its magnitude plotted over time to assess the tracking performance.

3. **Count Vehicular Traffic (25 points)**
   - **Objective:** Monitor and record the number of vehicles passing through a highway.
   - **Method:** 
     - Assume the video is captured from a stationary camera.
     - Implement a counting mechanism that reports the number of vehicles moving in two different directions.
     - The counts are normalized by the total duration of the video, starting from 0 and increasing as vehicles pass by.

## Repository Contents

- **AI_Assignment_3.ipynb:**  
  The primary notebook containing the implementation for all three tasks. It includes:
  - Frame extraction and object detection code.
  - Kalman filter implementation using `filterpy`.
  - Computation and plotting of the innovation sequence.
  - Vehicle counting logic based on the tracked centroids.
  - Inline outputs (videos, plots, and other results).

- **Outputs:**  
  The notebook displays the processed video frames with bounding boxes and centroids, the Kalman filter tracking performance (innovation sequence plot), and the vehicular traffic count as a function of time.

## Setup and Installation

To run this notebook locally, follow these steps:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/your-repo-name.git
   cd your-repo-name
   ```

2. **Create and Activate a Virtual Environment (Optional but Recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows, use: venv\Scripts\activate
   ```

3. **Install Required Dependencies:**
   Install the necessary Python packages using pip:
   ```bash
   pip install -r requirements.txt
   ```
   Make sure to include packages such as:
   - `opencv-python` (for video processing)
   - `filterpy` (for the Kalman filter)
   - Other libraries such as `numpy`, `matplotlib`, etc.

4. **Download the Video:**
   Use `yt-dlp` to download the video used in this assignment:
   ```bash
   yt-dlp <video_url>
   ```
   Replace `<video_url>` with the actual URL provided for the assignment.

5. **Run the Notebook:**
   Launch Jupyter Notebook or JupyterLab:
   ```bash
   jupyter notebook AI_Assignment_3.ipynb
   ```
   Follow the steps outlined in the notebook to reproduce the results.

## Usage

- **Object Detection:**  
  The notebook processes the video to extract frames, applies the object detection model to locate cars, and creates an output video with overlaid bounding boxes and centroids.

- **Kalman Filter Tracking:**  
  The Kalman filter is used to predict and update the state of the tracked vehicle. The resulting innovation sequence is plotted to analyze the difference between the detection measurements and the filter's predictions.

- **Vehicle Counting:**  
  The solution includes logic to count vehicles moving in two directions. The counts are updated over time and normalized by the video duration.

## Project Structure

```
.
├── AI_Assignment_3.ipynb       # Main notebook containing the full implementation and outputs
├── README.md                  # This file
├── requirements.txt           # List of dependencies
└── outputs/                   # Directory containing processed videos and plots (if applicable)
```
