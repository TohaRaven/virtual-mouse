# 🖱️ Virtual Mouse using Hand Gestures

## 🔍 Project Overview

This project turns your **hand into a virtual mouse** using a webcam. By detecting your hand in real time, it tracks your **index finger and thumb**, allowing you to control the system mouse cursor. When your **thumb and index finger touch**, it simulates a **mouse click**.

---

## 🧠 Libraries Used

* **OpenCV (****`cv2`****)**: For real-time webcam access and image processing.
* **MediaPipe**: For detecting and tracking hand landmarks.
* **PyAutoGUI**: To move the mouse and simulate clicks.

---

## 🧩 How It Works

### 1. **Initialization**

* The webcam is activated.
* MediaPipe's Hand Detection module is initialized.
* The screen resolution is captured for mouse coordinate mapping.

### 2. **Real-time Frame Capture**

* Each frame is read and flipped horizontally to mimic a mirror.

### 3. **Hand Detection**

* The frame is converted from BGR to RGB.
* MediaPipe processes the frame to detect hand landmarks.

### 4. **Index Finger Tracking (Landmark ID 8)**

* Detects the index finger tip.
* Draws a circle on the tip.
* Maps the webcam coordinate to screen resolution for mouse movement.

### 5. **Thumb Tracking (Landmark ID 4)**

* Detects the thumb tip.
* Draws a circle.
* Also mapped to screen space.

### 6. **Gesture Recognition & Action**

* If the index finger and thumb are close (< 20 pixels apart vertically):

  * Perform a left mouse click.
  * Wait 1 second to avoid rapid clicking.
* If not too close but within a range (< 100 pixels):

  * Move the mouse cursor to the index finger position.

### 7. **Display**

* Shows the processed webcam frame with hand landmarks drawn.

---

## 💡 Key Concepts

* **Hand Landmark Detection**: 21 hand points detected by MediaPipe.
* **Gesture Detection**: Calculating distances between landmarks.
* **Screen Mapping**: Webcam frame coordinates scaled to screen dimensions.
* **Mouse Control**: Done using PyAutoGUI.

---

## ✅ Output

* Live webcam feed with visual hand tracking.
* Cursor movement with index finger.
* Click simulation when thumb touches index finger.

---

## 📦 Use Case Ideas

* Contactless computer control.
* Accessibility tool for users with limited mobility.
* Gaming, AR/VR, and smart TV interfaces.
* Educational gesture-based applications.

---

## 🔧 Future Improvements

* Add scrolling with two fingers.
* Detect and support multiple gestures.
* Smoother hand tracking with movement filtering.
* Enhance click accuracy using time-based checks.

---

## 🧠 Author

Developed by **Mustanzid Ashraf Toha**, an aspiring AI & Robotics engineer with a passion for creative tech.
