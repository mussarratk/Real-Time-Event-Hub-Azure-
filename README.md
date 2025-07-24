# Real-Time-Event-Hub-Azure-

Here is a complete and well-structured **`README.md` file** for your **GitHub project** titled *Real-Time IoT Data Streaming and Visualization using Azure and Power BI*, including a project summary, setup steps, and visual overview:

---

````markdown
# 📡 Real-Time IoT Data Streaming and Visualization using Azure and Power BI

## 📝 Summary

This project demonstrates how to build a **real-time IoT analytics pipeline** using **Azure IoT Hub**, **Azure Stream Analytics**, and **Power BI**. Simulated sensor data from a virtual Raspberry Pi device is streamed to Azure, processed in real time, and visualized via live dashboards in Power BI.

It serves as a blueprint for **IoT-based monitoring systems** in industries like smart manufacturing, supply chain logistics, environmental tracking, and home automation.

---

## 🔧 Technologies Used

| Component              | Purpose                                     |
|------------------------|---------------------------------------------|
| Azure IoT Hub          | Ingests telemetry data from simulated device |
| Raspberry Pi Simulator | Generates real-time temperature and humidity data |
| Azure Stream Analytics | Transforms and routes streaming data        |
| Azure Blob Storage     | Stores processed data for future reference  |
| Power BI               | Visualizes streaming data in real time      |

---

## 📊 Dashboard Features

- Real-time monitoring of sensor telemetry (e.g., temperature, humidity)
- Trend analysis with rolling average lines
- Visual indicators for threshold breaches
- Time slicers for filtering data by timestamp
- Auto-refresh visuals with streaming dataset in Power BI Service

---

## 🛠️ Setup Instructions

### 1. Azure IoT Hub

- Create an IoT Hub via Azure portal.
- Register a new device (e.g., `raspi-simulator`).
- Copy connection string and use it in the Raspberry Pi simulator code.

### 2. Raspberry Pi Simulator

- Use Python or a Node.js simulator to send telemetry like:

```json
{
  "deviceId": "raspi-simulator",
  "temperature": 74.6,
  "humidity": 45.2,
  "timestamp": "2025-07-24T12:00:00Z"
}
````

* Connect the simulator to the IoT Hub using the device connection string.

### 3. Azure Stream Analytics

* Create a Stream Analytics Job.
* Set IoT Hub as **input**, Azure Blob Storage and Power BI as **outputs**.
* Define a SQL-like query such as:

```sql
SELECT
    deviceId,
    temperature,
    humidity,
    System.Timestamp AS eventTime
INTO
    [PowerBIOutput]
FROM
    [IoTHubInput]
```

* Start the job and verify data flow.

### 4. Power BI

* In Power BI Service:

  * Create a **streaming dataset** (API-based).
  * Add fields: `deviceId`, `temperature`, `humidity`, `eventTime`.
* Build visuals like:

  * Line chart for temperature over time
  * Card visual for latest temperature/humidity
  * Gauge for threshold alerts
* Pin visuals to a **dashboard** and enable auto-refresh.

---

## 🖼️ Sample Dashboard

> Add a screenshot here of your Power BI dashboard
> Example:
> ![Power BI Dashboard Screenshot](images/iot_dashboard_sample.png)

---

## 📦 Folder Structure

```bash
├── simulator/
│   └── raspi_simulator.py         # Code to simulate device
├── stream-analytics/
│   └── query.sql                  # Sample SQL query for stream job
├── dashboard/
│   └── dashboard.pbix             # (Optional) PBIX file if exported
├── images/
│   └── iot_dashboard_sample.png   # Dashboard screenshot
├── README.md
```

---

## 🚀 Key Learnings

* Set up and manage Azure IoT Hub and device simulation
* Build streaming pipelines with Azure Stream Analytics
* Create real-time dashboards with Power BI streaming datasets
* Understand practical IoT analytics architecture

---

## 💡 Use Cases

* Smart factory equipment monitoring
* Environmental sensor dashboards
* Smart home automation
* Vehicle/fleet tracking

---

## ✅ Future Enhancements

* Integrate with Azure Functions to trigger alerts (email/SMS)
* Add anomaly detection using Azure ML or custom Python
* Store historical data in Azure SQL for deep analytics
* Export Power BI reports to PDF or email subscriptions

---

## 📬 Contact

For questions or collaboration opportunities:
**\[Your Name]** – \[[mussarrat.khatoon@gmail.com](mailto:your.email@example.com)]
🔗 [LinkedIn](https://linkedin.com/in/your-profile) | 🔗 [Portfolio](https://yourportfolio.site)

```

---

```
