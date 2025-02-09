# 📊 Chama Data Engineering

## 🚀 Project Overview
This project is a task for a **Data Engineering** position at **Chama**, a modern company focused on app-driven services. Chama relies on data to optimize operations, improve user experience, and make informed business decisions. 

### 📌 **Objective**
The goal of this project is to process **event data** provided in a JSON file (`case.json`), transform it into structured tables, and export the results into three **CSV files**:  
- `CuratedOfferOptions.csv`
- `DynamicPriceOption.csv`
- `DynamicPriceRange.csv`

The project involves:
- **Parsing JSON data**
- **Extracting nested fields**
- **Transforming timestamps to the Brazilian timezone (UTC-3)**
- **Structuring data into relational tables**
- **Exporting cleaned data to CSV format**

---

## 📂 **Project Background**
Chama is a relatively new and modern company with an **iOS and Android app**. The company operates in the **fuel delivery industry**, leveraging data analytics to optimize its operations. The company’s business model is based on app-based transactions, real-time pricing algorithms, and partnerships with fuel providers. Data quality and structured insights drive its decision-making process, making data engineering a crucial component of the business.

Insights and recommendations are provided on the following key areas:
- **Category 1:** Data transformation and quality
- **Category 2:** Time zone handling and accuracy
- **Category 3:** JSON parsing efficiency
- **Category 4:** Structured data for business insights

The SQL queries used to inspect and clean the data for this analysis can be found here [link].
Targed SQL queries regarding various business questions can be found here [link].
An interactive Tableau dashboard used to report and explore sales trends can be found here [link].

---

## 🔧 **Project Structure**
```
📂 Chama-Data-Engineering
📝 case.json                  # Input JSON file
📝 process_data.py             # Python script to process data
📝 CuratedOfferOptions.csv      # Output CSV file 1
📝 DynamicPriceOption.csv       # Output CSV file 2
📝 DynamicPriceRange.csv        # Output CSV file 3
📝 README.md                    # Project documentation
```

---

## ⚙ **Setup & Execution**

### 1️⃣ **Install Dependencies**
Ensure you have Python installed. Then, install the required libraries:

```bash
pip install pandas pytz
```

### 2️⃣ **Run the Script**
Execute the Python script to process the JSON data:

```bash
python process_data.py
```

### 3️⃣ **Output Files**
After running the script, three CSV files will be generated in the project directory:

1. `CuratedOfferOptions.csv`
2. `DynamicPriceOption.csv`
3. `DynamicPriceRange.csv`

---

## 📈 **Executive Summary**
### **Overview of Findings**
1. **Event data transformation ensures structured insights** - Extracting and structuring JSON data improves business decision-making.
2. **Accurate timezone conversion is critical** - Converting UTC timestamps to the Brazilian time zone enhances usability.
3. **Efficient parsing reduces processing time** - Optimized JSON extraction improves computational performance.

[Visualization: Snapshot of structured event data trends]

---

## 🛠 **Implementation Details**
### **Extracting Nested JSON Fields**
The `Payload` column contains a **JSON string**, so we use `json.loads()` to extract relevant fields.

### **Timezone Conversion**
The `EnqueuedTimeUtc` field is converted from UTC to **Brazilian Standard Time (UTC-3)** using `pytz`:

```python
import pandas as pd
import pytz

# Convert UTC to Brazilian Time (UTC-3)
def convert_to_brazilian_time(timestamp):
    utc_time = pd.to_datetime(timestamp, utc=True)
    brazil_time = utc_time.dt.tz_convert("America/Sao_Paulo").dt.strftime("%d/%m/%Y")
    return brazil_time
```

---

## 📊 **Insights Deep Dive**
### **Category 1: Data Transformation & Quality**
- Efficiently structured event data reduces inconsistencies.
- Ensuring all numerical values are correctly formatted improves accuracy.

### **Category 2: Time Zone Handling**
- Converting UTC timestamps enhances usability for local business decisions.
- Ensuring time format consistency reduces reporting errors.

### **Category 3: JSON Parsing Efficiency**
- Optimized data extraction reduces processing time.
- Handling missing or malformed JSON prevents data loss.

### **Category 4: Structured Data for Business Insights**
- Well-structured tables facilitate better analytics.
- Ensuring unique identifiers maintains data integrity.

---

## 💡 **Recommendations**
- Implement robust data validation before transformation.
- Ensure timezone conversion is consistent across all events.
- Optimize JSON parsing to improve performance.
- Standardize CSV output formats to align with business intelligence tools.


