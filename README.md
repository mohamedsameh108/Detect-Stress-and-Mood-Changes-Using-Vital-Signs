# 🧠 Detect Stress and Mood Changes Using Vital Signs 
*A Machine Learning Approach to Real-Time Emotion Detection from Wearable Sensors*  
📍 Developed for the **Biomedical Signal Processing** course – Helwan University  

---

## 📌 Overview

This project explores the classification of emotional states using physiological data from the **WESAD dataset**.  
Our goal: build **machine learning models** that can accurately classify a person's emotional state using data from wearable sensors like ECG, EDA, Respiration, BVP, and Accelerometers.

---

## 🔍 Problem Statement

Emotion recognition using biosignals is a growing field in affective computing. By analyzing signals from wearable sensors, we can infer emotional states—such as stress, amusement, or baseline (neutral)—which can be applied in:

- Mental health monitoring
- Smart wearables
- Human-computer interaction
- Real-life stress detection systems

---

## 🧪 Dataset

**Dataset Used:** [WESAD (Wearable Stress and Affect Detection)](https://archive.ics.uci.edu/ml/datasets/WESAD) [Data on Kaggle](https://www.kaggle.com/datasets/mohamedasem318/wesad-full-dataset) big thanks to [Eng/Mohamed Assem](https://www.linkedin.com/in/mohamedasem318/).

- **Subjects:** 15 (excluding subject 16 due to feature extraction error)
- **Sensors:**  
  - Chest: ECG, EDA, RESP, EMG, Temp, ACC  
  - Wrist: BVP, EDA, ACC, Temperature

Some windows had to be excluded due to incomplete feature extraction (caused by missing values or limited window size). We only used complete, valid records for model training and testing.

---

## 🏗️ Model Architecture

We designed two main model categories—each serving a different application context:

## Category 1: **WESAD-Centric Models (Controlled Conditions)**

These models are developed based strictly on the controlled conditions and features extracted from the WESAD dataset.

### 🧠 Model 1: *VitalCore Classifier*
- **Type**: One-vs-Rest Logistic Regression
- **Features Used**: Top 10 features from **ECG**, **Chest EDA**, and **Respiration**
- **Rationale**: Focuses on physiological signals that are frequently referenced in academic literature.
- **Performance**: Achieved **79% accuracy**

### 🌐 Model 2: *FusionTop Classifier*
- **Type**: One-vs-Rest Logistic Regression
- **Features Used**: Top 15 features from **all available signals**
- **Rationale**: Combines a wider range of informative signals for improved accuracy.
- **Performance**: Achieved **84% accuracy**

---

## Category 2: **Real-World-Oriented Models (Wearable Scenarios)**

These models are designed with practical, real-world deployment in mind—targeting wearables like smartwatches, fitness trackers, and sports gear.

### ⌚ Model 3: *SmartBand Core*
- **Type**: Weighted One-vs-One Logistic Regression
- **Features Used**: **BVP** and **Wrist Acceleration**
- **Rationale**: Utilizes only sensors commonly available in everyday smartwatches.
- **Performance**: Achieved **74% accuracy**

### 🏃‍♂️ Model 4: *WristFit Classifier*
- **Type**: Weighted One-vs-One Logistic Regression
- **Features Used**: **All Wrist-based Signals**
- **Rationale**: Tailored for fitness wearables and advanced smartwatch usage.
- **Performance**: Achieved **81% accuracy**

### 🧍 Model 5: *ChestPro Classifier*
- **Type**: Weighted One-vs-One Logistic Regression
- **Features Used**: **All Chest-based Signals**
- **Rationale**: Suitable for athletes in sports (e.g., football) where limb wearables are impractical.
- **Performance**: Achieved **85% accuracy**

### 🔬 Model 6: *FullScope Model*
- **Type**: Weighted One-vs-One Logistic Regression
- **Features Used**: **All Extracted Features**
- **Rationale**: Designed for experimental setups and comprehensive research environments.
- **Performance**: Achieved **87% accuracy**

> 📈 All models are capable of improvement with a larger and more varied dataset.

---

## 🧠 Feature Engineering

- Features extracted using sliding windows.
- Top features selected using feature importance and correlation analysis.
- Subject 16 excluded due to failed extraction.
- Redundant or constant columns removed (e.g., "subject number", features with only "No" values).

---

## 📝 Project Acknowledgment

This project was proudly created as part of the **Biomedical Signal Processing** course at the **Faculty of Engineering, Helwan University** – **Biomedical Engineering Department**, by **Group 12**.

👥 **Team Members**:  
- [Hebatullah ElGazoly](https://www.linkedin.com/in/hebatullah-elgazoly-308ab2243/)  
- [Mohamed Sameh](https://www.linkedin.com/in/muhamedsameh/)

🧠 **Under the Supervision of**:  
- [Prof. Ibrahim Sadek](https://www.linkedin.com/in/ibrahim-sadek-78830075/)

---

## 🚀 How to Use This Repo

1. Clone the repository  
   ```bash
   git clone https://github.com/mohamedsameh108/Detect-Stress-and-Mood-Changes-Using-Vital-Signs.git
   cd Detect-Stress-and-Mood-Changes-Using-Vital-Signs
   ```

2. Install requirements  
   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebook  
   Use Jupyter or Colab to open and execute the main notebook.

---

## 🔗 GitHub Repository

Explore the notebook, trained models, and more via the link below:  
👉 [Visit Our GitHub Repo](https://github.com/mohamedsameh108/Detect-Stress-and-Mood-Changes-Using-Vital-Signs)

> ⚠️ Warning: Side effects of visiting this repo include improved knowledge, data addiction, and overconfidence in logistic regression. Explore responsibly! 😅

---

## 📬 Feedback & Contact

We’re still students and always open to learning—so if you’ve got improvements, suggestions, or just want to geek out over biosignals:

💬 Leave an issue or  
📩 Connect with us on [LinkedIn](https://www.linkedin.com/in/muhamedsameh/) or [LinkedIn](https://www.linkedin.com/in/hebatullah-elgazoly-308ab2243/)  

---

## 🛑 Disclaimer

Please don't try to deploy this in a medical setting just yet.  
We're engineers in training, not doctors (yet 😄).  
Stay safe and have fun learning!

