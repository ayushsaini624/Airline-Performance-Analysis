# Airline Data Management and Analysis Using Power BI ✈️

## 📝 Project Overview

[cite_start]This project addresses the complexities of the airline industry by leveraging Power BI for effective data management and analysis[cite: 811]. [cite_start]The primary goal is to analyze and visualize data from flight schedules, passenger details, and ticketing systems to derive actionable insights, ultimately improving operational efficiency and customer satisfaction[cite: 811, 812].

---

## 📊 Final Dashboard

[cite_start]The final published dashboard provides a comprehensive overview of airline operations, featuring key metrics on passenger volume, booking statuses, and flight details[cite: 682, 683, 684, 687].

*(**Note:** Replace the text below with a screenshot of your final dashboard from the Power BI Service.)*

`[Screenshot of the final, published dashboard]`

---

## ✨ Key Features

* [cite_start]**Data Cleaning & Transformation**: Utilized Power Query to clean and prepare data by removing duplicates, handling missing values, and ensuring correct column formatting[cite: 5, 6, 11, 14].
* [cite_start]**Relational Data Modeling**: Built a robust data model with one-to-many relationships centered around the `FlightID` key to enable integrated analysis across different datasets[cite: 109, 112, 114, 116].
* [cite_start]**DAX-Powered KPIs**: Developed key calculations using DAX to measure total passengers, count confirmed ticket bookings, and filter for top-performing flights[cite: 184, 193, 257, 343].
* [cite_start]**Interactive Visualizations**: Created a suite of visuals including bar charts and tables, enhanced with slicers for airline and destination to allow for dynamic user interaction[cite: 395, 396, 430, 459, 491].
* [cite_start]**Row-Level Security (RLS)**: Implemented RLS to restrict data access, ensuring users associated with a specific airline (e.g., "Airline A") can only view their relevant data[cite: 688, 690].
* [cite_start]**Automated Refresh**: Deployed the report to the Power BI Service and configured a daily scheduled refresh at 5 PM to ensure the dashboard always displays the most current data[cite: 692, 788, 790, 791].

---

## 🛠️ Project Workflow

The project was executed following a structured, multi-stage process:

### 1. Data Preparation and Cleaning

* [cite_start]Data was imported from three Excel sources into the Power BI Power Query Editor[cite: 4, 5].
* [cite_start]Duplicates were removed from primary key columns (`flightID`, `ticketID`, `passengerID`) to ensure data integrity[cite: 6, 8, 9].
* [cite_start]Standard data cleaning procedures were applied, including handling missing values and verifying correct data types for all columns[cite: 11, 14].

### 2. Data Modeling

* [cite_start]In the Power BI Model View, relationships were established between the `Flight_Information` table and the `Passenger_Information` and `Ticket_Information` tables using `FlightID` as the shared key[cite: 108, 112, 113, 114].
* [cite_start]The relationship cardinality was confirmed as one-to-many, with `Flight_Information` serving as the central "one" table[cite: 116, 121].

### 3. Enhanced Data Insights (Feature Engineering)

* [cite_start]A conditional column named `Flight Category` was created in Power Query to classify flights[cite: 136, 137]. [cite_start]Flights with a status of "On Time" were categorized as "Best"; all others were marked as "To Be Improved"[cite: 138, 141].
* [cite_start]The "Column from Examples" feature was used to extract a numerical `Flight Number Code` from the existing flight number text[cite: 153, 154, 156].

### 4. Calculations Using DAX

Key analytical calculations were created using DAX:
* [cite_start]A measure to calculate the total number of passengers[cite: 193]:
    ```dax
    Number of passengers = COUNT(passenger_information[PassengerID])
    ```
* [cite_start]A measure to count only confirmed ticket bookings[cite: 257]:
    ```dax
    Total Tickets Booked = COUNTROWS(FILTER(Ticket_Information, Ticket_Information[BookingStatus] = "Confirmed"))
    ```
* [cite_start]A new calculated table to isolate all data for "Best" flights[cite: 332, 343]:
    ```dax
    BestFlights = FILTER(Flight_Information, Flight_Information[Flight Category] = "Best")
    ```

### 5. Visualization and Interactive Features

* [cite_start]An interactive dashboard was built with several key visuals[cite: 395]:
    * [cite_start]A bar chart showing the total **Passenger Count by Airline**[cite: 396].
    * [cite_start]A bar chart displaying the distribution of **Ticket Booking Statuses**[cite: 430].
    * [cite_start]A table visual detailing **Flights by Airline and Destination**[cite: 459].
* [cite_start]**Slicers** for `Destination` and `Airline` were added to allow users to filter the report dynamically[cite: 491].

### 6. Final Dashboard and Power BI Service

* [cite_start]The completed report was published to the Power BI Service[cite: 681].
* [cite_start]**Row-Level Security (RLS)** was configured by creating a role named "Airline A" and assigning it to a user in the service[cite: 688, 690, 691].
* [cite_start]A **Scheduled Refresh** was set up to run daily at 5 PM, ensuring the report data remains current[cite: 692, 788, 790, 791].

---

## 💾 Data Sources

[cite_start]The analysis is based on the following datasets[cite: 813, 814, 815]:
* `Flight_Information.csv`
* `Passenger_Information.csv`
* `Ticket_Information.csv`

---

## 🔧 Tools Used

* **Microsoft Power BI Desktop**
* **Power Query (M Language)**
* **DAX (Data Analysis Expressions)**
* **Power BI Service**
