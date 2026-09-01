# ☀️ Morning Buddy

Morning Buddy is an AI-powered personal productivity assistant that helps users start and plan their day using personalized weather updates, interest-based news, and AI-generated daily plans.

The application combines real-time information from external APIs with Google Gemini to provide useful and easy-to-understand daily insights.

---

## 🚀 Features

- ☀️ Daily motivational quotes and morning images
- 🌤️ Real-time weather information for any city
- 👕 Weather-based suggestions for clothing and things to carry
- 📰 News discovery based on user interests
- 📝 AI-generated summaries of news articles
- 📅 AI-powered smart daily planner
- 📍 City-based recommendations for places to visit
- 🎟️ Local event discovery
- 🌦️ Weather-aware activity recommendations
- 🗓️ Chronological day planning from morning to evening
- 🤖 Google Gemini-powered AI responses
- 🔎 Google Search grounding for current city information
- 🖥️ Interactive Streamlit interface

---

## 🛠️ Tech Stack

### Frontend / UI

- Streamlit

### Programming Language

- Python

### AI

- Google Gemini API
- Gemini 2.5 Flash
- Gemini 2.5 Flash Lite
- Google Search grounding

### APIs

- OpenWeather API
- NewsAPI

### Libraries

- `requests`
- `python-dotenv`
- `google-genai`
- `streamlit`

---

## 🏗️ Architecture

```text
                         👤 User
                           │
                           ▼
                  ┌─────────────────┐
                  │    Streamlit    │
                  │       UI        │
                  └────────┬────────┘
                           │
              ┌────────────┼────────────┐
              │            │            │
              ▼            ▼            ▼
         Weather        News        Smart Planner
              │            │            │
              ▼            ▼            ▼
       OpenWeather     NewsAPI      External Data
              │            │        + Google Search
              │            ▼            │
              │       Gemini AI          │
              │       Summarization      │
              │            │             │
              └────────────┼─────────────┘
                           │
                           ▼
                    Google Gemini
                           │
                           ▼
                  Personalized Output
                           │
                           ▼
                    Streamlit UI
```

---

## 🔄 How It Works

Morning Buddy works as a collection of AI-powered utilities inside a single Streamlit application.

### 1. Home

The home page displays a randomly selected motivational quote along with a morning image to provide a simple personalized start to the application.

### 2. Weather

The user enters a city name.

```text
User
  │
  │ City Name
  ▼
Streamlit
  │
  ▼
OpenWeather API
  │
  │ Weather JSON
  ▼
Gemini 2.5 Flash
  │
  ▼
Human-readable Weather Report
```

The application fetches weather information such as:

- Current temperature
- Feels-like temperature
- Weather condition
- Humidity
- Wind speed
- Sunrise
- Sunset

Gemini then converts the raw weather information into a conversational report and provides practical suggestions such as what to wear or carry.

---

### 3. News by Interest

The user enters an area of interest such as:

```text
Technology
Sports
Health
Business
```

The application fetches the latest articles using NewsAPI.

```text
User Interest
     │
     ▼
   NewsAPI
     │
     ▼
Latest Articles
     │
     ▼
Gemini 2.5 Flash
     │
     ▼
Concise Article Summaries
     │
     ▼
Streamlit UI
```

The application displays the latest articles along with:

- Article title
- Image
- Article link
- AI-generated summary

---

### 4. Smart Planner

The Smart Planner generates a personalized day itinerary for a city.

The planner combines:

- Weather forecast
- Recommended places to visit
- Local events
- User's available time
- AI-generated planning logic

```text
                 User
                  │
                  │ City
                  ▼
          ┌───────────────┐
          │ Smart Planner │
          └───────┬───────┘
                  │
        ┌─────────┼─────────┐
        │         │         │
        ▼         ▼         ▼
     Weather    Places    Events
     Forecast   to Visit  in City
        │         │         │
        └─────────┼─────────┘
                  │
                  ▼
           Gemini 2.5 Flash
                  │
                  ▼
        Personalized Day Plan
                  │
                  ▼
             Streamlit UI
```

The generated plan organizes activities chronologically:

```text
Morning
   ↓
Lunch
   ↓
Afternoon
   ↓
Evening
```

The planner also considers weather conditions when recommending indoor or outdoor activities and includes event links when available.

---

## ✨ Key Components

| Component | Purpose |
|---|---|
| Streamlit UI | Provides the interactive application interface |
| OpenWeather API | Fetches current weather information |
| NewsAPI | Fetches latest news articles |
| SerpAPI | Finds local events |
| Google Search Grounding | Provides current information for city planning |
| Gemini 2.5 Flash | Generates weather reports, summaries and daily plans |
| Gemini 2.5 Flash Lite | Used for forecast and place discovery |
| Python | Core application logic |

---

## 📁 Project Structure

```text
morning-buddy/
│
├── app.py
│   └── Streamlit application and UI navigation
│
├── applications.py
│   └── Weather, news, Gemini and smart planner functions
│
├── requirements.txt
│   └── Python dependencies
│
├── .gitignore
│
└── README.md
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd morning-buddy
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

### 3. Activate the Virtual Environment

#### Windows

```bash
venv\Scripts\activate
```

#### macOS / Linux

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 API Configuration

The application uses external APIs for weather, news, event discovery and AI functionality.

Create a `.env` file in the project root:

```env
GOOGLE_API_KEY=your_google_gemini_api_key
```

The application uses the Google Gemini API through the `google-genai` package.

> **Important:** API keys should never be committed to GitHub. Use environment variables or a secrets manager for all API credentials.

---

## ▶️ Running the Application

Run the Streamlit application using:

```bash
streamlit run app.py
```

The application will open in your browser.

---

## 🖥️ Application Pages

### 🏠 Home

Provides:

- Morning motivational quote
- Morning image
- Navigation to other features

### 🌤️ Get Weather of Your City

Enter a city to receive:

- Current weather
- Temperature
- Humidity
- Wind information
- Sunrise and sunset
- Weather-based recommendations

### 📰 News by Interest

Enter an interest to receive:

- Latest articles
- Article images
- Article links
- AI-generated summaries

### 📅 Smart Planner

Enter a city to generate a personalized day plan using:

- Weather conditions
- Recommended places
- Local events
- AI-generated scheduling

---

## 🧠 AI Integration

Google Gemini acts as the main intelligence layer of the application.

It is used for:

- Converting raw weather data into natural-language reports
- Generating practical weather recommendations
- Summarizing news articles
- Finding and formatting city information
- Generating personalized daily itineraries
- Choosing activities based on weather and available information

The Smart Planner also uses Gemini's tool capabilities to access external information such as Google Search and application-defined functions.

---

## 📊 Data Flow

```text
                 User Input
                     │
                     ▼
              Streamlit Interface
                     │
                     ▼
              Python Application
                     │
          ┌──────────┼──────────┐
          │          │          │
          ▼          ▼          ▼
      OpenWeather  NewsAPI   SerpAPI
          │          │          │
          └──────────┼──────────┘
                     │
                     ▼
                Gemini API
                     │
                     ▼
            Processed AI Output
                     │
                     ▼
              Streamlit UI
```

---

## 🔮 Future Improvements

- 🔐 Move all API keys to environment variables
- 🗂️ Add persistent user preferences
- 👤 Add user authentication
- 📍 Automatically detect user location
- ⏰ Allow users to specify exact available time windows
- 🧠 Improve personalization using user preferences
- 💾 Save generated daily plans
- 📱 Improve mobile responsiveness
- 🧪 Add automated testing
- ⚡ Add caching to reduce repeated API calls
- 🚀 Improve production deployment and security

---

## ⚠️ Limitations

- The quality of results depends on the availability and accuracy of external APIs.
- News availability depends on NewsAPI results.
- Local event information depends on third-party search results.
- AI-generated summaries and plans may occasionally contain inaccurate information.
- API rate limits may affect availability.
- The application currently does not persist user preferences or planning history.

---

## 📸 Screenshots

### Home

```markdown
![Morning Buddy Home](./screenshots/home.png)
```

### Weather

```markdown
![Weather](./screenshots/weather.png)
```

### News

```markdown
![News](./screenshots/news.png)
```

### Smart Planner

```markdown
![Smart Planner](./screenshots/planner.png)
```

Create a `screenshots` folder and add the corresponding images if you want these sections to appear on GitHub.

---

## 🎯 Use Cases

Morning Buddy can be used as a lightweight daily assistant for:

- 🌅 Starting the morning with motivation
- 🌤️ Checking weather before going outside
- 👕 Deciding what to wear or carry
- 📰 Catching up on news based on interests
- 📅 Planning a productive day
- 📍 Discovering places and events in a city
- 🗺️ Creating weather-aware daily itineraries

---

## 👩‍💻 Author

**Yashvi**

GitHub: `yashvi-arch`

---

## 📄 License

This project is intended for educational and personal use.
