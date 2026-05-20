# **Pomodoro Alarm: Premium Warm-Monochrome Focus Hub**

An elegant, browser-native Pomodoro utility built with an ultra-premium, "Utilitarian Premium" aesthetic. It leverages a modern bento-grid layout, high-contrast typography hierarchies, tactile micro-animations, and custom-synthesized browser audio.

## **🎨 Design Philosophy & Aesthetic Tokens**

The application prioritizes functional elegance, avoiding generic dashboards in favor of an editorial, tactile, high-end look.

### **1\. Palette & Atmosphere**

* **Warm Monochrome Canvas (\#F7F6F3):** A soft, warm off-white that prevents screen glare and evokes premium physical stationery.  
* **Ink Black (\#111111):** A high-contrast off-black used for precise readability of numbers, titles, and borders.  
* **Muted Accent States:**  
  * **Work Mode (Fokus Kerja):** Soft crimson (\#9F2F2D) represents focus, heat, and activity.  
  * **Break Mode (Istirahat):** Warm sage (\#346538) represents ease, rest, and renewal.  
* **Ambient Depth:** An interactive soft background radial glow slowly shifts positions and changes tint to reflect whether you are in focus or break mode.

### **2\. Typographic Hierarchy**

The UI blends three premium font families:

* **Editorial Serif (Instrument Serif):** Used for large headers to give the interface a literary, thoughtful atmosphere.  
* **Modern Sans-Serif (Geist / SF Pro Display):** Provides clean, highly legible structures for UI layout, forms, and instructions.  
* **Tactile Mono (Geist Mono / SF Mono):** Used for dynamic data elements like digital timer counts, hotkey keyboard badges (\<kbd\>), stats, and labels.

## **🧱 The Bento Grid Layout**

The interface uses a highly responsive grid layout that adapts flawlessly from wide desktop layouts to vertical mobile screens.

\+-------------------------------------------------------------------+  
|                         Editorial Header                          |  
|                  POMODORO ALARM (Vers. 2.2.0)                     |  
\+------------------------------------+------------------------------+  
|                                    |                              |  
|           CARD 1: TIMER            |       CARD 2: SHORTCUTS      |  
|                                    |       \[Space\]  \[R\]  \[Tab\]    |  
|   (Interactive Twin-Bell Clock     |                              |  
|   Vector, Mode Switcher, Progress, \+------------------------------+  
|   Tactile Play/Pause Controls)     |                              |  
|                                    |       CARD 3: FOCUS TASKS    |  
|                                    |       "Input custom task..." |  
|                                    |                              |  
\+------------------------------------+------------------------------+  
|                                                                   |  
|                   CARD 4: ANALYTICS & LOGS                        |  
|        \[ Total Fokus \]  \[ Sesi Selesai \]  \[ Efficiency: A+ \]      |  
|                                                                   |  
\+-------------------------------------------------------------------+

## **⚙️ Core Technical Architecture**

The single-file app features robust structural and logical mechanics entirely in pure, local vanilla JavaScript:

### **🔊 Native Web Audio API Chime**

Instead of depending on heavy, fragile external .mp3 dependencies that can fail due to network changes, the application uses the browser's built-in **Web Audio API** to synthesize a custom, resonant, three-tone melodic chord (C-Major progression):

* Creates an AudioContext and dynamically spins up short-lived, high-quality oscillators.  
* Shapes the tone envelopes with custom gain nodes to eliminate harsh clicks, giving a premium "bell chime" ring.  
* Outputs a series of warm sine-wave frequencies to announce transitions gently yet clearly.

### **⏰ Structural State & Timer Machine**

* **High-Accuracy Drift Protection:** Evaluates time continuously using browser interval clocks to prevent sleep delays and tab-throttling bugs.  
* **Physical Clock Animation Engine:** The CSS alarm clock features custom physical animation loops:  
  * float-slow triggers when active to give a gentle "breathing" kinetic feel.  
  * clock-shaking triggers when the timer completes, physically rattling the bell-striker vector until dismissed.

### **⌨️ Dynamic Keyboard Navigation**

Power-users can fully pilot their focus flow without ever lifting their hands from the keyboard:

* Spacebar ![][image1] Start/Pause current countdown  
* R or r ![][image1] Reset current mode back to default durations  
* Tab ![][image1] Instantly cycle focus modes (Work vs. Break)

### **📝 Minimalist Task List**

* A clean, inline task engine that supports adding tasks by pressing Enter.  
* Includes completion checkbox states that apply a clean line-through styled text transition.  
* A localized hover-state button slides out to display **"HAPUS"** for instant deletion.

## **📖 User & Configuration Guide**

### **Standard Operational Workflow**

1. **Configure Intent:** Choose whether you want to log **Fokus Kerja** (25 minutes) or **Istirahat** (1 minute/short break).  
2. **Add Goals:** Write down your target tasks in the **Daftar Tugas** card to keep them visually anchored next to the clock.  
3. **Execute & Run:** Hit Mulai Sesi or tap the Spacebar. The clock will begin floating, and the background ambient color will subtly pulse.  
4. **Transition:** When the countdown reaches 00:00, the chime will sound, the clock will vibrate, and a modern modal will request your attention to move into your next session block.

### **State Reset & Diagnostics**

* Should you need to halt a session, clicking **Atur Ulang** (or hitting R) will restore the selected mode's maximum value.  
* Total completed sessions are dynamically added into the bottom analytics grid continuously during your active session.

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABUAAAAYCAYAAAAVibZIAAAAoUlEQVR4XmNgGAWjYGCBgoICh5ycXJqoqCgPuhwlgFFeXr4VaLAxugRFAGQg0OBeIJMFXY4SwAgMhgKg4XEgNrokGAAVCABtliQFKykpAc2Umw9kT1ZRUeFDN5MsICsrawI0cLW0tLQMuhxZAGiQMNDAxYqKivLocmQDoIFZwCCLQBcnG4DSKdDQqTIyMtLocpQARnV1dV4QjS4xCkYBjQAAvNgWekn9kccAAAAASUVORK5CYII=>