# Ex.No.3 — Wireshark Network Packet Capture and Analysis Tool

![Wireshark](https://img.shields.io/badge/Tool-Wireshark-green)
![Platform](https://img.shields.io/badge/Platform-Cross--Platform-orange)
![Type](https://img.shields.io/badge/Analysis-Network%20Analysis-blue)

**📚 Course / Lab:** Digital Forensics Lab  
**🔢 Experiment No.:** 3  
**📝 Title:** Wireshark – Network Packet Capture and Analysis Tool

---

## 📑 Table of Contents

- [Ex.No.3 — Wireshark Network Packet Capture and Analysis Tool](#exno3--wireshark-network-packet-capture-and-analysis-tool)
  - [📑 Table of Contents](#-table-of-contents)
  - [🎯 Aim](#-aim)
  - [🛠️ Requirements](#️-requirements)
  - [📝 Description](#-description)
  - [🌐 Website Used](#-website-used)
  - [📋 Procedure: Capturing Plaintext Passwords](#-procedure-capturing-plaintext-passwords)
    - [Step 1: Start Capturing Packets](#step-1-start-capturing-packets)
    - [Step 2: Generate Login Traffic](#step-2-generate-login-traffic)
    - [Step 3: Stop Capture and Filter Traffic](#step-3-stop-capture-and-filter-traffic)
    - [Step 4: Inspect the Packet to Find Credentials](#step-4-inspect-the-packet-to-find-credentials)
  - [✅ Result](#-result)
  - [📝 Notes](#-notes)

---

## 🎯 Aim
To demonstrate how to use **Wireshark** for network packet capture and analysis, specifically focusing on capturing and analyzing plaintext passwords transmitted over HTTP connections to understand network security vulnerabilities.

---

## 🛠️ Requirements

- **💻 Computer with network connectivity**
- **🔧 Wireshark** (Network Protocol Analyzer)
- **🌐 Web browser** (Chrome, Firefox, Edge, etc.)
- **📡 Active network interface** (Wi-Fi or Ethernet)
- **🎯 Test website** for demonstration purposes

---

## 📝 Description
Wireshark is a powerful **network protocol analyzer** that allows users to capture and interactively browse the traffic running on a computer network. It is widely used by network administrators, security professionals, and forensic investigators to analyze network communications, troubleshoot network issues, and identify security vulnerabilities. This experiment demonstrates how easily plaintext credentials can be intercepted when transmitted over unsecured HTTP connections.

---

## 🌐 Website Used
**🔗 Test Site:** [http://demo.testfire.net/](http://demo.testfire.net/)

⚠️ **Note:** This is a deliberately vulnerable web application designed for security testing and educational purposes.

---

## 📋 Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets

**🎯 Purpose:** Initialize Wireshark and begin network traffic capture.

**📋 Instructions:**

1. **🚀 Open Wireshark application.**

2. **📡 You will see a list of all available network interfaces:**
   - Wi-Fi adapter
   - Ethernet adapter
   - Loopback interface

3. **🔍 Select the network interface your computer is using to connect to the internet** (typically Wi-Fi or Ethernet).

<details>
<summary>🖥️ View Network Interface Selection</summary>
<br>
<p align="center">
 <img width="1893" height="994" alt="Screenshot 2025-11-12 161910" src="https://github.com/user-attachments/assets/51041c19-1f3a-4d7f-a482-b46f34bf51be" />
</p>
</details>

4. **🦈 Click the blue shark fin icon in the top-left corner to start the capture.**
   - Wireshark will immediately begin capturing all network traffic passing through the selected interface.

<details>
<summary>📊 View Packet Capture Interface</summary>
<br>
<p align="center">
  <img width="1919" height="1023" alt="Screenshot 2025-11-12 162125" src="https://github.com/user-attachments/assets/83e4ce0d-2de6-4998-a0c8-8fcc3b0e137e" />
</p>
</details>

---

### Step 2: Generate Login Traffic

**🎯 Purpose:** Create network traffic containing login credentials for analysis.

**📋 Instructions:**

1. **🌐 Open a web browser and navigate to:** `http://demo.testfire.net/`

2. **👤 Enter dummy credentials for testing:**
   - **Username:** `testuser`
   - **Password:** `password123`

3. **🔐 Click the login button.**
   - The login will fail (expected behavior)
   - However, the credentials have been transmitted over the network

<details>
<summary>🔐 View Login Process</summary>
<br>
<p align="center">
  <img width="1920" height="1080" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/5f937be9-f192-4f40-b227-73e689014eab" />
</p>
</details>

---

### Step 3: Stop Capture and Filter Traffic

**🎯 Purpose:** Stop packet capture and isolate relevant HTTP traffic for analysis.

**📋 Instructions:**

1. **⏹️ Return to Wireshark and click the Stop button** (red square icon).

2. **🔍 Apply a display filter to find the login packet:**
   - In the display filter bar, enter appropriate filter criteria
   - Look for HTTP POST requests containing form data
   - Press **Enter** to apply the filter

<details>
<summary>🔍 View Traffic Filtering</summary>
<br>
<p align="center">
  <img width="1919" height="1022" alt="Screenshot 2025-11-12 164006" src="https://github.com/user-attachments/assets/466cb20e-1334-499f-84e8-bee5282467e1" />
</p>
</details>

---

### Step 4: Inspect the Packet to Find Credentials

**🎯 Purpose:** Analyze captured packets to extract plaintext credentials.

**📋 Instructions:**

1. **📋 In the filtered packet list, locate a packet with information like:**
   - `POST /userinfo.php` or similar endpoint
   - HTTP protocol designation

2. **🔍 Select the relevant packet to view its details.**

3. **📂 In the Packet Details pane, expand the following sections:**
   - **Hypertext Transfer Protocol**
   - **HTML Form URL Encoded**

4. **👁️ Inside the "HTML Form URL Encoded" section:**
   - You will see the credentials transmitted in plaintext
   - Username and password are clearly visible

<details>
<summary>🚨 View Credential Extraction</summary>
<br>
<p align="center">
  <img width="1918" height="1031" alt="Screenshot 2025-11-12 170022" src="https://github.com/user-attachments/assets/4cfc014e-1e0c-4f64-b623-d20e1bc02a77" />
</p>
</details>

---

## ✅ Result

The experiment successfully demonstrates the interception of login credentials in a human-readable format. The analysis of the captured POST packet reveals the plaintext data that was transmitted over the network.

