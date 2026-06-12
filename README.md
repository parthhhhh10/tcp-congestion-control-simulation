# TCP Congestion Control Simulation
### TCP Tahoe vs TCP Reno — Python Simulation

**Subject:** Computer Communication Networks (CCN)  
**Branch:** Electronics and Telecommunication Engineering (TY)  
**University:** University of Mumbai

---

## Overview

This project simulates and compares two foundational TCP Congestion Control algorithms — **TCP Tahoe** and **TCP Reno** — using Python. The simulation models Congestion Window (CWND) behavior over multiple Round Trip Times (RTTs) and demonstrates how each algorithm responds to two types of network congestion events: **Timeout** and **Triple Duplicate ACKs**.

---

## Key Concepts

| Term | Description |
|------|-------------|
| **CWND** | Congestion Window — limits unacknowledged segments in flight |
| **ssthresh** | Slow Start Threshold — boundary between Slow Start and Congestion Avoidance |
| **RTT** | Round Trip Time — one send + ACK cycle |
| **Timeout** | No ACK received in time — severe congestion signal |
| **Triple Dup ACK** | Same ACK received 3× — mild congestion, packet lost but pipe still flowing |

---

## Algorithm Comparison

| Feature | TCP Tahoe | TCP Reno |
|---------|-----------|----------|
| Timeout response | CWND → 1 | CWND → 1 |
| Triple Dup ACK response | CWND → 1 (same as timeout) | Fast Recovery: CWND → ssthresh/2 |
| Recovery speed | Slow (full Slow Start) | Faster (skips Slow Start) |
| Introduced | 1988 | 1990 |

---

## Project Structure

```
tcp-congestion-control-simulation/
│
├── TCP_Congestion_Control_Simulation.ipynb   # Main simulation notebook
├── requirements.txt                           # Python dependencies
└── README.md
```

---

## Setup & Usage

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/tcp-congestion-control-simulation.git
cd tcp-congestion-control-simulation
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the notebook
```bash
jupyter notebook TCP_Congestion_Control_Simulation.ipynb
```

---

## Outputs

The notebook generates three visualizations:
- **Plot 1** — Individual CWND plots for Tahoe and Reno with loss event markers
- **Plot 2** — Overlay comparison with shaded area highlighting Reno's throughput advantage
- **Plot 3** — Phase highlighting (Slow Start vs Congestion Avoidance)
- **Comparison Table** — Side-by-side RTT-level CWND breakdown

---

## Dependencies

- Python 3.8+
- `matplotlib`
- `numpy`
- `pandas`

---

## Why This Project?

Unit 5.4 of the CCN syllabus covers Flow Control, Error Control, and Congestion Control theoretically, but none of the standard lab experiments simulate congestion control behavior. This project fills that gap with a clean, visual, Python-based simulation.
