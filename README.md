# **SafeGas: IoT-Based Smart Gas Leak Detection System**

SafeGas adalah proyek berbasis **Internet of Things (IoT)** yang dirancang untuk mendeteksi kebocoran gas secara real-time, memberikan peringatan dini, dan mengambil tindakan otomatis guna meningkatkan keamanan rumah tangga dan industri.

---

## **Fitur Utama**
- 🔍 **Deteksi Real-Time**: Mendeteksi gas berbahaya seperti LPG, metana, dan karbon monoksida.  
- 📱 **Notifikasi Langsung**: Memberikan peringatan ke aplikasi mobile/web.  
- ⚙️ **Tindakan Otomatis**: Mengontrol solenoid valve untuk menutup aliran gas dan exhaust fan untuk ventilasi.  
- 📊 **Data Historis**: Menyimpan data konsentrasi gas untuk analisis lebih lanjut.  
- ☁️ **Integrasi Cloud**: Menggunakan **AWS IoT Core, Lambda, DynamoDB**, dan **SNS** untuk memproses data dan mengelola notifikasi.  

---

## **Arsitektur Sistem**
Sistem SafeGas terdiri dari beberapa layer:  
1. **Edge Layer**:  
   - **Komponen**: Sensor Gas (MQ-2), Solenoid Valve, Exhaust Fan.  
   - **Fungsi**: Mendeteksi kebocoran gas dan mengaktifkan tindakan lokal.  

2. **Network Layer**:  
   - **Komponen**: Gateway, Modul Komunikasi (Wi-Fi/LoRa).  
   - **Fungsi**: Menghubungkan perangkat edge ke cloud.  

3. **Cloud Layer**:  
   - **Komponen**: AWS IoT Core, Lambda, DynamoDB, SNS.  
   - **Fungsi**: Pemrosesan data, penyimpanan, dan pengiriman notifikasi.  

4. **Application Layer**:  
   - **Komponen**: Aplikasi Mobile/Web.  
   - **Fungsi**: Monitoring data dan kontrol perangkat.

---

## **Teknologi yang Digunakan**
- **Perangkat Keras**:  
  - Sensor Gas (MQ-2)  
  - Mikrokontroler (ESP32/ESP8266)  
  - Solenoid Valve  
  - Exhaust Fan  

- **Layanan Cloud**:  
  - AWS IoT Core  
  - AWS Lambda  
  - AWS DynamoDB  
  - AWS SNS  

- **Bahasa Pemrograman**:  
  - Python (untuk cloud functions)  
  - C++/Arduino (untuk mikrokontroler)  

---

## **Cara Kerja**
1. Sensor gas mendeteksi konsentrasi gas di lingkungan.  
2. Data dikirimkan ke gateway melalui Wi-Fi/LoRa.  
3. Gateway mengirim data ke AWS IoT Core untuk diproses.  
4. AWS Lambda menganalisis data, dan jika mendeteksi kebocoran, mengirimkan:  
   - **Perintah ke aktuator** (solenoid valve atau exhaust fan).  
   - **Notifikasi ke pengguna** melalui aplikasi mobile/web.  
5. Pengguna dapat memantau kondisi real-time dan mengontrol perangkat melalui aplikasi.  

---

