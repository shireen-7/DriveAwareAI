🚗 DriveAwareAI

Real-Time Driver Distraction and Drowsiness Detection using ResNet-18, Temporal Attention-LSTM and Explainable AI

📌 Project Overview

DriveAwareAI is a deep learning-based Driver Monitoring System (DMS) designed to detect driver distraction and potential drowsiness using computer vision techniques.

The system combines two independent ResNet-18 models for driver activity classification and eye-state detection with an Attention-based LSTM network to analyse temporal patterns across consecutive frames.

It also incorporates rule-based decision fusion and Grad-CAM visualization to improve prediction interpretation.

The main objective is to develop an intelligent driver-monitoring framework that can identify unsafe driving behaviour and support road safety.

🎯 Objectives

- Detect distracted driving activities.
- Identify open and closed eye states.
- Analyse consecutive frames to identify potential drowsiness.
- Reduce false alarms using temporal analysis.
- Improve model interpretability using Grad-CAM.
- Develop an efficient driver-monitoring architecture.

📂 Datasets Used

1. State Farm Distracted Driver Dataset

- 22,424 labelled driver images.
- 26 different drivers.
- 10 activity classes (c0–c9).
- Used for driver distraction classification.

Activities include:

- Safe driving
- Texting
- Phone calls
- Operating the radio
- Drinking
- Reaching behind
- Hair and makeup
- Talking to passengers

2. MRL Eye Dataset

- 84,898 eye images.
- Contains open and closed eye samples.
- Includes variations in lighting and eye appearance.
- Used for eye-state classification.

Note: The datasets are not included in this repository. Please obtain them from their respective official dataset sources and follow their usage terms.

🧠 Proposed Methodology

The proposed system consists of three main deep learning components.

1. ResNet-18 – Driver Distraction Detection

- Uses transfer learning with a pretrained ResNet-18 architecture.
- Extracts important visual features from driver images.
- Classifies driver activities into 10 categories.
- Fine-tunes the deeper residual layers to improve classification performance.

2. ResNet-18 – Eye-State Detection

- Uses a separate ResNet-18 model.
- Processes cropped eye images.
- Classifies eye states as OPEN or CLOSED.
- Generates eye-closure confidence scores.

3. Attention-Based LSTM – Temporal Analysis

- Uses frame-level prediction probabilities from both spatial models.
- Processes sequences of 30 consecutive frames.
- Uses LSTM to learn temporal dependencies.
- Applies an additive attention mechanism to assign importance to different frames.
- Produces three driver-state categories:
  - SAFE
  - DISTRACTED
  - DROWSY

4. Decision Fusion

Combines temporal predictions with rule-based safety conditions.

The system considers:

- PERCLOS (Percentage of Eye Closure).
- Consecutive closed-eye frames.
- Non-safe driving activity predictions.

5. Grad-CAM Explainability

Gradient-weighted Class Activation Mapping (Grad-CAM) generates visual heatmaps to identify image regions influencing CNN predictions.

This helps inspect the model's decision-making process.

⚙️ Technologies Used

- Python
- PyTorch
- ResNet-18
- Convolutional Neural Networks (CNN)
- Long Short-Term Memory (LSTM)
- Attention Mechanism
- Grad-CAM
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Kaggle Notebooks

📊 Experimental Results

The models were evaluated separately on their respective test datasets.

Model| Dataset| Accuracy
ResNet-18 (Distraction)| State Farm| 90.52%
ResNet-18 (Eye State)| MRL Eye| 98.79%
Attention-LSTM + Fusion| Temporal experiment| 99.20%

Additional Performance Metrics

Distraction Detection

- Accuracy: 90.52%
- Macro F1-score: 0.8941
- ROC-AUC: 0.9891

Eye-State Detection

- Accuracy: 98.79%
- Macro F1-score: 0.9879
- ROC-AUC: 0.9992

Temporal Analysis

- Sequence accuracy: 99.20%
- SAFE false-alarm rate: 1.2%

The temporal experiment uses simulated sequences. Its results should not be interpreted as validation on real-world driving videos.

📈 Key Findings

- Fine-tuning ResNet-18 improved distraction classification accuracy from 47.46% to 90.52%.
- The eye-state classifier achieved 98.79% accuracy.
- Temporal attention helps analyse driver behaviour across multiple frames.
- Decision fusion reduced reported safe-driving false alarms in the temporal experiment.
- Grad-CAM provides visual explanations of CNN predictions.

🚀 Future Enhancements

- Integrate real-time webcam input.
- Train and evaluate using real driving video sequences.
- Improve detection of difficult distraction categories.
- Test under different lighting conditions.
- Optimize the system for edge-device deployment.
- Develop a complete real-time driver monitoring application.

📌 Conclusion

DriveAwareAI presents a multi-model deep learning framework for driver distraction and drowsiness monitoring. By combining ResNet-18, Attention-LSTM, rule-based decision fusion and Grad-CAM, the project explores how spatial and temporal information can be used together for driver-state analysis.

The experimental results demonstrate promising performance on the selected datasets, while real-world video validation remains an important next step.

---

Project: DriveAwareAI
Domain: Deep Learning | Computer Vision | Artificial Intelligence | Road Safety
