# 📊 Monitoring Dashboard — Grafana & Prometheus

> A containerized monitoring stack using Prometheus, Node Exporter, and Grafana for real-time system metrics collection and visualization. Spin up a complete observability setup with a single command.

![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat&logo=grafana&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)

## 📋 Overview

Knowing what's happening inside your infrastructure is critical. This project sets up a complete monitoring stack that collects system-level metrics (CPU, memory, disk, network) using Node Exporter, stores and queries them with Prometheus, and visualizes everything through Grafana dashboards — all containerized with Docker Compose for easy, repeatable deployment.

## 🛠️ Tech Stack

- **Metrics Collection:** Prometheus
- **System Metrics Exporter:** Node Exporter
- **Visualization:** Grafana
- **Containerization:** Docker Compose

## 🧩 Architecture

Node Exporter (9100) ──► Prometheus (9090) ──► Grafana (3001)
collects system        scrapes & stores       visualizes
metrics                  metrics            dashboards

## 📁 Project Structure

monitoring-dashboard/
├── docker-compose.yml   # Orchestrates Prometheus, Node Exporter & Grafana
├── prometheus.yml       # Prometheus scrape configuration
└── README.md            # Project documentation

## 🚀 Quick Start

```bash
# Clone the repo
git clone https://github.com/isuruchathushka724-dev/monitoring-dashboard
cd monitoring-dashboard

# Start the monitoring stack
docker-compose up -d

# Stop the stack
docker-compose down
```

## 🌐 Access the Services

| Service       | URL                     | Notes                          |
| ------------- | ----------------------- | ------------------------------ |
| Grafana       | http://localhost:3001   | Login: `admin` / `admin123`    |
| Prometheus    | http://localhost:9090   | Query & target status          |
| Node Exporter | http://localhost:9100   | Raw system metrics             |

> ⚠️ **Note:** The Grafana credentials are default demo values. Change them via the `GF_SECURITY_ADMIN_*` environment variables before any production use.

## 📈 Scrape Targets

Prometheus is configured (`prometheus.yml`) to scrape metrics every **15s** from:

- **prometheus** — `localhost:9090` (self-monitoring)
- **node-exporter** — `node-exporter:9100` (host system metrics)

## ⚙️ Setting Up a Grafana Dashboard

1. Open Grafana at `http://localhost:3001` and log in
2. Add **Prometheus** as a data source → URL: `http://prometheus:9090`
3. Import a prebuilt dashboard (e.g. **Node Exporter Full**, dashboard ID `1860`)
4. View live CPU, memory, disk, and network metrics

## ✅ Best Practices Used

- Fully containerized stack — reproducible with one command
- Service dependencies managed via `depends_on`
- Node Exporter integrated for real host-level observability
- Configuration externalized in `prometheus.yml` for easy edits

## 👨‍💻 Author

**Isuru Chathushka** — Undergraduate @ Horizon Campus LK
🔗 [LinkedIn](https://www.linkedin.com/in/isuru-chathushka)
