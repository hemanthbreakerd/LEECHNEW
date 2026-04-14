# hemanth Bot 🚀

hemanth is a high-performance, feature-rich Telegram bot for mirroring and leeching, now upgraded with **Sequential Merge** and a **Premium UI**.

## 🌟 Premium Features
- **Sequential Merge**: Automatically merge video files in natural order (1, 2, 10...) losslessly using FFmpeg.
- **Premium UI**: Attractive Red & Blue progress bars with premium emojis.
- **Enhanced Speed**: Optimized with multiple workers for faster processing.
- **Multi-Service Support**: Support for Gdrive, Rclone, YouTube, GoFile, and more.

## 🛠 Deployment Guide

### 1. VPS Deployment (Recommended)
#### Using Termius / SSH
1. **Update System:**
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
2. **Install Docker:**
   ```bash
   curl -fsSL https://get.docker.com -o get-docker.sh
   sh get-docker.sh
   ```
3. **Clone Repo:**
   ```bash
   git clone https://github.com/hemanthbreakerd/LEECHNEW hemanth && cd hemanth
   ```
4. **Configure:** Edit `config.py` with your credentials.
5. **Build & Run:**
   ```bash
   docker build . -t hemanth
   docker run -p 80:80 hemanth
   ```

#### Using Termux (Android)
1. **Setup Environment:**
   ```bash
   pkg update && pkg upgrade
   pkg install docker python git
   ```
2. **Follow VPS steps** above (Note: Docker on Termux requires root/proot).

### 2. Heroku Deployment
1. Create a Heroku account and install [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli).
2. Login: `heroku login`.
3. Create App: `heroku create my-bot-name`.
4. Set Stack: `heroku stack:set container`.
5. Push Code: `git push heroku main`.

### 3. Koyeb Deployment
1. Create a Koyeb account.
2. Connect your GitHub repository.
3. Choose **Docker** as deployment method.
4. Add your Environment Variables in the Koyeb dashboard.
5. Click **Deploy**.

## ⚙ Configuration
Refer to the `docs/CONFIGURATIONS.md` for detailed variable explanations.

## 🤝 Support & Credits
- **Developer:** hemanth
- **Channel:** [@alonekingstar77](https://t.me/ALONEKINGSTAR77)
- **Base Project:** Original developers of Mirror-Leech-Telegram-Bot.

## 📄 License
This project is licensed under the MIT License.
