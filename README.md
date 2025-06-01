# WeatherSphere Pro

## Overview
WeatherSphere Pro is a modern, interactive web application that provides real-time weather updates, 5-day forecasts, and hourly weather details for any city worldwide. Built with HTML, CSS, and JavaScript, it leverages the WeatherAPI to deliver accurate weather data with a visually appealing, dynamic interface. The application features a glassmorphism design, animated weather effects, and a responsive layout for an engaging user experience.

This project is containerized using Docker and includes a Jenkins pipeline for automated building, testing, and deployment to Docker Hub.

---

## Features
- **Real-Time Weather Data**: Displays current temperature, humidity, wind speed, visibility, air quality, and more.
- **5-Day Forecast**: Provides a detailed forecast for the next five days with key metrics like temperature, humidity, and precipitation chance.
- **Hourly Forecast**: Shows hourly weather updates for the current day.
- **Dynamic Weather Effects**: Animated backgrounds and effects (e.g., rain, clouds, meteors, and stars) that adapt to weather conditions and time of day (day/night mode).
- **Geolocation Support**: Automatically fetches weather data based on the user's current location.
- **Autocomplete Search**: Suggests city names as the user types for quick and accurate searches.
- **Responsive Design**: Optimized for both desktop and mobile devices with a clean, modern UI.
- **CI/CD Pipeline**: Automated build and deployment using Jenkins and Docker, ensuring seamless updates.

---

## Tech Stack
- **Frontend**: HTML, CSS, JavaScript
- **API**: [WeatherAPI](https://www.weatherapi.com/) for weather data
- **Fonts and Icons**: Google Fonts (Outfit), Font Awesome
- **Containerization**: Docker
- **CI/CD**: Jenkins
- **Web Server**: Nginx (used in Docker container)

---

## Prerequisites
To run this project locally or deploy it, you need:
- [Docker](https://www.docker.com/get-started) installed
- A [WeatherAPI](https://www.weatherapi.com/) account and API key
- [Jenkins](https://www.jenkins.io/) (optional, for CI/CD pipeline)
- [Git](https://git-scm.com/) for cloning the repository
- A Docker Hub account (for pushing images)

---

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/devnfo/weathersphere.git
cd weathersphere
```

### 2. Configure the API Key
1. Sign up at [WeatherAPI](https://www.weatherapi.com/) to obtain an API key.
2. Open `index.html` and replace the `API_KEY` placeholder in the `<script>` section with your actual WeatherAPI key:
   ```javascript
   const API_KEY = 'your_api_key_here';
   ```

### 3. Build and Run Locally with Docker
1. Build the Docker image:
   ```bash
   docker build -t weatherupdate .
   ```
2. Run the Docker container:
   ```bash
   docker run -d -p 8081:80 --name weatherupdate weatherupdate
   ```
3. Open your browser and navigate to `http://localhost:8081` to view the application.

### 4. (Optional) Set Up Jenkins for CI/CD
1. Install and configure Jenkins on your system.
2. Set up Docker Hub credentials in Jenkins:
   - Go to **Manage Jenkins > Manage Plugins** and install the **Docker** and **Credentials** plugins.
   - Add your Docker Hub credentials under **Manage Jenkins > Manage Credentials** with the ID `dockerhub-creds`.
3. Create a new pipeline job in Jenkins and use the provided `Jenkinsfile` to automate building, running, and pushing the Docker image to Docker Hub.
4. Update the `your_email@gmail.com` in the `Jenkinsfile` with your email address for build notifications.

### 5. Deploy to Docker Hub
The `Jenkinsfile` includes a stage to push the Docker image to Docker Hub. Ensure your Docker Hub username is correctly set in the `Jenkinsfile`:
```groovy
DOCKER_HUB_USER = "dev637"
```

---

## Usage
1. **Search for a City**:
   - Enter a city name in the search bar and click the **Search** button or select from the autocomplete suggestions.
2. **Use Current Location**:
   - Click the **My Location** button to fetch weather data based on your geolocation.
3. **View Weather Details**:
   - The main weather card displays current conditions, including temperature, humidity, wind speed, visibility, air quality, and more.
   - Scroll down to see the 5-day forecast and hourly weather updates.
4. **Dynamic Effects**:
   - The background and animations change based on the weather condition (e.g., rain, sunny, cloudy) and time of day (day/night).

---

## Project Structure
```
weathersphere/
├── index.html       # Main HTML file with embedded CSS and JavaScript
├── Dockerfile       # Docker configuration for building the image
├── Jenkinsfile      # Jenkins pipeline for CI/CD
└── README.md        # Project documentation
```

---

## Screenshots
*To be added: Include screenshots of the application in different weather conditions or on various devices.*

---

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes and commit (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments
- [WeatherAPI](https://www.weatherapi.com/) for providing the weather data.
- [Font Awesome](https://fontawesome.com/) for icons.
- [Google Fonts](https://fonts.google.com/) for the Outfit font.
- [Nginx](https://www.nginx.com/) for the lightweight web server.
- [Docker](https://www.docker.com/) for containerization.
- [Jenkins](https://www.jenkins.io/) for CI/CD automation.

---

## Contact
For questions or feedback, reach out to the project maintainer:
- GitHub: [devnfo](https://github.com/devnfo)
- Email: your_email@gmail.com (replace with your actual email)