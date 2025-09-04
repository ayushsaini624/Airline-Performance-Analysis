# Airline Data Management and Analysis Using Power BI ✈️

## 📝 Project Overview

This project addresses the complexities of the airline industry by leveraging Power BI for effective data management and analysis. The primary goal is to analyze and visualize data from flight schedules, passenger details, and ticketing systems to derive actionable insights, ultimately improving operational efficiency and customer satisfaction.

---

## 📊 Final Dashboard

The final published dashboard provides a comprehensive overview of airline operations, featuring key metrics on passenger volume, booking statuses, and flight details.

*(**Note:** Replace the text below with a screenshot of your final dashboard from the Power BI Service.)*

`[Screenshot of the final, published dashboard]`

---

## ✨ Key Features

* **Data Cleaning & Transformation**: Utilized Power Query to clean and prepare data by removing duplicates, handling missing values, and ensuring correct column formatting.
* **Relational Data Modeling**: Built a robust data model with one-to-many relationships centered around the `FlightID` key to enable integrated analysis across different datasets.
* **DAX-Powered KPIs**: Developed key calculations using DAX to measure total passengers, count confirmed ticket bookings, and filter for top-performing flights.
* **Interactive Visualizations**: Created a suite of visuals including bar charts and tables, enhanced with slicers for airline and destination to allow for dynamic user interaction.
* **Row-Level Security (RLS)**: Implemented RLS to restrict data access, ensuring users associated with a specific airline (e.g., "Airline A") can only view their relevant data.
* **Automated Refresh**: Deployed the report to the Power BI Service and configured a daily scheduled refresh at 5 PM to ensure the dashboard always displays the most current data.

---

## 🛠️ Project Workflow

The project was executed following a structured, multi-stage process:

### 1. Data Preparation and Cleaning

* Data was imported from three Excel sources into the Power BI Power Query Editor.
* Duplicates were removed from primary key columns (`flightID`, `ticketID`, `passengerID`) to ensure data integrity.
* Standard data cleaning procedures were applied, including handling missing values and verifying correct data types for all columns.

### 2. Data Modeling

* In the Power BI Model View, relationships were established between the `Flight_Information` table and the `Passenger_Information` and `Ticket_Information` tables using `FlightID` as the shared key.
* The relationship cardinality was confirmed as one-to-many, with `Flight_Information` serving as the central "one" table.

### 3. Enhanced Data Insights (Feature Engineering)

* A conditional column named `Flight Category` was created in Power Query to classify flights. Flights with a status of "On Time" were categorized as "Best"; all others were marked as "To Be Improved".
* The "Column from Examples" feature was used to extract a numerical `Flight Number Code` from the existing flight number text.

### 4. Calculations Using DAX

Key analytical calculations were created using DAX:
* A measure to calculate the total number of passengers:
    ```dax
    Number of passengers = COUNT(passenger_information[PassengerID])
    ```
* A measure to count only confirmed ticket bookings:
    ```dax
    Total Tickets Booked = COUNTROWS(FILTER(Ticket_Information, Ticket_Information[BookingStatus] = "Confirmed"))
    ```
* A new calculated table to isolate all data for "Best" flights:
    ```dax
    BestFlights = FILTER(Flight_Information, Flight_Information[Flight Category] = "Best")
    ```

### 5. Visualization and Interactive Features

* An interactive dashboard was built with several key visuals:
    * A bar chart showing the total **Passenger Count by Airline**.
    * A bar chart displaying the distribution of **Ticket Booking Statuses**.
    * A table visual detailing **Flights by Airline and Destination**.
* **Slicers** for `Destination` and `Airline` were added to allow users to filter the report dynamically.

### 6. Final Dashboard and Power BI Service

* The completed report was published to the Power BI Service.
* **Row-Level Security (RLS)** was configured by creating a role named "Airline A" and assigning it to a user in the service.
* A **Scheduled Refresh** was set up to run daily at 5 PM, ensuring the report data remains current.

---

## 💾 Data Sources

The analysis is based on the following datasets:
* `Flight_Information.csv`
* `Passenger_Information.csv`
* `Ticket_Information.csv`

---

## 🔧 Tools Used

* **Microsoft Power BI Desktop**
* **Power Query (M Language)**
* **DAX (Data Analysis Expressions)**
* **Power BI Service**
