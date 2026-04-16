# 📊 Prometheus-Grafana Monitoring System

---

## 🎯 Objective
To integrate Prometheus with Grafana for real-time monitoring and visualization of system performance metrics such as CPU, Memory, Disk usage, and service availability.

---

## 🛠️ Tools Used
- Docker
- Prometheus
- Grafana
- Node Exporter
- PromQL (Prometheus Query Language)

---

## ⚙️ Step-by-Step Implementation

---

### 🔹 Step 1: Install Docker
Download and install Docker Desktop from the official website and ensure it is running.

---

### 🔹 Step 2: Run Node Exporter then run grafana
Username: admin pass: admin123

---

## Query for CPU usage
100 - (avg by(instance)(rate(node_cpu_seconds_total{mode="idle"}[1m])) * 100)
## Query for memory panel
(1 - (node_memory_MemAvailable_bytes / node_memory_MemTotal_bytes)) * 100
## Query for disk usage
(1 - (node_filesystem_avail_bytes / node_filesystem_size_bytes)) * 100

Node Exporter is used to collect system-level metrics such as CPU, memory, and disk usage.

---

### In promql run up

```bash
docker run -d -p 9100:9100 prom/node-exporter
---

