# How to Limit Bufferbloat in Windows

This guide will help you make your internet faster by changing some settings on your Windows computer.

## What You Need

- You need to be an **admin** (the boss) on your computer.
- This guide works on Windows Pro, Enterprise, and Education. If you have Windows Home, you might need to turn on Group Policy Editor first.

## Steps to Follow

### 1. Open Group Policy Editor
- Press `Win + R` on your keyboard.
- Type `gpedit.msc` and hit **Enter**.

### 2. Find QoS Settings
- In the Group Policy Editor, go to:
  ```
  Computer Configuration > Administrative Templates > Network > QoS Packet Scheduler
  ```

### 3. Change Packet Settings
- Look for **Limit outstanding packets**.
- Double-click it.
- Turn it **On** (set it to **Enabled**).
- Change the number to between **5 and 20 packets**. This helps reduce lag.

### 4. Change Bandwidth Settings
- Go to:
  ```
  Computer Configuration > Administrative Templates > Network > QoS Packet Scheduler > Limit Reservable Bandwidth
  ```
- Turn this **On** (set it to **Enabled**).
- Change the percentage to **0**. This means no bandwidth is reserved.

### 5. Save and Restart
- Click **OK** to save your changes.
- Restart your computer to make everything work.

## Extra Tips
- You can also check your router settings. If it has options like **Smart Queue Management (SQM)** or **fq_codel**, turn those on to help even more.
- Test how well your internet is doing by visiting the **DSLReports Speed Test** website.
