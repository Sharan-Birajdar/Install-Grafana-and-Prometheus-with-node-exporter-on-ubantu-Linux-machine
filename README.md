# 🚀 Grafana + Prometheus with Node Exporter Setup on Linux machine (Beginner-Friendly Guide)

## 🌟 What is Grafana?

Grafana is an open-source visualization tool used to monitor and analyze metrics from multiple data sources such as Prometheus, Loki, MySQL, and more.

**Key Features:**

* 📊 Interactive dashboards
* 🔔 Alerting system
* ⚡ Real-time monitoring

---

## 🌟 What is Prometheus?

Prometheus is an open-source monitoring and alerting system designed for reliability and scalability.

**Key Features:**

* 📥 Collects metrics from configured targets
* 🗄️ Stores data as time-series
* 🔍 Powerful query language (PromQL)

---

## ✅ Prerequisites

* Ubuntu Linux (20.04 or later recommended) 🐧
* User with sudo privileges
* Active internet connection 🌐

---

# ⚡ Install Grafana on Ubuntu

### 1️⃣ Update system and install dependencies

```bash
sudo apt update
sudo apt install -y apt-transport-https software-properties-common wget
```

### 2️⃣ Add Grafana GPG key

```bash
sudo wget -q -O /usr/share/keyrings/grafana.key https://apt.grafana.com/gpg.key
```

### 3️⃣ Add Grafana repository

```bash
echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://apt.grafana.com stable main" | sudo tee /etc/apt/sources.list.d/grafana.list
```

### 4️⃣ Install Grafana

```bash
sudo apt update
sudo apt install grafana -y
```

### 5️⃣ Start and enable Grafana service

```bash
sudo systemctl daemon-reexec
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
```

### 6️⃣ Verify Grafana status

```bash
sudo systemctl status grafana-server
```

✅ Ensure it shows **active (running)**

---

# ⚡ Install Prometheus on Ubuntu

### 1️⃣ Update system packages

```bash
sudo apt update
sudo apt upgrade -y
```

### 2️⃣ Install Prometheus and Node Exporter

```bash
sudo apt install prometheus prometheus-node-exporter -y
```

### 3️⃣ Configure Prometheus (Optional)

```bash
sudo nano /etc/prometheus/prometheus.yml
```

➡️ Add scrape targets, jobs, and alert rules as needed.

---

### 4️⃣ Start and enable services

```bash
sudo systemctl enable --now prometheus prometheus-node-exporter
```

---

# 🌐 Access Web Interfaces

* **Grafana:** [http://localhost:3000](http://localhost:3000)
  Default login:

  * Username: `admin`
  * Password: `admin` (you’ll be prompted to change it)

* **Prometheus:** [http://localhost:9090](http://localhost:9090)

---

# 🎯 Verify Installation

```bash
systemctl status grafana-server
systemctl status prometheus
```

---

# 🔗 Connect Prometheus to Grafana

1. Open Grafana in your browser
2. Go to **Settings → Data Sources**
3. Click **Add Data Source**
4. Select **Prometheus**
5. Enter URL:

```
http://localhost:9090
```

6. Click **Save & Test**

---

# 🚀 Next Steps

* 📊 Build your first dashboard
* 📈 Import community dashboards
* 🔔 Configure alerts and notifications
* 🖥️ Monitor multiple servers using Node Exporter

---

# 💡 Why Use Grafana + Prometheus?

* 📊 Real-time insights
* ⚡ High performance and lightweight
* 🔥 Widely used in the industry
* 🎯 Essential tools for DevOps and SRE roles
