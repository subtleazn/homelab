# 🎬 Nash Ang's Homelab Dashboard

![Homelab Badge](https://img.shields.io/badge/Infrastructure-Bare%20Metal-blue?style=for-the-badge&logo=linux)
![Docker Badge](https://img.shields.io/badge/Containerization-Docker-blue?style=for-the-badge&logo=docker)
![Cloudflare Badge](https://img.shields.io/badge/Network-Cloudflare%20Tunnel-orange?style=for-the-badge&logo=cloudflare)
![Status Badge](https://img.shields.io/website?url=https%3A%2F%2Fnash.is-a.dev%2Fhomelab&label=Dashboard&style=for-the-badge)

A centralized **Web App Launcher** for my self-hosted infrastructure. This static dashboard provides a unified entry point for media servers, automation stacks, and system monitoring tools running on my bare-metal server.

## 🚀 Live Demo
**[Access the Dashboard](https://nash.is-a.dev/homelab)**

---

## 🏗️ Architecture

This lab runs on a **Bare Metal** setup, utilizing **Docker** for service isolation and **Cloudflare Tunnels** for secure remote access without open ports.

* **Host:** PinoySeoul-320S (Linux Mint / Ubuntu)
* **Networking:** Cloudflare Tunnel (WAN) & Tailscale (Admin Access)
* **Storage:** Local HDD + Rclone Mounts
* **Frontend:** HTML5 + Tailwind CSS (Hosted via GitHub Pages)

## ✨ Key Features

* **⚡ Zero-Dependency Frontend:** Built with vanilla HTML/JS and Tailwind via CDN. No build steps required.
* **🔄 Hybrid Connectivity Toggle:**
    * **CLOUD Mode:** Routes traffic through Cloudflare Tunnels (public domain).
    * **LAN Mode:** Direct local IP access (`192.168.x.x`) for lower latency when at home.
* **📂 Categorized Layout:** Services organized by function (System, Video, Audio, Books, Downloads).
* **⛔ Passive Security:** The dashboard contains only links; no API keys, credentials, or sensitive configurations are stored in the repo.

---

## 🛠️ Hosted Services

### 🖥️ System & Automation
* **Home Assistant:** Smart home control hub.
* **Glances:** Real-time system resource monitoring.
* **CasaOS:** Visual interface for container management.
* **Syncthing:** Continuous file synchronization across devices.

### 🎬 Media & Streaming
* **Jellyfin:** The core media server for Movies and TV.
* **Navidrome:** Self-hosted music streaming.
* **Photoview:** AI-powered photo gallery.
* **NodeCast TV & Dispatcharr:** IPTV management.

### 🏴‍☠️ The *Arr Stack
* **Radarr / Sonarr:** Movie and TV show collection management.
* **Lidarr / Readarr:** Music and Book automation.
* **Prowlarr:** Indexer management.
* **Bazarr:** Subtitle automation.
* **qBittorrent:** Download client.

### 📚 Books & Manga
* **Kavita:** Digital library for comics and books.
* **Suwayomi:** Manga downloader.
* **Audiobookshelf:** Audiobook streaming server.

---

## 📦 Usage / Deployment

This dashboard is designed to be forked and customized.

1.  **Fork the Repository.**
2.  **Edit `index.html`:**
    * Update the `services` array in the `<script>` section with your own URLs and IPs.
3.  **Enable GitHub Pages:**
    * Go to **Settings** > **Pages**.
    * Select **Source**: `Deploy from a branch` (main).
4.  **Done:** Your dashboard is live.

```javascript
// Example Configuration in index.html
const services = [
    { 
        name: "My App", 
        icon: "fa-server", 
        desc: "Description", 
        external: "[https://app.mydomain.com](https://app.mydomain.com)", 
        internal: "[http://192.168.1.100:8080](http://192.168.1.100:8080)", 
        category: "SYSTEM" 
    },
];
