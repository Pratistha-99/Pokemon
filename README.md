# 📊 Analysis of Quality of Experience (QoE) in Video Streaming

This repository presents a **data-driven analysis of Quality of Experience (QoE) in mobile video streaming**, focusing on how technical Quality of Service (QoS) metrics and user feedback influence perceived satisfaction.

The project was conducted as part of the **Data Science – Theory to Practice** course at **Télécom SudParis**, using real crowdsourced measurements from the **PoqeMoN project** collected around Paris.

---

## 🎯 Project Objectives

The main goals of this project are:

- Understand key drivers of user satisfaction (MOS) in video streaming  
- Analyze relationships between QoS metrics and QoE  
- Detect anomalies in user experience and network behavior  
- Identify at-risk users based on dissatisfaction signals  
- Build and compare machine learning models to predict user retention  

---

## 📂 Dataset Overview

- **Samples:** ~1,540 video streaming sessions  
- **Users:** 181 participants  
- **Devices:** 9 Android device models  
- **Operators:** Orange, SFR, Bouygues, Free  
- **Target Variable:** Mean Opinion Score (MOS), rated from 1 (poor) to 5 (excellent)

### Feature Categories

- **QoA (Quality of Application):**  
  Bitrate, buffering time, buffering count, framerate, dropped frames, resolution  

- **QoS (Quality of Service):**  
  Network operator, service type  

- **QoD (Quality of Device):**  
  Device model, OS version, API level  

- **QoU (Quality of User):**  
  Age, gender, study group  

- **QoF (Quality of Feedback):**  
  Audio and video quality ratings  

---

## 🔍 Exploratory Data Analysis (EDA)

Key insights from EDA include:

- Strong negative correlation between buffering time/count and MOS  
- Framerate positively impacts user satisfaction, especially above 25 fps  
- Bitrate alone is not a reliable predictor of user satisfaction  
- Dataset shows imbalances in device models, OS versions, and operators  
- MOS distribution is right-skewed, with most users rating 4 or 5  

---

## 🚨 Anomaly Detection

Two complementary techniques were applied:

- **Z-Score Analysis**  
  Detects extreme buffering times and MOS values  

- **Isolation Forest**  
  Identifies multidimensional and non-linear anomalies  

**Result:**  
A total of **77 anomalous sessions** were identified, improving robustness before modeling.

---

## 🤖 Modeling & Prediction

To predict **user retention**, MOS was transformed into a binary target:

- **Retained:** MOS ≥ 4  
- **At-Risk:** MOS < 4  

### Models Implemented

| Model               | Accuracy | Key Strength                                   |
|--------------------|----------|------------------------------------------------|
| Random Forest       | 90.71%   | Interpretability & feature importance           |
| XGBoost             | **90.50%** | Best overall performance                        |
| LightGBM            | 90.28%   | Fast and computationally efficient              |
| Logistic Regression | 90.06%   | Strong baseline                                 |

### Most Important Features

- Audio quality (QoF_audio)  
- Buffering time  
- Video quality feedback  

---

## 🧠 Key Takeaways

- Buffering is the most damaging factor for user experience  
- Smooth playback matters more than raw bitrate  
- Audio quality plays a dominant role in user satisfaction  
- Ensemble models outperform linear approaches  

---

## ⚠️ Limitations

- Imbalanced representation of devices, OS versions, and operators  
- MOS is subjective and may include personal bias  
- No temporal analysis (e.g., peak vs off-peak usage)  

---

## 🚀 Future Work

- Incorporate temporal features such as time-of-day congestion  
- Analyze network latency and packet loss  
- Apply fairness-aware modeling to address categorical imbalance  
- Extend to real-time QoE monitoring  

---

## 🛠️ Tech Stack

- Python (Pandas, NumPy, Scikit-learn)  
- XGBoost & LightGBM  
- Matplotlib & Seaborn  
- Jupyter Notebook  

---

## 📄 Report & Code

- **Project Report:**  
  [Analysis of Quality of Experience in Video Streaming](docs/Analysis_of_Quality_of_Experience_in_Video_Streaming.pdf)
 

- **Code Repository:**  
  https://github.com/Pratistha-99/Pokemon/tree/main  

---

## 👤 Author

**Pratistha Thapa**  
MSc Data Science & Network Intelligence
Télécom SudParis  
Paris, France
