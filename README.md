# 🚀 Jalankan Tiny Computer XFCE di Android Tanpa PC (NO Signal 9!)

Tutorial ini akan membimbing kamu untuk menjalankan **Tiny Computer XFCE** langsung dari Android, tanpa root, tanpa PC, dan bebas dari error **Signal 9 / Phantom Kill**. Semua cukup dari HP dengan bantuan **Termux Mod + ADB Wireless**.

---

## 🧰 Tools & File yang Dibutuhkan

| Tools / App | Link Download |
|-------------|----------------|
| ✅ Termux Mod v118 | [Download Termux Mod](https://sub4unlock.com/termuxmod) |
| ✅ Tiny Computer XFCE APK (versi besar) | [Download Tiny XFCE](https://sub4unlock.com/tinyxfce) |
| ✅ WPS Office .deb (opsional) | [Download WPS Office](https://sub4unlock.com/wpsdebian) |

> Pastikan semua file APK sudah kamu install di HP Android kamu.

---

## 🔧 Langkah Instalasi Lengkap

### 1. Nonaktifkan Play Protect

- Buka **Play Store**
- Tap foto profil > **Play Protect**
- Tap ⚙️ > Matikan dua opsi:
  - Scan apps with Play Protect
  - Improve harmful app detection

---

### 2. Jalankan Termux & Install ADB Tools

```bash
apt update
apt upgrade
apt install android-tools
