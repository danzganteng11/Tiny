# 🧠 Tiny Computer XFCE di Android (Tanpa Root, Tanpa PC)

Tutorial ini menjelaskan cara menjalankan sistem operasi desktop XFCE (Linux) langsung dari HP Android menggunakan **Termux + Tiny Computer XFCE** — tanpa root, tanpa PC, dan bebas error Signal 9.

---

## 📲 Download APK Tiny XFCE

Klik tombol di bawah ini untuk langsung download aplikasi Tiny Computer XFCE versi terbaru

---

## 🛠️ Tools yang Dibutuhkan

| Aplikasi                  | Link Download                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| ✅ Termux (via F-Droid)    | [📥 Download Termux](https://f-droid.org/packages/com.termux/)                |
| ✅ Tiny XFCE APK           | [📥 Download APK](https://github.com/Cateners/tiny_computer/releases/download/v1.0.24/tiny-computer-xfce.apk) |
| ⚙️ WPS Office (opsional)   | [📥 Download WPS .deb](https://wdl1.pcfg.cache.wpscdn.com/wpsdl/wpsoffice/download/linux/11723/wps-office_11.1.0.11723.XA_amd64.deb)                      |

---

## 🚀 Langkah-Langkah Install di Termux (1x Jalan)

✂️ Copy semua perintah di bawah ini lalu paste ke Termux kamu:

```bash
# STEP 1: Update dan Install ADB
apt update && apt upgrade -y
pkg install android-tools -y
<__________________________>
# STEP 2: Pairing Wireless Debugging (ubah port & kode sesuai punyamu)

adb pair localhost:
adb connect localhost:
adb devices
<_________________________>
# STEP 3: Fix error "Signal 9" (phantom kill)

adb shell "/system/bin/device_config set_sync_disabled_for_tests persistent"
adb shell "/system/bin/device_config put activity_manager max_phantom_processes 2147483647"
adb shell settings put global settings_enable_monitor_phantom_procs false

---
