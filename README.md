# Power BI & Excel – Ride Demand Dashboard (OLA Style)

This project analyzes ride demand for an OLA-style ride sharing platform using **Excel** for data preparation and **Power BI** for interactive reporting.  
The dashboard answers key questions about **when** rides peak, **how** weather and seasons impact demand, and **how casual users differ from registered users**.

---

## 📊 Dashboard Preview

![Overall Ride Demand Overview](https://github.com/tajfareedsyed/powerbi-excel-ride-demand-dashboard/blob/main/Visuals/Screenshot%202025-11-25%20at%2016.34.56.png)



---

## 🎯 Objectives

- Clean and prepare raw ride data in **Excel**
- Build DAX measures and visuals in **Power BI**
- Understand ride demand across:
  - Months
  - Seasons
  - Weather conditions
  - Peak hours
  - User types (Casual vs Registered)
- Design a portfolio-ready dashboard for data analytics roles

---

## 🧩 Dataset


- **Source:** Practice/learning dataset (similar to bike/ride sharing data)
- **Format:** CSV / Excel
- **Example Columns:**
  - `ride_id`
  - `date`
  - `month`
  - `season`
  - `weather`
  - `hour`
  - `user_type` (Casual / Registered)
  - `total_rides`

### Excel Work

In Excel, the following steps were performed:

- Removed null / duplicate rows  
- Standardized date, month, and season values  
- Fixed inconsistent text values (e.g., “summer” vs “Summer”)  
- Created helper columns if needed (e.g., **Month Name**, **Hour Group**)

The cleaned file was then loaded into Power BI.

---

## 📌 Business Questions

The dashboard is designed to answer:

1. What is the **total number of rides** and **casual users**?
2. Which **weather conditions** generate the most rides?
3. What are the **top peak hours** during the day?
4. How does demand change **across seasons**?
5. How do **casual users** compare to **registered users** by rides?
6. How do **rides trend month by month**?

---

## 📈 Dashboard Features

### KPIs
- **Total Rides** (≈ 1M)
- **Total Casual Users** (≈ 267K)

### Filters
- **Month slicer** to dynamically filter all visuals.

### Visuals

- **Donut Chart – Total Rides by Weather**
  - Clear, Snow, Mist, Rain (counts + % share)

- **Column Chart – Top 5 Peak Hours**
  - Shows hours of the day with the highest ride volume.

- **Bar Chart – Total Rides by Seasons**
  - Spring, Summer, Fall, Winter.

- **Clustered Column Chart – Casual vs Registered Users**
  - Comparison of total rides by user type.

- **Line Chart – Total Rides by Month**
  - Trend of ride demand from January to December.

---

## 🛠️ Tools & Technologies

- **Excel**
  - Data cleaning & preprocessing
  - Basic exploration and validation

- **Power BI Desktop**
  - Data modelling
  - DAX measures
  - Visual design & interactivity

### Example DAX Measures

```DAX
Total Rides =
SUM('Rides'[total_rides])

Total Casual Users =
CALCULATE(
    SUM('Rides'[total_rides]),
    'Rides'[user_type] = "Casual"
)

Total Registered Users =
CALCULATE(
    SUM('Rides'[total_rides]),
    'Rides'[user_type] = "Registered"
)

