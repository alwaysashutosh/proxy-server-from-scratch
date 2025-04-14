# 🧩 Simple Multithreaded HTTP Proxy Server in C

This project implements a lightweight **HTTP Proxy Server** written in C. It acts as an intermediary between clients and web servers by forwarding HTTP requests and relaying responses. Designed for educational purposes, it demonstrates core networking concepts, thread management, caching, and system-level programming.

---

## 🚀 Key Features

- **🔌 Socket Programming:** Utilizes TCP sockets for robust and reliable client-server communication.
- **🔁 Multithreading:** Supports multiple concurrent clients using **POSIX threads (`pthread`)**.
- **🔐 Semaphore-Based Synchronization:** Efficient thread coordination using `sem_wait()` and `sem_post()`, eliminating the need for `pthread_join()` or `pthread_exit()` and avoiding thread ID dependencies.
- **📦 LRU Cache:** Implements a Least Recently Used (LRU) caching mechanism to store server responses and speed up subsequent requests.
- **📡 Request/Response Handling:** Parses and forwards HTTP GET requests, then relays responses to clients with minimal latency.

---

## 🎯 Motivation

This project was created to better understand:

- How HTTP requests travel from a local machine to the internet.
- Handling multiple client requests concurrently using system threads.
- Concurrency control using locks and semaphores.
- Browser caching mechanisms and how they enhance web performance.

---

## 🔎 Why a Proxy Server?

A proxy server offers several advantages:

- **📈 Performance:** Reduces server load by caching and reusing responses.
- **🛡️ Access Control:** Can be configured to block or allow access to specific websites.
- **🕵️ Anonymity:** Hides client IP addresses, offering increased privacy.
- **🔐 Security:** Can be extended to encrypt traffic for protection against unauthorized interception.

---

## ⚙️ OS Components Used

| Component      | Description |
|----------------|-------------|
| **Threading**  | POSIX threads (`pthread`) to handle concurrent clients. |
| **Locks**      | Used to ensure safe access to shared resources. |
| **Semaphores** | Used for efficient thread synchronization without relying on thread IDs. |
| **Cache**      | LRU (Least Recently Used) algorithm to store and retrieve frequently accessed responses. |

---

## ⚠️ Limitations

- **🧩 Cache Fragmentation:** If a URL opens multiple connections (e.g., for different resources), each response is stored separately, potentially leading to partial data retrieval.
- **💾 Fixed Cache Size:** Large websites may exceed the predefined cache size and fail to store completely.
- **📑 Limited Request Support:** Currently supports only HTTP GET requests.

---

## 📈 Future Extensions

- **🌐 Multiprocessing:** Introduce multiprocessing for better parallelism on multi-core systems.
- **🚫 Access Filtering:** Add rules to allow/block specific websites or domains.
- **📬 Request Method Support:** Implement HTTP POST and other methods.
- **📦 Advanced Cache:** Dynamic cache sizing and fragmentation fixes for storing large site responses.
- **🔐 Encryption Support:** Add HTTPS handling or encrypt requests to improve privacy and security.

---

## 📁 Project Structure

