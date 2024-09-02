# Data Collection and Storage in SQL


## Project Overview

You are working as an analyst for Zuber, a new rideshare company launching in Chicago. Your task is to find patterns in the available data. You want to understand passenger preferences and the impact of external factors on rides.

By working with a database, you will analyze competitor data and test a hypothesis about the impact of weather on the frequency of rides.

## Data Description
 
A database containing information about taxi rides in Chicago:

- **neighborhoods table**: Data about the city’s neighborhoods
  - `name`: The name of the neighborhood
  - `neighborhood_id`: The neighborhood code

- **cabs table**: Data about the taxis
  - `cab_id`: The vehicle code
  - `vehicle_id`: The technical ID of the vehicle
  - `company_name`: The company that owns the vehicle

- **trips table**: Data about the rides
  - `trip_id`: The trip code
  - `cab_id`: The vehicle code operating the ride
  - `start_ts`: The date and time when the ride started (time rounded to the hour)
  - `end_ts`: The date and time when the ride ended (time rounded to the hour)
  - `duration_seconds`: The duration of the ride in seconds
  - `distance_miles`: The distance of the ride in miles
  - `pickup_location_id`: The code of the pickup neighborhood
  - `dropoff_location_id`: The code of the dropoff neighborhood

- **weather_records table**: Data about the weather
  - `record_id`: The weather record code
  - `ts`: The date and time of the record (time rounded to the hour)
  - `temperature`: The temperature at the time of the record
  - `description`: A brief description of the weather conditions, e.g., "light rain" or "scattered clouds"


## Instructions for Completing the Project

#### **Step 1: Analyze Chicago Weather Data**
Write code to analyze the weather data in Chicago for November 2017 from the following website:

[Chicago Weather Data - November 2017](https://practicum-content.s3.us-west-1.amazonaws.com/data-analyst-eng/moved_chicago_weather_2017.html)

#### **Step 2: Exploratory Data Analysis**

1. **Taxi Rides on November 15-16, 2017**:
   - Find the number of taxi rides for each taxi company on November 15-16, 2017. Name the resulting field `trips_amount` and display it along with the `company_name` field.
   - Sort the results by `trips_amount` in descending order.

2. **Taxi Rides for Companies with "Yellow" or "Blue" in Their Name**:
   - Find the number of rides for each taxi company whose name contains the words "Yellow" or "Blue" from November 1-7, 2017. Name the resulting field `trips_amount`.
   - Group the results by the `company_name` field.

3. **Popular Taxi Companies in November 2017**:
   - The most popular taxi companies in November 2017 were Flash Cab and Taxi Affiliation Services. Find the number of rides for these two companies and name the resulting variable `trips_amount`.
   - Group the rides from all other companies into the group "Other".
   - Group the data by taxi company names. Name the field with the taxi company names `company`.
   - Sort the results in descending order by `trips_amount`.

#### **Step 3: Hypothesis Testing - Ride Duration on Rainy Saturdays**

1. **Retrieve Neighborhood IDs**:
   - Retrieve the neighborhood IDs for O'Hare and Loop from the `neighborhoods` table.

2. **Weather Conditions Grouping**:
   - For each hour, retrieve the weather conditions from the `weather_records` table. Use a `CASE` statement to divide all hours into two groups: "Bad" if the `description` field contains the words "rain" or "storm," and "Good" for all others. Name the resulting field `weather_conditions`.
   - The final table should include two fields: date and time (`ts`) and `weather_conditions`.

3. **Retrieve Taxi Rides Data**:
   - Retrieve from the `trips` table all rides that started in the Loop (neighborhood_id: 50) and ended in O'Hare (neighborhood_id: 63) on a Saturday.
   - Get the weather conditions for each ride using the method applied in the previous task. Also, retrieve the duration of each ride.
   - Ignore rides for which weather data is not available.

#### **Step 4: Exploratory Data Analysis (Python)**

1. **Dataset Review**:
   - Besides the data retrieved in the previous tasks, you have been given two additional CSV files:
     - `project_sql_result_01.csv`: Contains the following fields:
       - `company_name`: The name of the taxi company
       - `trips_amount`: The number of rides for each taxi company on November 15-16, 2017
     - `project_sql_result_04.csv`: Contains the following fields:
       - `dropoff_location_name`: Chicago neighborhoods where the rides ended
       - `average_trips`: The average number of rides that ended in each neighborhood in November 2017

2. **Tasks**:
   - Import the files
   - Review the data they contain
   - Ensure the data types are correct
   - Identify the top 10 neighborhoods in terms of drop-offs
   - Create visualizations: taxi companies and number of rides, top 10 neighborhoods by number of drop-offs
   - Draw conclusions based on each visualization and explain the results

#### **Step 5: Hypothesis Testing (Python)**

1. **Dataset**:
   - `project_sql_result_07.csv`: Contains data about rides from the Loop to O'Hare International Airport. The table includes the following fields:
     - `start_ts`: The date and time of the pickup
     - `weather_conditions`: The weather conditions at the time the ride started
     - `duration_seconds`: The duration of the ride in seconds

2. **Hypothesis Testing**:
   - Test the hypothesis: "The average ride duration from the Loop to O'Hare International Airport changes on rainy Saturdays."
   - Set the significance level (alpha) by yourself.

3. **Explanation**:
   - Explain how you formulated the null and alternative hypotheses
   - Describe the criterion you used to test the hypotheses and why


## Libraries
- Pandas version: 1.4.4
- Matplotlib version: 3.7.1
- Numpy version: 1.23.5
- Seaborn version: 0.12.2
- Scipy version: 1.10.1

