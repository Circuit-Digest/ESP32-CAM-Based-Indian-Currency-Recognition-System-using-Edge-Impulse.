IoT-Based Indian Currency Detection System using ESP32 and Edge Impulse

An intelligent on-device currency recognition system using **ESP32-CAM** and **Edge Impulse** for real-time detection of Indian currency notes. The system identifies currency denominations locally on the ESP32-CAM and indicates results using LEDs and the Serial Monitor.

---

## 📌 Overview

This project uses an **ESP32-CAM module** to capture images of Indian currency notes and run a **machine learning model trained using Edge Impulse** directly on the device (AI on Edge). No cloud processing is needed for inference. Once a note is recognized, a corresponding LED glows, and the result is shown on the Serial Monitor.

---

## 🧠 What is AI on Edge?

AI on Edge refers to performing machine learning inference directly on embedded hardware instead of a cloud server. This approach offers key benefits:
- Low latency real-time processing
- Offline operation (no internet required)
- Better data privacy
- Lower power and bandwidth usage

Object recognition is one of the primary applications of AI on Edge, enabling the device to visually identify and classify currency notes without external servers.

---

## 🧰 Components Required

| S.No | Component | Quantity | Purpose |
|------|-----------|----------|---------|
| 1 | ESP32-CAM (AI Thinker) | 1 | Capture images + run inference |
| 2 | USB to Serial Converter | 1 | Program the ESP32-CAM |
| 3 | LEDs | 4 | Indicate detected currency |
| 4 | 100 Ω Resistors | 4 | Current limiting for LEDs |
| 5 | Breadboard | 1 | Prototype connections |
| 6 | Jumper Wires | As required | Wiring |
| 7 | Arduino IDE | — | Upload code |
| 8 | Edge Impulse Studio | — | Train ML model |

---

## 🔌 Circuit Description

The ESP32-CAM communicates with a USB-to-Serial adapter for uploading code and serial debug output. LEDs are connected to GPIO pins through resistors. Each LED corresponds to a specific denomination, illuminating when that note is detected.

---

## ⚙️ System Workflow

1. **Image Acquisition**  
   The ESP32-CAM captures images of currency notes from its web interface.

2. **Dataset Preparation**  
   Images are labeled and uploaded to Edge Impulse Studio.

3. **Model Training**  
   Train an object detection model using Edge Impulse.

4. **Model Deployment**  
   Deploy the model as an Arduino library to the ESP32-CAM.

5. **Real-Time Detection**  
   The ESP32-CAM runs inference locally and indicates results via LEDs.

---

## 🧪 Getting Started

### Step 1: Install Required Libraries
- Install **EloquentEsp32cam** via Arduino Library Manager
- Add the **Edge Impulse Arduino library** generated after training

### Step 2: Collect Images
- Open: `Examples → EloquentEsp32cam → Collect_Images_for_EdgeImpulse`
- Enter Wi-Fi credentials
- Access the ESP32-CAM web interface
- Capture and label images

### Step 3: Train Model in Edge Impulse
- Upload images and assign labels
- Configure impulse (Image + Object Detection)
- Train and evaluate the model

### Step 4: Upload Inference Code
Add: #define CAMERA_MODEL_AI_THINKER


---
Upload the final sketch to the ESP32-CAM.

💵 Supported Currency Notes

₹10

₹20

₹50

₹500

Each denomination is mapped to a specific LED.

🧠 Applications

Assistive tech for the visually impaired

Automated currency sorting/counting

Embedded AI demos

Retail POS systems

🚀 Future Enhancements

Support for more denominations and coins

Fake currency detection

LCD/OLED display feedback

Voice output for announcements

Larger dataset for better accuracy

❓ FAQs

Q: Is internet required for detection?
A: No — inference runs locally on the ESP32-CAM.

Q: Can it detect fake currency notes?
A: Not currently — this can be added with model training.

Q: Which ESP32-CAM board is supported?
A: AI Thinker ESP32-CAM module

👨‍💻 Author

Developed as an AI on Edge embedded project using ESP32-CAM and Edge Impulse.
