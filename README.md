# 📞 Voice Appointment Scheduler (Twilio + Flask + Google Sheets)

This project allows users to **schedule appointments using a voice call**. The user's voice is processed through Twilio, and the data (name, date, and phone number) is saved into a Google Sheet. The application is built with Flask and deployed on [Replit](https://replit.com/).

## 🛠 Technologies Used

- **[Twilio Programmable Voice](https://www.twilio.com/voice)** – to handle voice calls and speech recognition
- **[Flask](https://flask.palletsprojects.com/)** – lightweight Python web framework
- **[Google Sheets API](https://developers.google.com/sheets/api)** – to store appointment data
- **[gspread](https://gspread.readthedocs.io/)** – Python wrapper for the Google Sheets API
- **[Replit](https://replit.com/)** – online development and hosting environment

---

## 🔊 How It Works

1. A user calls the Twilio phone number connected to the app.
2. The bot greets the user and asks for their name.
3. Then, it asks for the desired appointment date/time.
4. Responses are captured using speech recognition.
5. The information is saved to a Google Sheet (with timestamp and caller number).
6. The user receives a voice confirmation.

---

## ⚙️ How to Run It

1. Create a project on Replit and upload the following files:
   - `main.py` – your Flask app
   - `credentials.json` – your Google service account credentials
2. Create a Google Sheet titled **"Rejestr Wizyt"** (you can rename it if needed).
3. Upload `credentials.json` to the Replit project.
4. Share your Google Sheet with the service account email (from the credentials file).
5. Click **Run** on Replit to start the server.
6. Copy your Replit public URL (e.g. `https://yourproject.repl.co`)
7. In the Twilio Console:
   - Go to **Phone Numbers > Your Number**
   - Under **Voice & Fax > A CALL COMES IN**, set the webhook URL to:
     ```
     https://yourproject.repl.co/voice
     ```
   - Set the method to **HTTP POST**

---

## 📂 Files in This Repository

- `main.py` – Flask application code
- `credentials.json` – Google service account credentials (do NOT share this publicly!)
- `README.md` – this file
- `replit.nix` or other Replit config files

---

## 📋 Sample Google Sheet Entry

| Timestamp           | Name         | Appointment Time     | Phone Number       |
|---------------------|--------------|-----------------------|---------------------|
| 2025-08-06 14:35:12 | John Smith   | Monday at 10:00 AM    | +48123456789       |

---

## 🔐 Security Notes

- Never expose `credentials.json` publicly
- Consider validating user input (e.g., check if the date is valid)
- You can extend the app with SMS confirmations, admin dashboard, etc.

---

## 🙏 Author & Thanks

This is an educational project using Twilio Voice and Google Sheets integration.  
Created by: Kacper Grzeszyk  
Thanks to **Twilio**, **Google**, and **Replit** for their excellent tools and APIs.

