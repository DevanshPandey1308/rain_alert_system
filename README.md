# 🌧️ Rain Alert System (Python + OpenWeather + Twilio)

This project is a small automation script that checks the weather forecast for a given location and sends an SMS alert if there’s a chance of rain.

> “It’s about to rain… even the weather is crying. Take an umbrella before it cries on you.”  

Perfect for practising APIs, automation, and basic deployment.

---

## 🚀 Features

- Fetches 5-day / 3-hour forecast data from **OpenWeatherMap**
- Checks upcoming forecast slots for **rain conditions** (using weather condition codes)
- Sends an **SMS alert via Twilio** if rain is detected
- Easy to configure for any latitude/longitude and any phone number
- Can be scheduled on services like **PythonAnywhere** or cron to run automatically

---

## 🛠 Tech Stack

- **Language:** Python
- **APIs:** 
  - [OpenWeatherMap](https://openweathermap.org/api) – weather forecast
  - [Twilio](https://www.twilio.com/) – SMS sending
- **Libraries:**
  - `requests`
  - `twilio`

---

## 🧠 How It Works

1. Script calls the OpenWeatherMap **Forecast API** with:
   - Latitude & longitude of the target location  
   - API key
2. Parses the JSON response and loops over the next few forecast entries.
3. For each time slot, it checks the **weather condition code**:
   - If `id < 700` → considered rain / snow / drizzle → `will_rain = True`
4. If rain is expected:
   - Initializes the Twilio `Client`
   - Sends an SMS alert to the configured phone number

---

## 📂 Project Structure

```text
rain_alert_system/
├── main.py
├── README.md
├── requirements.txt
└── .gitignore
