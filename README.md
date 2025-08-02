# 🔐 SIEM Dashboard - Security Information and Event Management

A powerful, real-time SIEM (Security Information and Event Management) Dashboard built with Django, Celery, Redis, and Chart.js to analyze, filter, and visualize security event logs.

> ⚠️ Designed as an open-source alternative to commercial tools like Splunk or ELK Stack.

---



## 🧠 Features

✅ Upload or stream live log files (syslog, auth.log, JSON)  
✅ Parse and extract relevant fields  
✅ Real-time display and visualization (IP, country, time, attack type)  
✅ Filter by:
- IP address
- Country
- Timestamp
- Attack type

✅ Alert system (Email/Telegram) on anomalies  
✅ Export flagged logs to PDF or CSV  
✅ Beautiful Chart.js-based graphs for visual analysis  
✅ Modular log parsers (e.g., syslog_parser, json_parser)

---

## 💻 Tech Stack

| Layer      | Technology                       |
|------------|----------------------------------|
| Frontend   | HTML, CSS, JavaScript, Chart.js, Bootstrap |
| Backend    | Django, Python                   |
| Async Task | Celery + Redis                   |
| Visualization | Chart.js                      |
| Storage    | SQLite / PostgreSQL              |
| Export     | WeasyPrint / ReportLab (PDF), CSV writer |

---

## 📁 Folder Structure

```
siem_dashboard/
├── core/                  ← Main Django app
│   ├── templates/core/    ← HTML Templates
│   ├── static/core/       ← CSS, JS, Charts
│   ├── parsers/           ← Custom log parsers
│   ├── filters.py         ← IP / Time / Country filtering
│   ├── tasks.py           ← Celery tasks
│   ├── views.py
│   └── models.py
│
├── siem_dashboard/        ← Settings & Celery Config
│   ├── settings.py
│   ├── celery.py
│   └── urls.py
│
├── logs/                  ← Uploaded logs
├── exports/               ← Generated reports
├── manage.py
└── requirements.txt
```

---

## 🚀 How to Run Locally

1. **Clone the Repository**
```bash
git clone https://github.com/yourusername/siem-dashboard.git
cd siem-dashboard
```

2. **Install Requirements**
```bash
pip install -r requirements.txt
```

3. **Run Redis Server**
```bash
redis-server
```

4. **Start Celery Worker**
```bash
celery -A siem_dashboard worker --loglevel=info
```

5. **Run Django Server**
```bash
python manage.py runserver
```

---

## 📤 Log Formats Supported

- Linux Syslogs (`/var/log/syslog`)
- Auth Logs (`/var/log/auth.log`)
- Custom JSON logs (via template)

---

## 📦 Exports

- PDF Report (with tables, charts, filters)
- CSV Export (for SIEM processing or offline analysis)

---

## ⚠️ Alerts

Configure `.env` file with your email or Telegram bot token to receive alerts on:

- Suspicious IPs
- Known attack signatures
- Time-based spikes

---

## 📈 Future Enhancements

- ML-based anomaly detection (using Isolation Forest / DBSCAN)
- Real-time WebSocket log stream
- Dark Mode UI
- Threat intelligence integration

---

## 📄 License

This project is licensed under the **MIT License** – use freely, contribute back 🔁

---

## 🙌 Acknowledgments

- [Django Project](https://www.djangoproject.com/)
- [Celery](https://docs.celeryq.dev/)
- [Chart.js](https://www.chartjs.org/)
- [Redis](https://redis.io/)

---

> Made with ❤️ by Prince Chaudhary  
> Let’s make cybersecurity open and accessible for all.