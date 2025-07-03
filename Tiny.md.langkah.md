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
apt update
apt upgrade
pkg install android-tools

---

### 4. Pairing ADB via Wireless (Localhost)
Buka Wireless Debugging di HP kamu

Ambil info pairing dan port (misal: localhost:40365)

Jalankan:

'''bash
adb pair localhost:40365
# Masukkan pairing code dari layar HP

adb connect localhost:44739
adb devices
