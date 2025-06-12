# Web-Automation

Sure! Here's a **complete, well-documented `README.md`** file with detailed explanations for each part of your Rambagh Golf Club automation project:

---

### ✅ `README.md`

```markdown
# 🏌️ Rambagh Golf Club Tee Time Automation

This project automates daily golf tee time bookings on the [Rambagh Golf Club Jaipur](https://rambaghgolfclubjaipur.com/) website. It uses **Selenium WebDriver** to interact with the site, and a **Python scheduler script** to run the automation every day at 3:00 PM IST.

---

## 📁 Project Files

```

rambagh web automate/
│
├── venv/                   # Python virtual environment
├── daily\_booking.py        # Main automation script
├── scheduler.py            # Scheduler to run the script daily at a specific time
├── requirements.txt        # Required Python packages

````

---

## 📌 Features

- Logs into the Rambagh Golf Club member account.
- Navigates to "Tee Booking" → "Member Booking".
- Opens the booking page for tomorrow's date.
- Selects 9-hole and hole 1.
- Finds the first available 4-slot group.
- Auto-fills additional player usernames.
- Auto-fills the visible CAPTCHA code (non-image).
- Submits the booking request.

---

## ⚙️ Setup Instructions

### 1. Clone or Download the Project

```bash
cd your-project-directory
````

### 2. Create and Activate Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate on Windows
venv\Scripts\activate
```

### 3. Install Required Packages

```bash
pip install -r requirements.txt
```

---

## 📜 Script Breakdown

### 🐍 `daily_booking.py`

This is the main Selenium script that performs the following steps:

1. Opens Chrome browser and navigates to the site.
2. Logs in using provided credentials (`username` and `password`).
3. Navigates through the "Tee Booking" → "Member Booking" menus.
4. Constructs the URL for tomorrow’s date.
5. Selects 9-hole and hole-1.
6. Iterates through the table to find the first available row with 4 checkboxes.
7. Clicks the "Booking" button next to the selected row.
8. Fills in player usernames.
9. Auto-fills the CAPTCHA value (if it's plain text).
10. Submits the form.

### 🕒 `scheduler.py`

This script schedules the above automation daily:

* Uses a simple time loop to check system time.
* Triggers `daily_booking.py` at 3:00 PM IST (set using local time).
* Uses `subprocess.run()` to execute the script.

> ⚠️ Important: Ensure your system's clock is set to IST or adjust the schedule time accordingly.

---

## 🧾 Example `requirements.txt`

```txt
selenium==4.19.0
schedule==1.2.1
```

You can generate this file by running:

```bash
pip freeze > requirements.txt
```

---

## ✅ How to Run

To start the automation scheduler:

```bash
python scheduler.py
```

Keep the terminal running. It will check every second and execute `daily_booking.py` at the scheduled time.

---

## 🧪 Testing

You can change the time in `scheduler.py` temporarily to the current time + 1 minute for quick testing:

```python
schedule.every().day.at("14:59").do(run_booking_script)
```

---

## 🐞 Troubleshooting

* **ModuleNotFoundError**: Run `pip install -r requirements.txt`.
* **Chrome not opening**: Ensure Chrome is installed and `chromedriver` matches your browser version.
* **CAPTCHA fails**: The current method works only for text-based CAPTCHA. For image-based CAPTCHA, you’ll need OCR or manual input.
* **Time mismatch**: Make sure your system time is correctly set to IST if you're scheduling for 3 PM IST.

---

## 📌 Improvements You Can Add

* Retry logic for booking failures
* Email/Telegram alert after booking
* Logging to file instead of console
* Headless browser (optional)

---

## 👤 Author

**Aditi**
Python Developer | Automation Enthusiast

---

## 📝 License

This project is for personal automation use and educational purposes only. Not affiliated with Rambagh Golf Club.

```

---

You can copy-paste the above content into a file named `README.md` and place it in your project directory.

Let me know if you'd like this file generated and saved directly, or want to add screenshots and badges for GitHub.
```
