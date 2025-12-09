# Cattle-Detection

# 🐄 PenRider – Cattle Detection & Health Insight Prototype  
### Built during the 24-Hour Startup Summit (Winner 🏆)

PenRider is an early prototype that helps farmers track cattle more efficiently using computer vision and rule-based health insights.  
The goal: reduce the manual, time-consuming herd checks that producers still do with pen-and-paper.

This prototype was built in 24 hours and validated through conversations with farmers at **Canadian Western Agribition (Regina)**.

---

## 🚀 Features
### **1. YOLOv8-Based Cattle Detection**
- Detects cows/calves in pasture images  
- Extracts bounding boxes, centroids, and areas  
- Assigns unique IDs for each animal

### **2. Rule-Based Health Analyzer**
Uses only what YOLO provides:
- **Isolation check** – flags animals too far from the herd  
- **Undersized check** – detects animals significantly smaller than the group  
- **Lying-down check** – uses width/height ratio  
- Outputs structured health insights as **JSON**

### **3. Visual Output**
- Draws bounding boxes  
- Highlights animals needing attention  
- Produces a clean visualization for frontend integration  

---

## 🧠 Technical Stack
- Python  
- OpenCV  
- NumPy  
- Matplotlib  
- **Ultralytics YOLOv8 (8.0.196)**  
- Custom rule-based health analysis logic

The notebook includes installation notes for compatibility handling (Torch, OpenCV), model testing, and an end-to-end detection → analysis → visualization pipeline.

---

## 📸 Example Output (Concept)
- Input: pasture image  
- Output: annotated image + JSON summary:
```json
{
  "count": 7,
  "animals": [
    {"id": 1, "isolated": false, "undersized": false, "lying": false},
    ...
  ]
}
