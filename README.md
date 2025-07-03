# Tiny
Untuk menggunakan GUI windows Linux menggunakan termux+Tiny computer xfce 
# 🧠 Tiny Computer XFCE di Android (Tanpa Root, Tanpa PC)

Tutorial ini menjelaskan cara menjalankan sistem operasi desktop XFCE (Linux) langsung dari HP Android menggunakan **Termux + Tiny Computer XFCE** — tanpa perlu PC, tanpa root, dan bebas error Signal 9.

---

## 🚀 Tools yang Digunakan

| Aplikasi               | Link Resmi                                                                 |
|------------------------|----------------------------------------------------------------------------|
| ✅ Termux (F-Droid)     | [Download Termux](https://f-droid.org/packages/com.termux/)                |
| ✅ Tiny Computer XFCE   | [Download Tiny XFCE APK](https://github.com/EXALAB/tc-install/releases)    |
| ⚙️ Optional (WPS .deb)  | [WPS Community](https://github.com/wps-community)                          |

---

## 🔧 Langkah Eksekusi 1x Jalan

Copy script di bawah ini dan jalankan langsung dari Termux:

```bash
# STEP 1: Update Termux & install ADB
apt update && apt upgrade -y
pkg install android-tools -y

# STEP 2: Pair Wireless Debugging (ganti port & kode sesuai milikmu)
adb pair localhost:40365
# Masukkan kode pairing saat diminta

adb connect localhost:44739
adb devices

# STEP 3: Fix Signal 9 (phantom kill)
adb shell "/system/bin/device_config set_sync_disabled_for_tests persistent"
adb shell "/system/bin/device_config put activity_manager max_phantom_processes 2147483647"
adb shell settings put global settings_enable_monitor_phantom_procs false

# STEP 4: Buka aplikasi Tiny Computer XFCE dan login:
# Username: tiny | Password: tiny
# Klik "Start Desktop"

# STEP 5: Setelah masuk desktop, ubah bahasa:
tmoe
# ➜ Pilih english_united states ➜ manager ➜ locale ➜ english_united states ➜ exit

# STEP 6: Install Browser
sudo apt update
sudo apt install firefox-esr -y
# atau sudo apt install midori -y

# (Opsional) Install WPS .deb jika ada
# sudo dpkg -i namafile.deb
# sudo apt --fix-broken install
