# Weather Project

A full-stack weather dashboard that combines localized forecasts, interactive radar, and AI-assisted clothing recommendations. Search for a city to explore current forecast periods, detailed weather conditions, map-based radar data, and suggested attire tailored to the forecast.

## Features

- Search forecasts by city, including day and night temperatures, icons, wind conditions, and detailed forecast descriptions.
- View a city-centered interactive weather map and radar experience powered by the Windy API.
- Receive AI-generated weather summaries and clothing recommendations, displayed with dynamic outfit visuals.
- Responsive React interface with loading, empty-state, and API-error handling.

## Tech Stack

- **Frontend:** React, Vite, React Router, Tailwind CSS, JavaScript
- **Backend:** Java 11, Spring Boot, Maven, Jackson, REST APIs
- **AI / Infrastructure:** Python, Modal, vLLM, GPT-OSS
- **Integrations:** National Weather Service API, Windy API

## Project Structure

```
frontend/   # React + Vite client application
backend/    # Spring Boot weather API service
llm/        # Modal/vLLM configuration for the recommendation model
```

## Running Locally

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Create a `frontend/.env` file and supply your Windy API key:

```env
VITE_WINDY_API=your_windy_api_key
```

### Backend

```bash
cd backend
mvn spring-boot:run
```

The backend runs on `http://localhost:8080` by default. Start it before using the frontend.

### AI Recommendation Service

The `llm/weather_LLM.py` script defines the Modal deployment for the vLLM-powered recommendation service. Configure Modal and the required model access before deploying:

```bash
modal deploy llm/weather_LLM.py
```

## APIs

- [National Weather Service API](https://www.weather.gov/documentation/services-web-api)
- [Windy API](https://api.windy.com/)
