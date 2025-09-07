# 🚦 Intelligent Traffic Violation Detection System

> AI-powered system that analyzes CCTV/video feeds to automatically detect traffic violations such as helmetless riders, signal jumping, and triple riding using object detection + multi-object tracking.

---

## 📌 Table of contents
- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Future Enhancements](#future-enhancements)
- [Author](#author)
- [License](#license)

---

## 📌 Project Overview
This project processes CCTV/video streams to detect and track riders and vehicles, then applies simple rule-based logic to flag traffic violations such as:

- Helmetless riders (no helmet detected on rider)
- Signal jumping (vehicle crosses intersection when light is red)
- Triple riding (more than two riders on a two-wheeler)

It is designed for Smart City / GovTech usage to reduce manual monitoring, improve road safety, and provide actionable insights to authorities.

---

## 🚀 Key Features
- 🔍 Real-time object detection (YOLOv8 / Detectron2)
- 🧭 Multi-object tracking (DeepSORT) for consistent identities across frames
- ⚠️ Rule-based violation detection (helmet, signal, triple riding)
- 📥 Accepts CCTV RTSP stream or local video files
- 📊 Logs violations with timestamps and bounding boxes for review
- 🗂️ Stores outputs (annotated video frames, CSV/JSON logs)

---

## 🛠️ Tech Stack
| Component | Purpose |
|---|---|
| **YOLOv8 / Detectron2** | Object detection (person, helmet, motorbike, vehicle) |
| **DeepSORT** | Multi-object tracking across frames |
| **OpenCV** | Video capture, processing & visualization |
| **Python** | Glue code, inference, tracking & logging |
| **Pandas / JSON** | Logging & reporting outputs |

---

## 📂 Project Structure

```
intelligent-traffic-violation-detection/
│
├── data/                        # Sample videos, images, test datasets
│
├── models/                      # Pre-trained YOLO/Detectron2 weights
│
├── src/                         # Source code
│   ├── run_pipeline.py          # Main entry point (video inference pipeline)
│   ├── detection.py             # Object detection module (YOLOv8 / Detectron2)
│   ├── tracking.py              # DeepSORT tracking module
│   ├── violations.py            # Violation detection logic (helmetless, triple ride, signal jump)
│   ├── utils/                   # Helper utilities
│   │   ├── drawing.py           # Drawing bounding boxes, annotations
│   │   ├── logging.py           # Save violations, logs, reports
│   │   └── preprocessing.py     # Frame extraction, resizing, ROI masks
│   └── config/                  # Configurations
│       ├── pipeline.yaml        # Model paths, thresholds
│       └── classes.json         # Class label mappings
│
├── outputs/                     # Annotated videos, violation logs, snapshots
│
├── notebooks/                   # Jupyter notebooks (experiments, training, evaluation)
│
├── README.md                    # Project documentation
├── requirements.txt             # Python dependencies
├── .gitignore                   # Ignore files/folders
└── LICENSE                      # MIT license

```
## 📸 Demo Preview  
<img width="1869" height="101" alt="Image" src="https://github.com/user-attachments/assets/8d84da24-a964-4ae1-8de0-175aba709ddd" />
<img width="1861" height="843" alt="Image" src="https://github.com/user-attachments/assets/970db2ea-cc7d-40c3-9784-035b7289b2b5" />
<img width="1861" height="801" alt="Image" src="https://github.com/user-attachments/assets/8c1983fd-e8e5-434d-935e-c78ed1ce35ae" />

---
## 🔮 Future Enhancements

📷 Automatic Number Plate Recognition (ANPR) to identify violators and link them with vehicle registration databases.

🤖 Integration with advanced ML models for more complex violations (overspeeding, wrong-lane driving, distracted driving).

🌍 Real-time alerting system integrated with traffic police dashboards or mobile apps for on-ground enforcement.

☁️ Deployment to cloud/edge platforms (AWS / Azure / NVIDIA Jetson) for scalable and low-latency monitoring.

📱 Mobile-friendly violation reports for authorities to access on-the-go.

📊 Analytics dashboards with violation heatmaps, trends, and KPIs for city-level traffic management.

🧠 Adaptive learning system that improves detection accuracy under challenging conditions (night, rain, occlusions).

🛰️ Integration with IoT and smart traffic signals for automated traffic control and violation prevention. 

---
## 👩‍💻 Author  
**Pratyush Kashyap Mishra**  
📍 AI / Computer Vision Enthusiast
🔗 [Portfolio](https://github.com/pratyushkm894) | [LinkedIn](https://www.linkedin.com/in/pratyushkm809) 

---

## 📜 License  
This project is open-sourced under the MIT License — feel free to use and adapt it!
