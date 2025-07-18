# Motion Detector with Email Alerts

A Python-based motion detector that uses **OpenCV** to scan your webcam feed for motion. If movement is detected, the system captures an image and sends an email alert with the snapshot attached. Background threads handle email sending and image cleanup for smooth, real-time operation.

---

## Features

- Real-time motion detection via your webcam
- Captures and saves images on motion events
- Automatic email alerts with attached images
- Cleans saved images regularly to conserve space
- Threaded operation for simultaneous image capture, email, and cleanup

---

## Tech Stack

- Python 3.x
- OpenCV (`cv2`)
- Email (Python `smtplib`, `email.message`)
- Threading (`threading` module)

---

## Project Structure

```
.
├── main.py               # Main (threaded) motion detection & emailing
├── main2.py              # Simpler, non-threaded version
├── emailing.py           # Email sending logic (send_email function)
├── images/               # Stores captured images
├── docs/
│   └── setup.md          # Detailed setup/instructions
├── README.md             # Overview and usage guide
```

---

## How It Works

1. **Start**: `main.py` launches webcam capture.
2. **Frame Processing**: Each frame is converted to grayscale and blurred for better motion detection.
3. **Motion Detection**: If a significant moving contour is found, an image is captured and saved.
4. **Alert**: When motion stops, an email is sent with the most recent image.
5. **Cleanup**: Old images are automatically deleted in the background.

---

## Email Configuration

- **Sender Email:** `set an email`
- **Security:** Generate a Google *App Password* instead of your standard Gmail password.
- **Configuration:** Update the following variables in `emailing.py`:
    - `SENDER`
    - `RECEIVER`
    - `PASSWORD`

---

## Run the Project

In your terminal, execute:

```
python main.py
```

Alternatively, for the non-threaded version:

```
python main2.py
```

---

## Exit

Press **q** in the webcam window to stop the program safely and clean up the `images` folder.

---

*Happy Coding! If you have questions or feedback, check out the [docs](docs/setup.md) or reach out to the project maintainer.*
