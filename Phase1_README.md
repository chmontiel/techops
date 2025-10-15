# README – Phase 1 : Prometheus & Grafana Basics

## 📘 Overview
This phase documents how to **install, configure, and connect Prometheus and Grafana**, along with **Windows Exporter**, **Blackbox Exporter**, and **Alertmanager**.  
The goal is to establish a functioning local monitoring stack capable of collecting, visualizing, and alerting on system metrics.

---

## 🧩 Key Sections
1. **Installing Prometheus** – download, run, and verify `http://localhost:9090`  
2. **Installing Grafana** – install Windows MSI package, verify `http://localhost:3000`  
3. **Installing Windows Exporter** – add system-metrics scrape job (`localhost:9182`)  
4. **Installing Blackbox Exporter** – add endpoint probe job (`localhost:9115`)  
5. **Connecting Prometheus to Grafana** – add Prometheus as a data source  
6. **Setting up Alertmanager** – define routing and PromQL-based alert rules  
7. **Official Docs & Resources** – quick links to Prometheus, Grafana, YAML, and repo

---

## ⚙️ Configuration Files
- **prometheus.yml** – main scrape config and rule files  
- **alerts.yml** – PromQL alert definitions  
- **alertmanager.yml** – notification routing (e.g., email, Slack, Teams)  
- **blackbox.yml** – probe settings for HTTP/HTTPS/ICMP checks  

---

## ✅ How to Run
1. Start Prometheus  
   ```bash
   prometheus.exe
   ```
   → Visit `http://localhost:9090`  
2. Start Grafana  
   - Runs as a background service after installation (default port 3000)  
3. Start Windows Exporter and Blackbox Exporter (if not set as services)  
   ```bash
   windows_exporter.exe
   blackbox_exporter.exe
   ```
4. Confirm targets at `http://localhost:9090/targets`  
5. Connect Prometheus to Grafana → **Save & Test**  
6. Validate alerts via Alertmanager (`alertmanager.exe`)

---

## 🧠 Best Practices
- Always **restart Prometheus** after editing `prometheus.yml`.  
- Use dedicated folders for Prometheus, Grafana, and exporters.  
- Bookmark UI pages (`localhost:9090`, `localhost:3000`, `localhost:9115`).  
- Automate startup with simple batch scripts for each service.  
- Keep config files under version control (e.g., `/configs` directory in repo).

---

## 🧹 Improvements from Original
- Standardized headings and step formatting.  
- Removed repeated notes about restarting processes.  
- Corrected grammar and flow for readability.  
- Added example PromQL alert rule and YAML syntax tips.  
- Clarified port mappings and file paths.  

---

## 📂 Directory Structure (Recommended)
```
project-root/
├── prometheus/
│   ├── prometheus.yml
│   ├── alerts.yml
│   └── alertmanager.yml
├── windows_exporter/
├── blackbox_exporter/
├── grafana/
└── README.md
```

---

## 🔗 Resources
- **Prometheus Docs:** https://prometheus.io/docs  
- **Grafana Docs:** https://grafana.com/docs  
- **YAML Basics:** https://yaml.org  
- **Your Repo:** [grafana-prometheus-lab](#)
