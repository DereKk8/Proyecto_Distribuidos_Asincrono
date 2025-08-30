
# Distributed Classroom Allocation System 🎓🏫
![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![ZeroMQ](https://img.shields.io/badge/zeromq-async-green)
![Status](https://img.shields.io/badge/status-done-green)

An **academic project built in Python with ZeroMQ** that implements a distributed system for the automatic assignment of classrooms and laboratories.  
The system simulates a real-world environment with multiple academic programs, intermediary faculties, and a central server (DTI), using **Request–Reply communication patterns** and concurrency support.  

---

## 🚀 Key Features

- **Automatic classroom/lab allocation** via a central server.  
- **Distributed architecture with ZeroMQ** (REQ–REP pattern, broker support, load balancing).  
- **Concurrent simulation** of requests with threads and configurable parameters.  
- **Planned fault tolerance and monitoring** (heartbeat, performance metrics, automatic recovery).  
- **Data persistence** in structured log files.  
- **Future extensibility**: graphical interface, advanced statistics, support for more classroom types.  

---

## 🏗️ System Architecture

The system is composed of three main modules:

1. **Academic Program (`programa_academico.py`)**  
   Client that generates requests and connects to faculties in a Round-Robin fashion.

2. **Faculty (`facultad.py`)**  
   Intermediary that validates program requests and forwards them to the DTI.

3. **DTI (`DTI_servidor.py`)**  
   Central server that manages the classroom database, processes allocations, and logs events.  

> 📌 Communication Flow:  
> Academic Program → Faculty → DTI → Faculty → Academic Program  

---

## ⚙️ Installation & Execution

### Requirements
- Python 3.8+  
- [ZeroMQ](https://zeromq.org/)  

Install dependencies:
```bash
pip install pyzmq
````

### Running the System

1. Start the central DTI server:

   ```bash
   python3 DTI_servidor.py
   ```
2. Start faculty servers:

   ```bash
   python3 facultad.py 1
   python3 facultad.py 2
   ```
3. Run the academic program:

   ```bash
   python3 programa_academico.py
   ```

### Simulation Mode

```bash
python3 programa_academico.py --simulacion A
python3 programa_academico.py --simulacion B
```

* **A**: concurrent requests from 5 faculties with base parameters.
* **B**: same as A, but with higher demand on resources.

---

## 📊 Core Functionalities

* **Classroom management** with `dataclasses` and dynamic states (available, assigned, mobile).
* **Structured requests/responses** in JSON.
* **Reset command** to clean logs and reset classrooms.
* **Robust error handling** for input validation, ZMQ communication, and data parsing.
* **Real-time statistics** on classroom usage, occupancy, and system throughput.

---

## 📚 Technical Notes

* Uses **`dataclasses`** and **enums** to model classrooms and states.
* **Structured logging** for traceability.
* Extensible architecture to support new allocation policies.

---

## 🤝 Contributions

This project was developed as an academic practice in **Asynchronous Distributed Systems**.
Contributions for new features (GUI, advanced metrics, reservations) are welcome.


✅ This is your **final English README**, ready to drop into the repo.  

Do you want me to now rework your **first repo (Ehrgeizig LogBook)** into a polished English README in `.md` format too so your pinned projects look consistent?
```
