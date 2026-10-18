# 🛞 AI-Driven Tyre Health Checker
### An Intelligent Computer Vision System for Tyre Condition Analysis and Predictive Maintenance

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![YOLOv8](https://img.shields.io/badge/Object_Detection-YOLOv8-purple)
![TensorFlow](https://img.shields.io/badge/Deep_Learning-TensorFlow-orange)
![OpenCV](https://img.shields.io/badge/Computer_Vision-OpenCV-green)
![Streamlit](https://img.shields.io/badge/Dashboard-Streamlit-red)
![Scikit-learn](https://img.shields.io/badge/Machine_Learning-Scikit--learn-yellow)
![Status](https://img.shields.io/badge/Status-Development-orange)

---

## 📌 Project Overview

**AI-Driven Tyre Health Checker** is a computer vision and machine learning project designed to analyse tyre images and identify visible indicators of tyre wear and damage.

The system combines object detection, image processing, deep learning, and machine learning techniques to evaluate tyre condition and present the results through an interactive Streamlit dashboard.

The project aims to demonstrate how artificial intelligence can support tyre inspection, vehicle maintenance, and road-safety awareness.

Instead of relying entirely on manual visual inspection, the system processes tyre images to extract useful visual features and generate an interpretable analysis.

### 🎯 Main Objectives

- Detect tyres in input images.
- Classify tyre condition into different health categories.
- Analyse visible tread patterns and wear indicators.
- Identify potential punctures, deformations, and flat-tyre conditions.
- Estimate tyre health indicators from extracted image features.
- Present analysis results through an interactive dashboard.
- Demonstrate the application of AI and computer vision to automotive maintenance.

---

## ✨ Key Features

### 1. 🔍 Tyre Detection

The system uses YOLOv8 for object detection.

The detection module identifies tyre regions in an image and extracts regions of interest for further analysis.

**Key capabilities:**
- Image-based object detection.
- Tyre region localisation.
- Bounding-box visualisation.
- Support for integrating custom-trained detection weights.

### 2. 🧠 Tyre Condition Classification

The classification module is designed to categorise tyre conditions using image features.

The intended categories are:

| Category | Description |
|---|---|
| Good | Tyre appears visually healthy. |
| Worn | Visible tread wear or deterioration. |
| Critical | Potentially severe wear or damage. |
| Puncture | Possible visible puncture-related damage. |
| Flat | Possible deflation or deformation. |

Classification performance depends on the availability and quality of the trained model and dataset.

### 3. 📊 Tread Wear Analysis

OpenCV-based image processing techniques are used to analyse visible tread patterns.

The intended processing pipeline includes:

1. Image preprocessing.
2. Grayscale conversion.
3. Contrast enhancement.
4. Noise reduction.
5. Edge detection.
6. Morphological operations.
7. Tread-region analysis.
8. Feature extraction and score calculation.

The resulting visual features can be used to generate an indicative tread-condition score.

**Note:** An image-derived score is not equivalent to a calibrated physical tread-depth measurement.

### 4. ⚠️ Puncture and Flat-Tyre Analysis

The system is designed to analyse tyre shape and visible irregularities using image-processing techniques.

Potential techniques include:

- Image thresholding.
- Contour extraction.
- Circularity analysis.
- Aspect-ratio analysis.
- Hough Circle Transform.
- Shape-anomaly detection.

These methods can help identify suspicious visual patterns.

However, a puncture or pressure loss cannot always be confirmed from a photograph alone.

### 5. 📈 Tyre Lifespan Estimation

The project includes a regression-based approach for estimating a tyre-health indicator or potential remaining service distance.

Potential input features include:

- Tread-condition score.
- Predicted condition category.
- Edge density.
- Circularity.
- Aspect ratio.

A meaningful remaining-distance prediction requires a properly trained regression model and representative labelled data.

**Important:** Any distance estimate is experimental and must not be treated as a certified prediction of safe driving distance.

### 6. 🖥️ Interactive Streamlit Dashboard

The dashboard provides a user interface for interacting with the analysis pipeline.

Planned dashboard capabilities include:

- Uploading tyre images.
- Displaying analysis results.
- Visualising tyre-condition categories.
- Presenting tread-analysis indicators.
- Displaying potential anomaly alerts.
- Showing available model predictions.
- Presenting image-processing outputs.

The availability of individual features depends on the corresponding implementation and model files.

---

## 🏗️ System Architecture

The project follows a modular computer vision pipeline.

```text
                 ┌────────────────────────┐
                 │       User Input       │
                 │                        │
                 │  Tyre Image / Webcam   │
                 └────────────┬───────────┘
                              │
                              ▼
                 ┌────────────────────────┐
                 │    Image Processing    │
                 │                        │
                 │ Resize, Normalize,     │
                 │ Prepare Image          │
                 └────────────┬───────────┘
                              │
                              ▼
                 ┌────────────────────────┐
                 │   Tyre Object Detection│
                 │                        │
                 │        YOLOv8           │
                 └────────────┬───────────┘
                              │
                              ▼
                 ┌────────────────────────┐
                 │   Feature Extraction   │
                 │                        │
                 │   Tyre Region / ROI    │
                 └────────────┬───────────┘
                              │
                 ┌────────────┼────────────┐
                 │            │            │
                 ▼            ▼            ▼
          ┌────────────┐ ┌───────────┐ ┌────────────┐
          │ Condition  │ │   Tread   │ │  Anomaly   │
          │Classification│ │ Analysis │ │ Detection  │
          └──────┬─────┘ └─────┬─────┘ └──────┬─────┘
                 │             │              │
                 └─────────────┼──────────────┘
                               │
                               ▼
                 ┌────────────────────────┐
                 │   Feature Integration  │
                 │                        │
                 │ Condition and Health   │
                 │ Indicators             │
                 └────────────┬───────────┘
                              │
                              ▼
                 ┌────────────────────────┐
                 │   Optional Regression  │
                 │                        │
                 │ Lifespan Estimation    │
                 └────────────┬───────────┘
                              │
                              ▼
                 ┌────────────────────────┐
                 │   Streamlit Dashboard  │
                 │                        │
                 │ Results, Indicators,   │
                 │ Visualisations, Alerts  │
                 └────────────────────────┘
```

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| YOLOv8 | Object detection |
| TensorFlow / Keras | Deep learning and classification |
| OpenCV | Image processing and computer vision |
| Scikit-learn | Machine learning and regression |
| NumPy | Numerical computation |
| Matplotlib | Data visualisation |
| Pillow | Image loading and manipulation |
| Streamlit | Interactive web dashboard |
| Plotly | Interactive charts and visualisations |
| PyTorch | Deep learning framework used by Ultralytics |
| Git and GitHub | Version control and project hosting |

---

## 📁 Project Structure

```text
AI-driven-Tire-Health-Checker/
│
├── app/
│   └── streamlit_app.py
│
├── src/
│   ├── dataset_loader.py
│   ├── detection.py
│   ├── classification.py
│   ├── tread_analysis.py
│   ├── puncture_detection.py
│   ├── lifespan.py
│   └── pipeline.py
│
├── models/
│   ├── yolo/
│   ├── classifier/
│   └── regression/
│
├── tests/
│   ├── test_pipeline.py
│   └── run_tests.py
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── annotations/
│
├── train.py
├── requirements.txt
├── README.md
├── .gitignore
└── yolov8n.pt
```

**Note:** This structure describes the intended organisation of the project. Some files and directories may need to be created if they are not present in your current repository.

---

## 💻 Installation and Setup

Follow these instructions to run the project locally on Windows.

### Prerequisites

Install the following software:

- Python 3.10 or a compatible supported version.
- Git.
- Visual Studio Code (recommended).
- pip package manager.

A compatible Python environment is recommended because deep-learning libraries may not support every Python release.

### Step 1: Clone the Repository

Open PowerShell or the VS Code terminal.

Run:

```bash
git clone https://github.com/abhigoraya005/AI-driven-Tire-Health-Checker.git
```

Navigate into the project:

```bash
cd AI-driven-Tire-Health-Checker
```

### Step 2: Create a Virtual Environment

Run:

```bash
python -m venv venv
```

### Step 3: Activate the Environment

On Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

If activation succeeds, the terminal prompt will display `(venv)`.

### Step 4: Upgrade pip

```bash
python -m pip install --upgrade pip
```

### Step 5: Install Dependencies

```bash
pip install -r requirements.txt
```

Wait for all required packages to finish installing.

---

## 🚀 Running the Dashboard

After installing the dependencies, run the following command from the project root:

```bash
python -m streamlit run app/streamlit_app.py
```

When Streamlit starts successfully, the terminal will display a local address.

Open:

```text
http://localhost:8501
```

The application should load in your default web browser.

### Stopping the Dashboard

To stop the application, return to the terminal and press:

```text
Ctrl + C
```

---

## 🧠 Model Setup and Training

The project includes a pretrained YOLOv8 nano weights file:

```text
yolov8n.pt
```

This is a general-purpose pretrained object-detection model. Its presence does not mean that it has been specifically trained to detect every tyre condition.

### Training Command

If the training script and required datasets are available, the intended command is:

```bash
python train.py
```

To skip YOLO training when the script supports that option:

```bash
python train.py --skip-yolo
```

### Dataset Requirements

For condition classification, organise labelled images into category-specific folders.

```text
data/
└── raw/
    ├── good/
    ├── worn/
    ├── critical/
    ├── puncture/
    └── flat/
```

For custom YOLO training, the dataset should contain images and corresponding bounding-box annotations.

```text
data/
└── annotations/
    ├── train/
    │   ├── images/
    │   └── labels/
    └── val/
        ├── images/
        └── labels/
```

YOLO annotation files generally use normalized bounding-box coordinates.

Training requires correctly labelled data and an appropriate dataset configuration.

**Do not assume that the model can be trained successfully until the dataset, training code, and model-saving logic have been verified.**

---

## 🧪 Testing

The project includes a `tests/` directory intended for testing the computer vision pipeline.

If the test runner is present and configured, execute:

```bash
python tests/run_tests.py
```

Alternatively, if the project uses pytest:

```bash
python -m pytest tests/
```

Potential test cases include:

- Valid tyre images.
- Images without detectable tyres.
- Low-resolution images.
- Multiple tyres in one image.
- Blurred or poorly illuminated images.
- Unexpected model outputs.
- Missing model files.

The actual test coverage depends on the tests implemented in the repository.

---

## 📊 Expected Output

The system is intended to produce an analysis containing information such as:

| Output | Description |
|---|---|
| Condition | Predicted tyre-condition category |
| Tread Score | Indicative score derived from image features |
| Anomaly Indicators | Potential visible irregularities |
| Remaining Distance | Experimental regression estimate, if available |
| Alerts | Messages describing detected visual concerns |
| Inference Time | Time required to process an image, if measured |

An illustrative result might look like this:

```json
{
  "condition": "Worn",
  "tread_score": 43.2,
  "remaining_km": null,
  "status": "monitor",
  "alerts": [
    "Visible tread wear requires inspection"
  ]
}
```

**This JSON is an illustrative example, not a verified output from the current implementation.** The actual fields and values depend on the code and available models.

---

## 📸 Dashboard Screenshots

The project repository can include screenshots of the dashboard to demonstrate its interface and outputs.

Suggested screenshots:

1. Main dashboard.
2. Tyre image upload.
3. Object-detection results.
4. Tyre-condition classification.
5. Tread-analysis visualisation.
6. Anomaly detection.
7. Final analysis summary.

Add screenshots to your repository and reference them using Markdown.

For example, if you upload an image named `Analysis1.png` to the repository root:

```markdown
![Tyre Analysis Dashboard](Analysis1.png)
```

Repeat this for additional screenshots.

---

## 🔬 Applications

Potential applications of the project include:

- Automotive maintenance research.
- Computer vision experimentation.
- Vehicle inspection assistance.
- Tyre-condition monitoring prototypes.
- Predictive maintenance research.
- AI-assisted road-safety awareness.
- Educational demonstrations of deep learning and image processing.

The system is a research and development prototype rather than a certified automotive inspection system.

---

## ⚠️ Limitations and Safety Disclaimer

This project has several important limitations.

1. **Image dependency:** Results depend on image quality, lighting, viewing angle, and tyre visibility.

2. **Model dependency:** Classification performance depends on the training dataset and model quality.

3. **Tread-depth limitations:** Image-derived tread scores do not replace measurements from a calibrated tread-depth gauge.

4. **Puncture detection:** Small punctures, internal tyre damage, and air leakage may not be visible in an image.

5. **Lifespan estimation:** Remaining-distance predictions require validated training data and real-world testing.

6. **Generalisation:** Performance may vary across tyre manufacturers, tread designs, vehicle types, and environmental conditions.

7. **Safety:** The system must not be used as the sole basis for deciding whether a tyre is safe to drive on.

Always use appropriate physical inspection and professional assessment when tyre damage or unsafe conditions are suspected.

---

## 🔮 Future Improvements

Potential future enhancements include:

- Training a tyre-specific YOLO detection model.
- Developing a dedicated tyre-condition classification model.
- Integrating larger and more diverse tyre datasets.
- Improving tread-wear segmentation.
- Adding tyre-damage localisation.
- Integrating video-based tyre inspection.
- Improving dashboard visualisations.
- Adding model performance metrics.
- Evaluating precision, recall, F1-score, and confusion matrices.
- Validating predictions against physical tyre measurements.
- Deploying the dashboard to a cloud platform.
- Exploring edge deployment for automotive applications.

---

## 👨‍💻 Developer

**Abhiney Kumar**

B.Tech — Electronics and Communication Engineering

Dr. B.R. Ambedkar National Institute of Technology, Jalandhar

### Areas of Interest

- Artificial Intelligence and Machine Learning
- Computer Vision
- Embedded Systems
- Automotive Electronics
- Intelligent Monitoring Systems
- Predictive Maintenance

### GitHub

[abhigoraya005](https://github.com/abhigoraya005)

### Project Repository

[AI-driven-Tire-Health-Checker](https://github.com/abhigoraya005/AI-driven-Tire-Health-Checker)

---

## 📄 License

Choose an appropriate open-source license before distributing the project.

For example, if you decide to release your own project code under the MIT License, add a `LICENSE` file containing the license terms.

Check the licenses of third-party models, datasets, and dependencies separately before redistribution.

---

## 🙌 Acknowledgements

This project builds on open-source computer vision and machine learning technologies, including:

- Ultralytics YOLO.
- OpenCV.
- TensorFlow and Keras.
- Scikit-learn.
- Streamlit.
- NumPy and the Python ecosystem.

Their documentation and development resources support experimentation with AI-driven tyre inspection.

---

## ⭐ Support

If you find this project useful for learning or research, consider starring the repository on GitHub.

Contributions, suggestions, and constructive feedback are welcome.

---

**Developed by Abhiney Kumar**
**Inspired by git usernmae: Adesh2204
*Exploring the intersection of Artificial Intelligence, Computer Vision, and Automotive Safety.*
