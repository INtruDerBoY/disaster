# Dizaal – Disaster Alerts

Android app that helps users monitor nearby disaster risks, view affected zones on a map, and quickly access emergency guidance.

## Features

- Live **flood risk alerts** using Open-Meteo flood data
- Nearby **earthquake data** using USGS earthquake feeds
- Interactive **Google Map** with disaster overlays and location search
- Alert details view with **copy**, **share**, and **open in maps**
- Built-in **emergency dial shortcuts** (police, ambulance, fire)
- Disaster-specific **safety tips**
- Periodic background earthquake checks with local notifications
- Optional Firebase Realtime Database write for new earthquake events
- Light/dark theme toggle

## Tech Stack

- Kotlin
- AndroidX + Material Components
- ViewPager2 + Fragments
- Retrofit + Gson + OkHttp
- Google Maps SDK + Fused Location Provider
- WorkManager
- Firebase Realtime Database (optional)

## Project Structure

- `/app/src/main/java/com/example/dizaal_disasteralerts/ui` – screens and navigation
- `/app/src/main/java/com/example/dizaal_disasteralerts/data` – models, network services, repositories
- `/app/src/main/java/com/example/dizaal_disasteralerts/viewmodel` – UI state/data loading
- `/app/src/main/java/com/example/dizaal_disasteralerts/worker` – periodic earthquake worker
- `/app/src/main/res` – layouts, drawables, strings, themes

## Setup

### Prerequisites

- Android Studio (latest stable)
- Android SDK configured
- Internet connection for map + disaster APIs

### Configuration

1. Clone the repository.
2. Open the project in Android Studio.
3. Configure Google Maps API key for `MAPS_API_KEY` (manifest placeholder).
4. (Optional) Replace `app/google-services.json` with your Firebase config if using your own project.
5. Sync Gradle and run the app on an emulator or physical device.

## Permissions Used

- `ACCESS_FINE_LOCATION` / `ACCESS_COARSE_LOCATION` – location-based alerts and map positioning
- `INTERNET` – API calls and map data
- `POST_NOTIFICATIONS` – earthquake alert notifications

## Data Sources

- Flood API: `https://flood-api.open-meteo.com/`
- Earthquake API: `https://earthquake.usgs.gov/`

## Notes

- Background earthquake polling is scheduled every 15 minutes with WorkManager.
- If location permission is denied, the app falls back to a default location for flood data.
