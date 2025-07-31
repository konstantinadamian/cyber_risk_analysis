Cybersecurity Threat Detection in Telesurgery Systems
This project presents a supervised machine learning pipeline for detecting potential cybersecurity threats in robotic telesurgery systems. The dataset captures gesture-based communication, network transmission metrics, and encryption status across surgical events.

Workflow Overview
Data Preprocessing

Clean parsing of gesture coordinates (x, y, z)

Timestamp decomposition (hour, day, month, etc.)

Conversion of categorical variables (Robot Status, Encryption Status, Sender, Receiver)

Removal of target-leaking columns (e.g., Threat Severity, Response Time, Response Action Taken)

Feature Engineering

Gesture dynamics: gesture_magnitude, gesture_speed, squared axes (x², y², z²)

Network behavior: duration_latency_ratio, latency and transfer rate analysis

One-hot encoding for gesture type

Modeling

Pipeline: FunctionTransformer + XGBClassifier

Imbalanced binary classification (Threat Detected: 70% positive, 30% negative)

Applied scale_pos_weight to adjust class distribution

Evaluation: Stratified 10-fold cross-validation using f1-score, along with test-set metrics (Precision, Recall, ROC AUC)

Explainability

SHAP summary plots to analyze model behavior

Identification of top contributing features (e.g., gesture_duration, latency, encryption_status, gesture type)

📊 Objective
To build a robust and interpretable machine learning model that can detect cyber threats in robotic surgical environments, accounting for imbalanced data and critical communication indicators.
