# 📘 Smart EIIN Info API

A **Flask-based API service** that provides structured data about divisions, districts, thanas, institutes, employees, and teachers in Bangladesh.
It wraps and simplifies raw government APIs into clean JSON endpoints with caching, CSV export, and developer-friendly responses.

🌐 **Live Demo** → [smarteiin.vercel.app](https://smarteiin.vercel.app)

---

## 🚀 Features

* ✅ Get **Divisions, Districts & Thanas** info.
* ✅ Fetch **Institutes** by division, district, thana, or EIIN.
* ✅ Retrieve **Employees & Teachers** details of an institute.
* ✅ Built-in **Caching** for better performance.
* ✅ Support for **CSV export** of results.
* ✅ JSON responses with **Bangla & English names**.
* ✅ Friendly error handling and structured responses.

---

## 📡 API Endpoints

### 🔹 Health Check

```http
GET /
```

Returns `status.html` file.

---

### 🔹 Divisions

```http
GET /api/v1/divisions
```

---

### 🔹 Districts

```http
GET /api/v1/districts
```

---

### 🔹 Thanas

```http
GET /api/v1/thanas?district_code={district_code}
```

---

### 🔹 Institute Types

```http
GET /api/v1/institute-types
```

---

### 🔹 Institutes

```http
GET /api/v1/institutes?division_code=03&district_code=26&thana_code=308276&institute_type_id=11
```

Optional query params:

* `page` (default: 1)
* `size` (default: 10)
* `eiin_no`
* `is_govt` (true/false)
* `full_response` (true/false)
* `export_csv` (true/false)

---

### 🔹 Employees

```http
GET /api/v1/employees?eiin_no=XXXXX
```

---

### 🔹 Teachers

```http
GET /api/v1/teachers?eiin_no=XXXXX
```

---

## 📦 Installation

Clone the repo:

```bash
git clone https://github.com/abirxdhack/SmartEiinInfo.git
cd SmartEiinInfo
```

Create a virtual environment & install dependencies:

```bash
python3 -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

pip install -r requirements.txt
```

Run the server:

```bash
python app.py
```

Server will start at:

```
http://0.0.0.0:5000
```

---

## 📊 Example Response

**Request:**

```http
GET /api/v1/divisions
```

**Response:**

```json
{
  "status": "success",
  "data": {
    "Barisal": "01",
    "Chittagong": "02",
    "Dhaka": "03",
    "Khulna": "04",
    "Rajshahi": "05",
    "Rangpur": "06",
    "Sylhet": "07",
    "Mymensingh": "08"
  },
  "api_owner": "@ISmartCoder",
  "api_dev": "t.me/TheSmartDev"
}
```

---

## ⚡ Deployment

This project is live at → **[smarteiin.vercel.app](https://smarteiin.vercel.app)**
You can deploy your own copy on **Vercel / Heroku / Render**.

---

## 🛠 Tech Stack

* **Flask** (Python) – API framework
* **Requests** – External API calls
* **Cachetools (TTLCache)** – Response caching
* **Brotli & Gzip** – Data decompression
* **CSV & JSON** – Data export

---

## 📜 License

This project is for educational and open-source use.
API data is fetched from government public APIs.

---

## 👨‍💻 Author

**ISmartCoder**

* Telegram Dev: [t.me/TheSmartDev](https://t.me/TheSmartDev)
* API Owner: `@ISmartCoder`

---
