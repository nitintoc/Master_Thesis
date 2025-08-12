Methodology
1. Blemish Simulation
Used OpenCV to synthetically introduce:

Dust spots

Scratches

Smudges

Blurred areas

Controlled parameters: size, opacity, location, and shape.

2. Model Training & Validation
Datasets: KITTI, BDD100K

Models:

YOLOv4 for real-time detection.

Fast R-CNN for high-accuracy detection.

FCN for semantic segmentation.

Evaluation Metrics:

mAP (Mean Average Precision)

IoU (Intersection over Union)

Pixel Accuracy (for segmentation tasks)

3. Robustness Analysis
Measure performance drop (%) as blemish severity increases.

Compare sensitivity of different models to blemishes.

Identify critical defect characteristics that cause unacceptable performance degradation.

4. Statistical Correlation
Regression and correlation analysis between:

Blemish size, density, opacity

Drop in mAP / IoU / Pixel Accuracy

Determine pass/fail thresholds for manufacturing.

5. Cloud Deployment
Implemented as an end-to-end pipeline:

Data preprocessing

Blemish simulation

Model inference

Result visualization

Deployed on Google Cloud Platform with:

AI Platform for model serving

Cloud Storage for datasets

Cloud Functions for automation

Languages: Python 3.10

Libraries: OpenCV, PyTorch, TensorFlow, NumPy, Matplotlib, Pandas

Models: YOLOv4, Fast R-CNN, FCN

Cloud: Google Cloud Platform (AI Platform, Cloud Storage, Cloud Functions)

Tools: Jupyter Notebook, Docker, Git

Expected Outcomes
Quantitative relationship between blemish severity and AI model performance.

Defined manufacturing quality thresholds for camera acceptance.

Open-source simulation tool for blemish testing.

Cloud-deployable AI robustness testing pipeline.

Citation
If you use this work in your research, please cite:

View published paper: https://www.sciencedirect.com/science/article/pii/S1877050924000619
