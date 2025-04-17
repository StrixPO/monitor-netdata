
# 📊 Netdata Monitoring via Docker

This project demonstrates real-time system monitoring using [Netdata](https://www.netdata.cloud/) — a free and open-source performance monitoring tool. Netdata provides in-depth insights into CPU, memory, disk I/O, and running Docker containers with beautiful real-time charts.

## 🛠 Tools Used
- Docker
- Netdata
- Host OS: Windows 11 with Docker backend

## 🚀 Setup Instructions

### 1. Run Netdata using Docker

```
docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE \
  -v netdataconfig:/etc/netdata \
  -v netdatalib:/var/lib/netdata \
  -v netdatacache:/var/cache/netdata \
  -v /etc/passwd:/host/etc/passwd:ro \
  -v /etc/group:/host/etc/group:ro \
  -v /proc:/host/proc:ro \
  -v /sys:/host/sys:ro \
  -v /etc/os-release:/host/etc/os-release:ro \
  netdata/netdata
```
2. Access the Dashboard
Open your browser and go to:
```
http://localhost:19999
```

4. Monitor Metrics
Netdata provides insights into:
🔋 CPU usage

🧠 RAM and swap

💽 Disk I/O

📦 Running Docker containers

⚠️ Alerts and thresholds


🧹 Cleanup
To stop and remove the container:
```
docker stop netdata
docker rm netdata
```
✅ Outcome
This task demonstrates lightweight system monitoring with no performance impact, and helps visualize real-time metrics for any DevOps pipeline or server.

📄 What I Learned
  - Running containerized monitoring tools

  - Exploring system-level insights without agents

  - Basics of infrastructure observability
