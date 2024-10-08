
---

# How to Limit Bufferbloat Using Group Policy on Windows

This guide outlines how to reduce Bufferbloat on Windows by configuring network-related settings through the **Group Policy Editor**.

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Steps to Limit Bufferbloat](#steps-to-limit-bufferbloat)
3. [Additional Tips](#additional-tips)

---

## Prerequisites

- You must have **administrator privileges**.
- Group Policy Editor is available in **Windows Pro, Enterprise**, and **Education** editions. If you are on Windows Home, you may need to enable the Group Policy Editor manually.

---

## Steps to Limit Bufferbloat

1. **Open Group Policy Editor**:
   - Press `Win + R`, type `gpedit.msc`, and hit **Enter** to open the Group Policy Editor.

2. **Navigate to QoS Settings**:
   - In the Group Policy Editor, go to:
     ```
     Computer Configuration > Administrative Templates > Network > QoS Packet Scheduler
     ```

3. **Adjust the QoS Packet Scheduler**:
   - Find the setting **Limit outstanding packets**.
   - Double-click on this setting to configure it.
   - Set it to **Enabled**, and adjust the packet limit to a lower value. A typical value is **5** to **20** packets, which helps prevent excessive buffering.

4. **Set a Limit for Bandwidth**:
   - Go to:
     ```
     Computer Configuration > Administrative Templates > Network > QoS Packet Scheduler > Limit Reservable Bandwidth
     ```
   - Set this option to **Enabled**, and reduce the reserved bandwidth percentage to **0**.

5. **Apply and Reboot**:
   - Click **OK** to apply changes.
   - Restart your system to apply the new settings.

---

## Additional Tips

- Reducing Bufferbloat may also involve adjusting router settings. Consider enabling **Smart Queue Management (SQM)** or **fq_codel** on your router if supported.
- You can check the effectiveness of these settings by running a **Bufferbloat test** at [DSLReports Speed Test](http://www.dslreports.com/speedtest).

---
