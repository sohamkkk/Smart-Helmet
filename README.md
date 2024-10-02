

# 🎥🔍 Smart Helmet for the specially abled indivisuals 🗣️ on Raspberry Pi 🍓

Welcome to the **Object Detection with Voice Alerts** project! This fun and interactive project turns your Raspberry Pi into a live object detector and commentator, using the power of **OpenCV** and **pyttsx3** for text-to-speech (TTS). Watch objects being identified in real-time 🕒, and hear their names spoken aloud 🎧!

## 🌟 Features

- **Real-Time Object Detection**: Watch as your Pi detects objects live from the camera feed! 📷
- **Voice Announcements**: Each detected object is spoken aloud, like having a personal assistant for your camera. 🎤
- **Customizable**: Adjust detection thresholds, NMS, and even choose which objects you want to detect. 🎛️
- **Clean Display**: The detected objects are highlighted with green bounding boxes and labeled with their confidence score. 💬✅

---

## ⚙️ What You’ll Need

1. **Raspberry Pi** (with a camera set up) 🍓📸
2. **OpenCV** installed on your Pi:
   ```bash
   sudo apt-get install python3-opencv
   ```
3. **pyttsx3** for voice alerts:
   ```bash
   pip install pyttsx3
   ```
4. **Pre-trained Model Files**:
   - `ssd_mobilenet_v3_large_coco_2020_01_14.pbtxt`: Neural network config file.
   - `frozen_inference_graph.pb`: Pre-trained weights for object detection.
   - `coco.names`: List of object names the model can detect.

---

## 🚀 Setup Instructions

1. **Place the Model Files**:
   - Copy these files to `/home/pi/Desktop/Object_Detection_Files/`:
     - `ssd_mobilenet_v3_large_coco_2020_01_14.pbtxt`
     - `frozen_inference_graph.pb`
     - `coco.names`

2. **Run the Python Script**:
   Fire up your terminal and run the script:
   ```bash
   python3 object_detection.py
   ```
3. **Enjoy the Show**:
   The live video feed will pop up! Objects will be detected, highlighted, and spoken out loud in real-time. 🎉👀

---

## 🛠️ How It Works

1. **Model Setup**: The pre-trained SSD MobileNet model detects objects from your camera feed.
2. **Detection**: The objects are outlined with a green box, labeled with the object name and confidence score.
3. **Voice Feedback**: For each detected object, its name is spoken out loud using the text-to-speech engine. 🎧🗣️
   
   *Example*: If the model detects a "dog" 🐕, you’ll see it labeled on the screen and hear "dog" spoken through the speakers.

---

## 🔧 Configuration

### 🎯 Adjusting Detection Parameters

- **Threshold (confidence level)**: Defines the minimum confidence needed to consider an object detected.
- **NMS (Non-Maximum Suppression)**: Helps filter overlapping boxes.

```python
result, objectInfo = getObjects(img, 0.45, 0.2)
```

### 🎨 Customizing Detected Objects

Want to detect only specific objects like "person" or "dog"? Modify the `objects` parameter:

```python
result, objectInfo = getObjects(img, 0.45, 0.2, objects=['person', 'dog'])
```

---

## 📐 Camera Feed Setup

- **Resolution**: The feed is set to `640x480` for smooth performance on your Raspberry Pi.
- **Real-Time Detection**: Every frame from the camera is analyzed for object detection.

---

## 📢 Voice Settings

The **pyttsx3** engine powers the voice alerts, and it’s highly customizable:
- **Voice rate**: Change how fast the voice speaks.
- **Volume**: Control how loud the voice is.

---

## 👩‍💻 Example Output

Here’s what happens when the script runs:

1. **Visual Output**: You’ll see a live video feed, with detected objects like "person" or "dog" boxed and labeled.
2. **Voice Feedback**: Each object’s name is spoken aloud, like your Raspberry Pi is talking to you! 🎙️

---

## 💡 Tips & Tricks

- For better performance 🏎️, reduce the input size or try lowering the detection threshold.
- You can easily customize which objects you want to detect. Want to focus only on animals? 🐕🐈 No problem!

---

## 📝 License

This project is released under the **MIT License**, so feel free to modify, enhance, and share your own versions! 🎉

---

### Have Fun Detecting! 🔍📢

Turn your Raspberry Pi into a real-time object detector and announcer! Whether you're identifying people, pets, or everyday objects, the possibilities are endless. Enjoy your journey into the exciting world of object detection with voice feedback!
