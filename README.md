# ⚡ EV Charging Management Portal

A sleek, modern, and mobile-friendly web portal to manage and track Electric Scooter battery charging. This project uses a serverless architecture—relying on **HTML/CSS/JS** hosted on GitHub Pages for the frontend, and **Google Sheets & Google Apps Script** for the backend database.

## ✨ Features

- **Modern UI/UX:** A clean, card-based interface with gradient elements, stylish boxed headings, and mobile-responsive design.
- **Dynamic Vehicle Images:** The scooter image automatically smoothly transitions when you select between `DESPRO` and `LIBERTY+`.
- **Live Clock Integration:** Automatically records the current date and time in a strict `DD/MM/YYYY HH:MM:SS` format.
- **Smart Mileage Calculation:** Automatically looks up your previous odometer reading for the selected vehicle and calculates the exact mileage driven since the last charge.
- **Big Data Results:** Displays a beautiful popup card showing the newly calculated mileage immediately after logging a charge.
- **Live History Tables:** Automatically fetches and displays side-by-side charging history for your vehicles directly from Google Sheets.
- **Serverless Backend:** Uses Google Sheets as a free, easily accessible database.

---

## 🛠️ Tech Stack

- **Frontend:** HTML5, CSS3, Vanilla JavaScript (Fetch API)
- **Backend:** Google Apps Script (`Code.gs`)
- **Database:** Google Sheets
- **Hosting:** GitHub Pages

---

## 🚀 Setup & Installation Guide

To get this project running, you need to set up both the Google Sheets Backend and the GitHub Frontend.

### Part 1: Backend Setup (Google Sheets)

1. Go to [Google Sheets](https://sheets.google.com/) and create a new blank spreadsheet.
2. Name the first sheet exactly: **`MY ELECTRI`**
3. In the top menu, click **Extensions > Apps Script**.
4. Delete any existing code and paste the provided `Code.gs` script.
5. Save the project.
6. **Deploy the Web App:**
   - Click the blue **Deploy** button at the top right, then select **New deployment**.
   - **Select type:** Click the gear icon ⚙️ and choose **Web app**.
   - **Description:** "EV Portal v1" (or anything you like).
   - **Execute as:** `Me` *(Important!)*
   - **Who has access:** `Anyone` *(Crucial! If you don't select 'Anyone', GitHub cannot send data to it).*
   - Click **Deploy**. (You may need to authorize your Google account).
7. **Copy the Web App URL** generated. You will need this for the HTML file.

*(Note: If you ever change the `Code.gs` file in the future, you MUST create a **New deployment**. Do not just save or update the existing one, or the changes won't take effect).*

### Part 2: Frontend Setup (GitHub)

1. Fork or clone this repository, or simply create a new repository on your GitHub.
2. Create an `index.html` file and paste the provided HTML code.
3. Open `index.html` and scroll down to the `<script>` section (around line 161).
4. Replace the placeholder URL with your actual Google Web App URL:
   ```javascript
   const GOOGLE_APP_URL = "https://script.google.com/macros/s/YOUR_SCRIPT_ID/exec";
