# 🏋️‍♂️ NLP Workout Tracker to Google Sheets

An automated fitness tracking application built in Python. This project utilizes **Natural Language Processing (NLP)** to allow users to log their daily activities using plain conversational sentences. The script calculates exact caloric burn based on custom physical metrics and updates a live Google Sheet tracking document securely.

## 🚀 Features
* **Natural Language Inputs:** Parses casual human sentences like *"I ran 5km and benched for 20 minutes"* into structured workout data.
* **Smart Calorie Calculation:** Connects to the Nutritionix API to calculate precise energy expenditure dynamically optimized by your gender, weight, height, and age.
* **Automated Data Logging:** Uses the Sheety API to instantly append calculated workout details (Date, Time, Activity, Duration, Calories, Sets) into a Google Sheet.
* **Secure API Protocol:** Implements **Bearer Token Authentication** and utilizes environment variables to protect sensitive API endpoints and developer keys.

## 🛠️ Built With
* **Python 3**
* **Nutritionix API** (Natural Language Exercise Engine)
* **Sheety API** (Google Sheets Object-Mapping Gateway)
* `requests` library (HTTP Communication Platform)
* `datetime` module (Internal System Timestamping)

## 📋 Setup & Installation

### 1. Prerequisites
Ensure you have the required Python packages installed:
```bash
pip install requests python-dotenv
```

### 2. Sheet Setup
1. Create a blank Google Sheet with the following headers in row 1: 
   `Date`, `Time`, `Exercise`, `Duration`, `Calories`, `Sets`
2. Connect your sheet to a project on the [Sheety Dashboard](https://sheety.co).
3. In your Sheety project settings under the **Authentication** tab, enable **Bearer Auth** and define a custom secret token.

### 3. Environment Variables Configuration
To run this project without exposing your private developer tokens publicly, create a file named `.env` in the root directory of your project:

```env
ENV_NIX_APP_ID=your_nutritionix_app_id_here
ENV_NIX_API_KEY=your_nutritionix_api_key_here
ENV_SHEETY_TOKEN=your_sheety_bearer_token_here
```

*⚠️ **Important Safety Note:** Ensure your `.env` file is listed inside your `.gitignore` configuration before staging or pushing code to GitHub!*

## 💻 How to Use
1. Run the Python application:
   ```bash
   python main.py
   ```
2. When prompted (`Tell me which exercise you did :`), type in your workout including explicit duration components (e.g., *"I swam for 45 minutes and did pushups for 5 minutes"*).
3. The script will output confirmation payloads from the API and instantly sync your tracking sheet.
