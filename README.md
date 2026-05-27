# 📊 Monitoring Dashboard — Grafana & Prometheus

A containerized monitoring stack using Grafana and 
Prometheus for real-time metrics visualization.

## 🛠️ Tech Stack
- **Metrics Collection:** Prometheus
- **Visualization:** Grafana
- **Containerization:** Docker Compose

## 📁 Project Structure
monitoring-dashboard/
├── docker-compose.yml    # Container orchestration
└── prometheus.yml        # Prometheus config

## 🚀 Quick Start
```bash
# Clone repo
git clone https://github.com/isuruchathushka724-dev/monitoring-dashboard
cd monitoring-dashboard

# Start stack
docker-compose up -d

# Access dashboards
# Grafana:    http://localhost:3000  (admin/admin)
# Prometheus: http://localhost:9090
```

## 📈 Architecture
Prometheus (scrape metrics)
↓
Grafana (visualize)

## 👨‍💻 Author
**Isuru Chathushka** | Undergraduate @ Horizon Campus LK  
[LinkedIn](https://www.linkedin.com/in/isuru-chathushka)
