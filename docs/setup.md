# 🛠️ Motion Detector with Email Alerts – Setup Instructions

Follow this guide to set up and run the Motion Detector with Email Alerts project on your system.

---

## 1. Prerequisites

- **Python 3.x** must be installed.

Check your Python version:

```
python --version
# or
python3 --version
```

---

## 2. Clone the Repository

```
git clone https://github.com/thesaireddy20/motion-detector-email.git
cd motion-detector-email
```

---

## 3. Create a Virtual Environment (Optional but Recommended)

```
python -m venv venv
source venv/bin/activate    # On Windows: venv\Scripts\activate
```

---

## 4. Install Required Packages

Install dependencies using pip:

```
pip install opencv-python
```

If you're using an SMTP client for sending emails:

```
pip install secure-smtplib
```

**Built-in Python 3 modules** (no installation required):

- imghdr
- email
- smtplib
- threading
- glob
- time
- os

---

## 5. Create Required Folders

Create a folder named `images` in the project root:

```
mkdir images
```

---

## 6. Configure Email

Open `emailing.py` and update these variables:

```
PASSWORD = "your_app_password"
SENDER = "your_email@gmail.com"
RECEIVER = "receiver_email@gmail.com"
```

> ⚠️ **Important:** Use a Gmail App Password rather than your actual Gmail password.

---

## 7. Run the Application

- Start motion detection with threaded emailing and image cleanup:

    ```
    python main.py
    ```

- Or run the simpler (non-threaded) version:

    ```
    python main2.py
    ```

---

## 8. Quit the Program

To exit, simply press **q** in the webcam preview window. This will release the webcam and clean the `images/` folder.

---

## ✅ You're All Set!

If everything is set up correctly, you'll receive an email alert with a captured image whenever new movement is detected and stops.

---

## 💡 Tips

- Ensure you're **connected to the internet** for email functionality.
- Test using **slow and distinct motions** for better contour detection.
- Adjust `cv2.contourArea` threshold in `main.py` to tune detection sensitivity.

---

## 📬 Contact

For queries or suggestions, github:  
**[thesaireddy20](https://github.com/thesaireddy20)**

---

Happy Coding! ✨
