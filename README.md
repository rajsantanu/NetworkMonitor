# Network Monitor — Android Studio Project

## How to Build APK

### Prerequisites
- Android Studio Hedgehog (2023.1.1) or newer
- JDK 17+
- Android SDK with API 34

### Steps
1. Open Android Studio → **Open** → select this `NetworkMonitor` folder
2. Wait for Gradle sync to complete (first time may take 3–5 min downloading dependencies)
3. **Build → Build Bundle(s) / APK(s) → Build APK(s)**
4. APK location: `app/build/outputs/apk/debug/app-debug.apk`
5. Install: `adb install app/build/outputs/apk/debug/app-debug.apk`

### First Launch
- Grant **Usage Access** permission when prompted
  (Settings → Apps → Special app access → Usage access → Network Monitor → Enable)
- Grant **Notifications** permission (Android 13+)

### Features
- ⚡ Real-time download/upload speed (updates every second)
- 📡 Connection type, WiFi link speed, IPv4/IPv6, DNS, interface
- 📱 Per-app data usage (WiFi + Mobile) for last 30 days
- 🔔 Persistent notification showing live speed

### Project Structure
```
app/src/main/
├── AndroidManifest.xml
├── java/com/netmonitor/
│   ├── MainActivity.kt          — UI, tabs, permission handling
│   ├── NetworkSpeedService.kt   — Foreground service, TrafficStats polling
│   ├── NetworkStatsHelper.kt    — NetworkStatsManager per-app queries
│   ├── AppUsageAdapter.kt       — RecyclerView adapter
│   └── models/AppNetworkInfo.kt — Data model
└── res/
    ├── layout/activity_main.xml
    └── layout/item_app_usage.xml
```
