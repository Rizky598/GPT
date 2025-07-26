# Rizky-AI Bot Dashboard

Dashboard web untuk mengelola bot Telegram Rizky-AI dengan fitur lengkap untuk manajemen premium users, konfigurasi API, monitoring sistem, dan kontrol bot.

## 🚀 Fitur Utama

### 🔐 Sistem Login
- Login dengan password: `Rizky-Ai`
- Session management dengan PHP
- Logout otomatis untuk keamanan

### 👑 Premium Users Management
- Tambah premium user dengan durasi custom
- Lihat daftar semua premium users
- Hapus premium user
- Status tracking (active/expired)

### ⚙️ API Management
- Konfigurasi Bot Token Telegram
- Konfigurasi Google AI API Key
- Toggle visibility password untuk keamanan
- Save configuration langsung ke file bot

### 📊 Bot Monitoring
- Real-time bot status (online/offline)
- System resources monitoring (CPU, Memory)
- Bot uptime tracking
- Activity logs
- Statistics dashboard

### 🎛️ Bot Control
- Start/Stop/Restart bot dari dashboard
- Maintenance mode toggle
- Process management

## 📁 Struktur Proyek

```
telegram-dashboard/
├── frontend/           # Frontend files (HTML, CSS, JS)
│   ├── index.html     # Main dashboard page
│   ├── styles.css     # Dashboard styling
│   ├── script.js      # Frontend JavaScript
│   └── backend/       # Symlink to backend
├── backend/           # Backend PHP files
│   ├── api/          # API endpoints
│   │   ├── auth.php          # Authentication
│   │   ├── premium.php       # Premium users management
│   │   ├── config.php        # Bot configuration
│   │   ├── monitoring.php    # System monitoring
│   │   └── bot-control.php   # Bot control
│   ├── config/       # Configuration files
│   │   ├── database.php      # Database operations
│   │   └── auth.php          # Authentication logic
│   └── data/         # Data storage
├── bot/              # Original Telegram bot files
│   ├── main.js       # Bot main file
│   ├── config.js     # Bot configuration
│   ├── lib/          # Bot libraries and data
│   └── package.json  # Bot dependencies
├── start.sh          # System startup script
├── stop.sh           # System stop script
└── README.md         # This documentation
```

## 🛠️ Instalasi dan Setup

### Persyaratan Sistem
- PHP 8.1+ dengan ekstensi json dan curl
- Node.js 18+ dan npm
- Linux/Unix environment (Ubuntu recommended)

### Langkah Instalasi

1. **Extract dan Setup**
   ```bash
   # File sudah di-extract ke telegram-dashboard/
   cd telegram-dashboard
   ```

2. **Install Dependencies Bot**
   ```bash
   cd bot
   npm install
   cd ..
   ```

3. **Konfigurasi Bot**
   - Edit `bot/config.js` dan masukkan Bot Token dan Google AI API Key
   - Atau gunakan dashboard untuk konfigurasi

4. **Jalankan Sistem**
   ```bash
   ./start.sh
   ```

## 🚀 Cara Penggunaan

### Menjalankan Sistem

```bash
# Start semua services
./start.sh

# Stop semua services
./stop.sh
```

### Mengakses Dashboard

1. Buka browser dan akses: `http://localhost:8080`
2. Login dengan password: `Rizky-Ai`
3. Dashboard akan terbuka dengan menu navigasi di sidebar

### Konfigurasi Bot

1. Masuk ke menu **API Management**
2. Masukkan Bot Token dari @BotFather
3. Masukkan Google AI API Key
4. Klik **Save Configuration**

### Mengelola Premium Users

1. Masuk ke menu **Premium Users**
2. Klik **Add Premium User**
3. Masukkan User ID Telegram dan durasi (hari)
4. User akan otomatis ditambahkan ke sistem bot

### Monitoring Bot

1. Masuk ke menu **Monitoring**
2. Lihat system resources (CPU, Memory)
3. Cek activity logs
4. Monitor bot performance

### Kontrol Bot

1. Masuk ke menu **Settings**
2. Gunakan tombol **Restart Bot** atau **Stop Bot**
3. Toggle **Maintenance Mode** untuk maintenance

## 🔧 Konfigurasi untuk Termux

Untuk menjalankan di Termux Android:

1. **Install Dependencies**
   ```bash
   pkg update && pkg upgrade
   pkg install php nodejs-lts
   ```

2. **Setup Project**
   ```bash
   # Copy project ke Termux storage
   cd /data/data/com.termux/files/home
   # Extract project files here
   ```

3. **Jalankan**
   ```bash
   cd telegram-dashboard
   ./start.sh
   ```

4. **Akses Dashboard**
   - Dari Termux: `http://localhost:8080`
   - Dari device lain di network yang sama: `http://[IP-TERMUX]:8080`

## 📱 Akses dari Device Lain

Untuk mengakses dashboard dari device lain di network yang sama:

1. Cari IP address Termux:
   ```bash
   ifconfig wlan0
   ```

2. Akses dari browser device lain:
   ```
   http://[IP-ADDRESS]:8080
   ```

## 🔒 Keamanan

- Password dashboard: `Rizky-Ai`
- Session-based authentication
- API endpoints protected dengan authentication
- CORS enabled untuk cross-origin requests

## 🐛 Troubleshooting

### Dashboard tidak bisa diakses
```bash
# Cek apakah server berjalan
ps aux | grep php

# Restart server
./stop.sh
./start.sh
```

### Bot tidak bisa start
```bash
# Cek log bot


# Install ulang dependencies
cd bot && npm install
```

### API tidak response
```bash
# Cek permission file
chmod -R 755 backend/

# Cek log server
tail -f server.log
```

## 📝 API Endpoints

- `POST /backend/api/auth.php` - Authentication
- `GET|POST|DELETE /backend/api/premium.php` - Premium users
- `GET|POST /backend/api/config.php` - Bot configuration
- `GET /backend/api/monitoring.php` - System monitoring
- `POST /backend/api/bot-control.php` - Bot control

## 🎯 Fitur Mendatang

- [ ] Database integration (SQLite/MySQL)
- [ ] User roles dan permissions
- [ ] Advanced analytics
- [ ] Backup dan restore
- [ ] Multi-bot support

## 📞 Support

Untuk bantuan dan support, silakan hubungi developer atau buat issue di repository.

---

**Dibuat dengan ❤️ untuk Rizky-AI Bot**

