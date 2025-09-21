# 🌟 Panduan React Native di Windows

Selamat datang di panduan cepat dan santai buat kamu yang mau ngoding dengan **React Native** di Windows! 🚀✨

Panduan ini dibuat biar kamu nggak bingung lagi dari awal setup sampai aplikasi bisa jalan di emulator ataupun HP kamu. Fokus kita ada di **Android**, karena build iOS cuma bisa di macOS. 😅

---

## ⚙️ Apa aja yang harus disiapin?

1. **Node.js (LTS 18+)** 🟢
   👉 [Download Node.js](https://nodejs.org/en/download)

   ```powershell
   choco install -y nodejs-lts
   node -v
   ```

2. **JDK 17** ☕
   Kenapa JDK 17? Karena paling aman buat Gradle!
   👉 [Download JDK 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)

   ```powershell
   choco install -y microsoft-openjdk17
   java -version
   ```

3. **Android Studio & SDK** 📱
   👉 [Download Android Studio](https://developer.android.com/studio)

   * Centang **SDK, SDK Platform, AVD** waktu instalasi.
   * Tambahin **SDK Android 15 (API 35)** lewat SDK Manager.
   * Jangan lupa pasang: **Platform-Tools, Emulator, Command-line Tools, AEHD/Hypervisor Driver**.

4. **Setting Environment Variables** 🛠️
   Tambahin ini di Windows:

   ```
   ANDROID_HOME = C:\Users\<USERNAME>\AppData\Local\Android\Sdk
   PATH += %ANDROID_HOME%\platform-tools
   PATH += %ANDROID_HOME%\emulator
   ```

   Tes dengan:

   ```powershell
   adb --version
   ```

   Kalau keluar versi, berarti sukses! 🎉

---

## 🚀 Bikin Proyek Pertama

```bash
npx @react-native-community/cli@latest init AwesomeProject
cd AwesomeProject
```

Sip, proyek pertama kamu udah jadi! 🎊

---

## ▶️ Jalankan Proyek Kamu

1. **Start Metro Bundler** (otaknya React Native) 🧠

   ```bash
   npm start
   ```

   Atau langsung build ke Android:

   ```bash
   npm run android
   ```

2. **Jalanin di Emulator** 🖥️

   * Buka Android Studio → **AVD Manager** → Create Virtual Device → pilih Android 15.
   * Start emulator.

   **Mau di HP langsung?** 📱

   * Aktifin **USB Debugging** di Developer Options.
   * Sambungin HP ke laptop, lalu cek:

     ```bash
     adb devices
     ```

3. **Build & Run App**

   ```bash
   npx react-native run-android
   ```

Dan boom 💥 aplikasi kamu jalan di device!

---

## 🔄 Coba Hot Reload

* Ubah isi `App.tsx`.
* Tekan `R` dua kali di emulator, atau pilih **Reload** dari menu developer. 🔥

Codingan langsung update tanpa restart aplikasi. Mantap kan? 😎

---

## ⚠️ Beberapa Catatan Penting

* **iOS build?** Nggak bisa di Windows, harus macOS. 🍏
* Pake **JDK 17** biar aman.
* Kalau error pakai JDK baru → sesuaikan versi **Gradle** di `android/gradle/wrapper`.
* Kalau ada lisensi SDK, ketik ini:

  ```bash
  sdkmanager --licenses
  ```

  Terus pencet `y` aja sampai selesai. ✅

---

## 📝 Ringkasan Command Penting

```bash
npx @react-native-community/cli@latest init AwesomeProject
cd AwesomeProject
npm start
npm run android
adb devices
sdkmanager --licenses
```

🔗 Referensi resmi: [React Native Getting Started](https://reactnative.dev/docs/getting-started)

---

🎉 Selamat! Kamu udah siap bikin aplikasi React Native pertama kamu di Windows.
Sekarang tinggal **explore, kreasikan, dan bangun app keren versi kamu sendiri**! 🚀💡
