# ⚡ CryptoStream Analytics: High-Performance Data Pipeline

<p align="center">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker Badge"/>
  <img src="https://img.shields.io/badge/Redpanda-FF2A2A?style=for-the-badge&logo=redpanda&logoColor=white" alt="Redpanda Badge"/>
  <img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white" alt="Rust Badge"/>
  <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js Badge"/>
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript Badge"/>
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React Badge"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python Badge"/>
</p>

## ⭐ Project Goal: Real-Time Data Intelligence

This project is a sophisticated, full-stack, real-time data streaming pipeline built for the YEBELO Technology technical assignment. It showcases the ability to rapidly learn and integrate an unfamiliar tech stack, building a robust system that streams, processes, and visualizes live cryptocurrency trading data. The final project name is **CryptoStream Analytics**.

---

## 🔗 Live Demo

Experience the live, high-speed data updates and charting on the deployed application:

**[https://redbucket-project-two.vercel.app/](https://redbucket-project-two.vercel.app/)**

Below is a demonstration of the final application, showing the real-time updates of both the Price and RSI charts on the dashboard.

> **Note:** To create a GIF for your repository, you can use a free tool like [Giphy Capture](https://giphy.com/apps/giphycapture) or [Kap](https://getkap.co/) to record your screen. Then, simply drag and drop the GIF file into the text editor when editing your `README.md` on GitHub.

---

## ✨ Key Features & Technical Highlights

| Feature | Technology | Benefit |
| :--- | :--- | :--- |
| **Microservice Architecture** | **Redpanda** (Kafka-compatible) | Decouples the ingestion, processing, and visualization layers for superior **scalability and resilience**. |
| **High-Performance Processing** | **Rust** (with Tokio) | Leverages Rust's speed to execute the complex, stateful 14-period **RSI calculation** with minimal latency. |
| **Live UI** | **Next.js** & **Socket.IO** | Achieves true real-time visualization by pushing data from the server directly to the client instantly. |
| **Containerized Setup** | **Docker Compose** | Ensures the entire multi-service stack runs flawlessly across any environment with a single command. |
| **Data Ingestion** | **Python** | Handles reading and serializing raw trade data before injecting it into the stream. |

---

## 🛠️ Technology Stack & Architecture

The data flows through the system in a decoupled, microservice-oriented architecture:
| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Containerization** | Docker, Docker Compose | Environment consistency and orchestration |
| **Streaming Broker** | Redpanda | Real-time message bus for streaming data |
| **Data Ingestion** | Python | Reads CSV and produces initial trade data |
| **Backend Processor** | Rust (with Tokio & rdkafka) | Consumes trades, calculates RSI, produces results |
| **Frontend** | Next.js, TypeScript, React | Renders the user interface and charts |
| **UI Styling** | Tailwind CSS | For modern, responsive styling |
| **Charting** | Recharts | Renders interactive, real-time line charts |
| **Real-time UI** | Socket.IO | Pushes live data from server to client |

---

## 🚀 Getting Started

Follow these instructions to get the project running on your local machine.

### Prerequisites

- [Docker](https://www.docker.com/get-started/) & [Docker Compose](https://docs.docker.com/compose/install/)
- [Rust](https://www.rust-lang.org/tools/install) & Cargo
- [Node.js](https://nodejs.org/en/download/) (v18+) & npm
- [Python](https://www.python.org/downloads/) (v3.8+)

### ⚙️ How to Run

1.  **Clone the Repository:**
    ```bash
    git clone [[https://github.com/kandalabalaji/CryptoStream-Analytics.git](https://github.com/kandalabalaji/CryptoStream-Analytics.git)]
    cd CryptoStream-Analytics
    ```

2.  **Start the Infrastructure:**
    This command starts the Redpanda broker and the management console in the background.
    ```bash
    docker-compose up -d
    ```

3.  **Run the Data Ingestion Script:**
    This script seeds the `crypto-price` topic with data from the CSV.
    ```bash
    python3 ingest.py 
    ```
    *You can verify ingestion by visiting the Redpanda Console at `http://localhost:8080`.*

4.  **Run the Rust Backend:**
    In a **new terminal**, start the Rust service to begin processing the data.
    ```bash
    cd rust-processor
    cargo run
    ```
    *Leave this terminal running.*

5.  **Run the Frontend Application:**
    In **another new terminal**, start the Next.js frontend.
    ```bash
    cd frontend
    npm install
    npm run dev
    ```

6.  **View the Dashboard:**
    Open your web browser and navigate to **[http://localhost:3000](http://localhost:3000)**. The dashboard will connect and start displaying the live data.

---
