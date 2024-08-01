# Electron-IoT Project

This project includes predictive maintenance and productivity optimization models using machine learning. The project focuses on analyzing data from industrial machines to predict maintenance needs, optimize productivity, and enhance operational efficiency.

## Table of Contents
- [Project Overview](#project-overview)
- [Data Description](#data-description)
- [Setup Instructions](#setup-instructions)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Predictive Maintenance Model](#predictive-maintenance-model)
- [Productivity Optimization Model](#productivity-optimization-model)
- [Results and Evaluation](#results-and-evaluation)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
The goal of this project is to leverage machine learning techniques to improve the maintenance schedules and productivity of industrial machines. By analyzing machine operational data, we can predict maintenance needs, reduce downtime, and optimize machine usage.

## Data Description
The project uses two main datasets:
1. **Trend Data (`trend0.csv`)**: Contains various machine operation metrics over time.
    - Key columns: `ID`, `SMR`, `Calendar`, `Eng_Speed_Max`, `Blowby_Press_Max`, `LF_Exh_Temp_Max`, `TM_Oil_Temp_Max`, etc.
2. **Cycle Data (`pldcycn23.csv`)**: Captures operational cycles of the machine, including loading and transportation metrics.
    - Key columns: `ID`, `Calendar`, `Payload`, `Empty_Drv_Time`, `Loading_Stop_Time`, `Loaded_Drv_Time`, `Angle_Ave`, etc.

## Setup Instructions
To set up the project locally, follow these steps:

1. **Clone the Repository:**
    ```bash
    git clone https://github.com/samis922/Electron-IoT.git
    cd Electron-IoT
    ```

2. **Create Virtual Environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4. **Download Data:**
    - Place the `trend0.csv` and `pldcycn23.csv` files into the `data` directory.
## Data overview
Trend Data (trend0.csv):
The trend data contains various machine operation metrics over time. Here are the key columns:

ID: Unique identifier for each record.
SMR: Service Meter Reading, indicating the usage hours of the machine.
Calendar: Timestamp of the record.
Eng_Speed_Max / Eng_Speed_Ave: Maximum and average engine speed.
Blowby_Press_Max: Maximum blowby pressure.
LF_Exh_Temp_Max, LR_Exh_Temp_Max, RF_Exh_Temp_Max, RR_Exh_Temp_Max: Maximum exhaust temperatures for different parts.
TM_Oil_Temp_Max: Maximum transmission oil temperature.
Ambient_Temp_Max / Ambient_Temp_Ave / Ambient_Temp_Min: Maximum, average, and minimum ambient temperatures.
Atomos_Press_Ave: Average atmospheric pressure.
F_Brake_P_Max / R_Brake_P_Max: Maximum front and rear brake pressure.
Travel_Speed_Max: Maximum travel speed.
ECO_ON: Eco mode status.
Machine_Serial: Serial number of the machine.
Cycle Data (pldcycn23.csv):
The cycle data captures the operational cycles of the machine, including loading and transportation metrics. Key columns include:

ID: Unique identifier for each record.
Calendar: Timestamp of the record.
Payload: Weight of the material transported.
Empty_Drv_Time / Empty_Drv_Dist: Time and distance driven empty.
Empty_Stop_Time / Loading_Stop_Time / Loaded_Stop_Time: Stop times for various phases.
Loaded_Drv_Time / Loaded_Drv_Dist: Time and distance driven loaded.
Over_Load / Over_Speed: Indicators for overload and overspeed events.
Limit_Speed: Speed limit.
Truck_ID / Open_ID: Identifiers for the truck and operation.
Angle_Min / Angle_Ave / Angle_Max: Minimum, average, and maximum angles during operation.
Shift: Shift during which the operation took place.
Machine_Serial: Serial number of the machine.

## Data Preprocessing
Preprocessing steps include:
- Handling missing values.
- Converting data types.
- Normalizing or scaling relevant columns.
- Detailed preprocessing scripts can be found in the `scripts` directory.

## Exploratory Data Analysis (EDA)
EDA helps in understanding the data distribution, identifying patterns, and visualizing relationships. Key steps include:
- Descriptive statistics.
- Correlation analysis.
- Visualizations (histograms, heatmaps, etc.).
- EDA notebooks can be found in the `notebooks` directory.

## Predictive Maintenance Model
We used a Random Forest model to predict maintenance needs based on machine operation metrics.
- **Model Training:** Train-test split, model fitting.
- **Evaluation:** Mean Squared Error (MSE), R-squared (R²).


## Productivity Optimization Model
A Random Forest model was also used to predict and optimize cycle times.
- **Model Training:** Feature selection, train-test split, model fitting.
- **Evaluation:** Mean Squared Error (MSE), R-squared (R²).



## Results and Evaluation
- **Predictive Maintenance:** R² of 0.922 with Random Forest.
- **Productivity Optimization:** R² of 0.962 with Random Forest.
- Detailed results and visualizations can be found in the `notebooks` directory.

## Future Work
- **Feature Engineering:** Explore additional features and interaction terms.
- **Advanced Models:** Experiment with Gradient Boosting Machines, Deep Learning.
- **Real-time Analytics:** Implement real-time data processing and monitoring.
- **Process Optimization:** Apply simulation models for workflow improvements.

## Contributing
Contributions are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
