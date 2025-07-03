# 🚀 Tutorial Menjalankan Tiny Computer XFCE di Android Tanpa PC

Tutorial ini menjelaskan cara menjalankan desktop Linux (Tiny Computer XFCE) langsung di HP Android tanpa root dan tanpa PC, serta bebas error Signal 9 (phantom kill). Cocok untuk coding, pengetesan, dan belajar Linux full GUI langsung dari Android.

---

## 🧰 File & Tools yang Dibutuhkan

| Aplikasi | Link Resmi |
|----------|-------------|
| ✅ Termux (versi resmi) | [Download via F-Droid](https://f-droid.org/packages/com.termux/) |
| ✅ Tiny Computer XFCE (APK) | [GitHub: Tiny Core Linux Android](https://github.com/EXALAB/tc-install) |
| ✅ WPS Office .deb (opsional) | [wps-community (GitHub)](https://github.com/wps-community/wps_office_installer) *(atau cari repo debian)*

---

## 📱 Langkah Lengkap Instalasi & Konfigurasi

### 1. Instal Aplikasi

- Install **Termux** dari F-Droid  
  👉 [https://f-droid.org/packages/com.termux/](https://f-droid.org/packages/com.termux/)

- Install **Tiny Computer XFCE** dari GitHub  
  👉 [https://github.com/EXALAB/tc-install](https://github.com/EXALAB/tc-install)  
  *(Cari file `.apk` terbaru pada tab "Releases")*

---

### 2. Aktifkan Wireless Debugging

1. Masuk ke **Setelan > Tentang Ponsel**
2. Ketuk 7x "Nomor Bentukan" → aktifkan **Opsi Pengembang**
3. Aktifkan:
   - ✅ USB Debugging
   - ✅ Wireless Debugging

---

### 3. Jalankan Termux & Pasang ADB Tools

```bash
# LANGKAH 1–4: Update dan Install ADB di Termux
apt update && apt upgrade -y
pkg install android-tools -y

# LANGKAH 5–7: Pairing ADB Wireless
adb pair localhost:40365  # GANTI dengan pairing port dari Wireless Debugging
# Masukkan pairing code (misalnya: 123456)
adb connect localhost:44739  # GANTI dengan port adb connect kamu
adb devices

# LANGKAH 8: Fix Signal 9 / Phantom Kill Bypass
adb shell "/system/bin/device_config set_sync_disabled_for_tests persistent"
adb shell "/system/bin/device_config put activity_manager max_phantom_processes 2147483647"
adb shell settings put global settings_enable_monitor_phantom_procs false

# LANGKAH 9: Buka Tiny Computer (manual buka APK), login:
# Username: tiny
# Password: tiny
# Tekan tombol "Start Desktop"

# LANGKAH 10: Setelah login ke desktop Tiny, buka terminal lalu ketik:
tmoe
# Pilih english_united states ➜ manager ➜ locale ➜ english_united states
# lalu ketik:
exit
# lalu tutup paksa Tiny dan buka ulang agar bahasa jadi English

# LANGKAH 11: (Opsional) install browser dan WPS Office:
sudo apt update
sudo apt install firefox-esr -y
# Atau:
sudo apt install midori -y

# (Opsional) Install .deb
# sudo dpkg -i namafile.deb
# sudo apt --fix-broken install

# DONE ✅ SELAMAT MENIKMATI XFCE TANPA ROOT DAN TANPA PC
