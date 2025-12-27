# Face Detection using OpenCV

A real-time face detection tool that identifies human faces from your webcam feed using OpenCV’s Haar Cascade classifier.

---

## 🚀 What is this project?

This project is a simple yet powerful **real-time face detection system**. Using OpenCV’s pre-trained Haar Cascade model, it identifies faces in the webcam feed and highlights them with a bounding box.

### **Input:**

A live webcam feed captured frame-by-frame.

### **Process:**

1. The webcam frame is converted to grayscale for faster processing.
2. OpenCV’s Haar Cascade classifier scans the frame for face patterns.
3. For every detected face:

   * A bounding rectangle is drawn.
   * A “Face Detected” label is displayed.
4. The output is shown on a live preview window.
5. The feed keeps running until the user presses **Q**.

### **Output:**

A real-time window displaying the webcam feed with detected faces highlighted.

---

## 🛠️ Tech Stack

* **Programming Language:** Python
* **Computer Vision Library:** OpenCV
* **Haar Models:** OpenCV Haar Cascade XML files
* **Hardware:** Any built-in or external webcam

---

## 🏗️ Architecture

The webcam continuously streams frames into the program. Each frame is converted to grayscale and passed into the Haar Cascade model for detection. The model returns bounding box coordinates for detected faces. The program draws rectangles and labels on those coordinates and displays the updated frame back to the user. The loop continues until the user exits by pressing **Q**.

---

## 🌐 Key Links

OpenCV Haar Cascades: [https://github.com/opencv/opencv/tree/master/data/haarcascades](https://github.com/opencv/opencv/tree/master/data/haarcascades)

OpenCV Documentation: [https://docs.opencv.org](https://docs.opencv.org)

Python Downloads: [https://www.python.org](https://www.python.org)

---

## ⚡ Quickstart

### **Prerequisites**

* Python 3.13.7
* OpenCV installed

```bash
pip install opencv-python
```

### **Project Setup**

Clone the repository:

```bash
git clone https://github.com/your-username/face-detection-opencv.git
cd face-detection-opencv
```

Make sure the Haar Cascade file exists:

```
haarcascade_frontalface_default.xml
```

### **Run the Application**

```bash
python face_detection.py
```

The webcam window will open automatically.
Press **Q** to close and exit the program.

---

## 🔑 Haar Cascade File

This project uses the Haar Cascade model:

`haarcascade_frontalface_default.xml`

Download it from the official OpenCV GitHub if not included.
Place it in the same directory as your Python script.

---

## 🤖 How It Works: Detection Engine

The detection logic follows a simple but efficient computer vision pipeline:

### **1. Frame Capture**

```python
cap = cv2.VideoCapture(0)
```

Continuously reads frames from the webcam.

### **2. Preprocessing**

```python
gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
```

Grayscale conversion improves detection speed.

### **3. Face Detection**

```python
faces = face_cascade.detectMultiScale(gray, 1.1, 5)
```

* `1.1` → scale factor
* `5` → minimum neighbors

### **4. Drawing Bounding Boxes**

```python
cv2.rectangle(frame, (x,y), (x+w, y+h), (0,255,0), 3)
```

### **5. Displaying Result**

```python
cv2.imshow("Webcam face Detection", frame)
```

### **6. Exit on 'Q' Key**

```python
if cv2.waitKey(1) & 0xFF == ord('q'):
    break
```

### **7. Cleanup**

Releases camera and closes windows.

---

## 👥 Contributing

Contributions, feedback, and improvements are welcome!
Feel free to open an issue or submit a pull request.

---

## 📜 License

MIT License
You are free to use, modify, and distribute this project.
