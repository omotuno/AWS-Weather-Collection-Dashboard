# 🌤️ AWS Weather Dashboard ☔️ - 30 Days DevOps Challenge Day 1

## 📖 Table of Contents 📖
- [Project Overview](#project-overview)
- [Project Architecture Diagram](#project-architecture-diagram)
- [Project Structure](#project-structure)
- [Application Features](#application-features)
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Installation Process](#installation-process)
- [Application Usage](#application-usage)
- [Code Explanation](#code-explanation)
- [Common Issues and Solutions](#common-issues-and-solutions)
- [Potential Future Improvements](#potential-future-improvements)
- [License](#license)
- [Contact](#contact)

## 🌤️ Project Overview

This project is an interactive **Weather Dashboard** application designed to collect real-time weather data for multiple cities. It utilizes the **OpenWeather API** to retrieve weather information and stores it in an **AWS S3 bucket**. The weather data includes key metrics like temperature (°F), humidity, and weather conditions, and is timestamped for historical tracking.

The project also integrates **AWS QuickSight** to visualize the data for better decision-making and monitoring.

### Key Technologies:
- **Python** for scripting and automation
- **OpenWeather API** for fetching weather data
- **AWS S3** for data storage
- **AWS QuickSight** for data visualization

---

## 🏗️ Project Architecture Diagram

![Project Architecture](https://github.com/omotuno/AWS-Weather-Collection-Dashboard/blob/main/img/Archiecture%20Diagram.png)

### Architecture Breakdown:
1. **OpenWeather API**:
   - Provides real-time weather data for multiple cities.
   - The data includes temperature, humidity, and weather conditions.

2. **AWS S3**:
   - Stores the fetched weather data in a designated S3 bucket.
   - Allows for easy retrieval and historical data tracking.

3. **Python Application**:
   - Fetches weather data from the OpenWeather API.
   - Processes and stores the data in S3.
  
4. **AWS QuickSight**:
   - Used to visualize the weather data for better insights and decision-making.

5. **S3 Bucket**:
   - Weather data is stored in S3, and HTML reports can also be stored for visualization.
   - You can store images or other static content like weather icons in the same bucket.

---
- **src/weather_dashboard.py**: Contains the main application logic and `WeatherDashboard` class.
- **data/cities.json**: Holds a list of cities for which weather data is fetched.
- **.env**: Stores environment variables like API keys and AWS configurations.
- **requirements.txt**: Lists the Python dependencies required to run the project.

---

## Application Features

- Fetches real-time weather data for multiple cities
- Displays temperature (°F), humidity, and various weather conditions
- Automatically stores weather data in AWS S3 bucket
- Timestamps data for historical tracking
- Supports data visualization through **AWS QuickSight**
- Allows users to store and visualize images (e.g., weather icons) in S3

---

## Getting Started

### 🔖 Prerequisites
Make sure you have the following setup:

- Python 3.7 or higher
- An **OpenWeather API key** (sign up [here](https://openweathermap.org/))
- An **AWS account** with S3 access
- **AWS CLI** configured with proper permissions
- Basic knowledge of **Git** and **GitHub**

---

## 📘 Installation Process

### Clone the repository:

```bash
git clone https://github.com/YourUsername/aws-weather-dashboard.git
cd weather-dashboard
```

---
### Install dependencies:

``` 
pip install -r requirements.txt
```

---
### Set up environment variables:

### Create a .env file in the project root and add:
```
OPENWEATHER_API_KEY=your_openweather_api_key
AWS_BUCKET_NAME=your_s3_bucket_name
AWS_REGION=your_aws_region
AWS_ACCESS_KEY_ID=your_aws_access_key_id
AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key
AWS_DEFAULT_REGION=your_aws_default_region
```

---
Configure AWS CLI (if not done already):
```
aws configure
```
 Make sure your credentials are set in the ~/.aws/credentials file.


## 🔋 Application Usage

Once you have the project set up and your environment variables configured, you can start using the **Weather Dashboard**.

### Running the Weather Dashboard

1. **Navigate to the project directory:**

   Open your terminal and navigate to the `src` directory:

   ```bash
   cd src
   ```


2. **Run the Application Script:**

   Use the following command to run the weather_dashboard.py script, which will fetch weather data for the cities specified in your configuration:

   ```bash
   python weather_dashboard.py

3.	The application will fetch weather data for predefined cities, store it in your S3 bucket

# 🌤️ AWS Weather Dashboard ☔️ (30 Days DevOps Challenge)

## 📝 Code Explanation

### weather_dashboard.py

- **WeatherDashboard class**: 
    - Initializes the API key and AWS S3 client.
    - Manages S3 bucket creation.
    - Fetches weather data from the OpenWeather API.

- **fetch_weather method**: 
    - Fetches weather data asynchronously from the OpenWeather API.

- **save_to_s3 method**: 
    - Saves the fetched weather data to the configured S3 bucket with a timestamp.

---

## Common Issues and Solutions

### 1. AWS Credentials Not Found
**Issue**: AWS credentials are not recognized.  
**Solution**: Use `aws configure` to set up your AWS credentials and ensure they are stored in `~/.aws/credentials`.

### 2. S3 Bucket Permission Denied
**Issue**: IAM user doesn’t have permission to access S3.  
**Solution**: Attach the `AmazonS3FullAccess` policy to your IAM user to grant the required permissions.

### 3. Environment Variables Not Loading
**Issue**: The application can't access `.env` variables.  
**Solution**: Ensure that the `.env` file is placed in the project root directory and is properly formatted.

### 4. GitHub SSH Issues
**Issue**: Unable to push to GitHub due to SSH authentication failure.  
**Solution**: Follow the [GitHub SSH guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) to set up SSH keys and ensure proper authentication.

---

## Potential Future Improvements

- **Implement Graphical User Interface (GUI)** for a more interactive user experience.
- **Add historical data tracking and visualization** in AWS QuickSight.
- **Integrate more weather APIs** for a broader range of weather conditions.
- **Add user authentication** for personalized weather data tracking.
- **Create a web application** version with real-time weather updates.
- **Implement geolocation** to automatically detect user cities.
- **Add weather alerts** for customized notifications.

---

## 📝 License

This project is licensed under the MIT License.

---

## 📞 Contact

Feel free to contact me at [omotundejunior@gmail.com](mailto:omotundejunior@gmail.com).
