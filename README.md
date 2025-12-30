🔍 Project Overview

The ESP32-CAM captures images of Indian currency notes placed in front of the camera. These images are processed locally using a machine learning model trained on Edge Impulse. Once a currency denomination is recognized, the corresponding LED glows to indicate the detected note, and the result is printed on the Serial Monitor.

This project highlights the concept of AI on Edge, where machine learning inference runs directly on embedded hardware, enabling low latency, better privacy, and offline operation.

🧠 What is AI on Edge?

AI on Edge, also known as edge computing, refers to running artificial intelligence algorithms directly on embedded devices such as microcontrollers and microprocessors instead of sending data to cloud servers. This approach offers several advantages:

Low latency

Reduced bandwidth usage

Improved data privacy

Real-time decision making

Object recognition is one of the most important applications of AI on Edge, allowing devices to visually identify and classify objects such as currency notes.

🧰 Components Required
S.No	Component	Quantity	Purpose
1	ESP32-CAM (AI Thinker)	1	Captures images and runs ML inference
2	USB to Serial Converter	1	Used to program the ESP32-CAM
3	LEDs (Red, Green, Yellow, Blue)	4	Indicate detected currency
4	100 Ω Resistors	4	Current limiting for LEDs
5	Breadboard	1	Prototyping
6	Jumper Wires	As required	Connections
7	Arduino IDE	—	Code upload
8	Edge Impulse Studio	—	Dataset training & deployment
🔌 Circuit Description

The ESP32-CAM is connected to a USB-to-Serial converter for programming and serial communication. LEDs are connected to the GPIO pins through 100 Ω resistors. Each LED corresponds to a specific currency denomination and glows when that note is detected.

⚙️ System Workflow

Image Acquisition
Images of Indian currency notes are captured using the ESP32-CAM web interface.

Dataset Preparation
Images are labeled and organized using Edge Impulse Studio.

Model Training
An object detection model is trained using Edge Impulse.

Deployment
The trained model is deployed as an Arduino library and uploaded to the ESP32-CAM.

Real-Time Detection
The ESP32-CAM performs inference locally and indicates results using LEDs.

🧪 Getting Started
Step 1: Install Required Libraries

Install EloquentEsp32cam from Arduino Library Manager.

Install the Edge Impulse Arduino Library generated after deployment.

Step 2: Collect Images

Open the example:

Examples → EloquentEsp32cam → Collect_Images_for_EdgeImpulse


Configure Wi-Fi credentials (2.4 GHz only).

Access the ESP32-CAM web server and capture images.

Step 3: Train Model on Edge Impulse

Upload images to Edge Impulse

Label currency notes

Configure impulse (Image + Object Detection)

Train and evaluate the model

Step 4: Upload Final Code

Replace camera model with:

#define CAMERA_MODEL_AI_THINKER


Upload the inference sketch to ESP32-CAM

🧪 Supported Currency Notes

₹10

₹20

₹50

₹500

Each denomination is mapped to a specific LED.

📸 Best Practices for Accuracy

Use a plain white background

Maintain consistent lighting

Fix the camera at a stable angle

Capture at least 50 images per denomination

🧠 Applications

Assistive technology for visually impaired users

Retail and point-of-sale systems

Automated currency counters

Vending machines

Smart financial systems

🚀 Future Improvements

Support for more denominations and coins

Fake currency detection

LCD/OLED display integration

Audio output for voice announcements

Improved model accuracy with larger datasets

✅ Conclusion

This project demonstrates how embedded AI can be implemented efficiently using ESP32-CAM and Edge Impulse. By performing inference directly on the device, the system achieves real-time performance without cloud dependency. It serves as an excellent example of TinyML and AI on Edge in real-world applications.

❓ FAQs

Q: Is internet required for detection?
No. Internet is only required during dataset collection and model training.

Q: Can it detect fake currency?
Not currently. This can be added in future with additional training data.

Q: Which ESP32-CAM board is supported?
AI Thinker ESP32-CAM module.

👨‍💻 Author

Developed as an AI on Edge embedded systems project using ESP32-CAM and Edge Impulse.
