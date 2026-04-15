# hemanth Bot 🚀 [Optimized Version]

hemanth is a high-performance, feature-rich Telegram bot for mirroring and leeching, now upgraded with an advanced **Video Tools (-vt)** system and a **Premium UI**.

## 🌟 Key Features
- **Video Tools Module (-vt)**: Complete suite for merging, trimming, and audio processing.
- **Auto Audio Split**: Automatically detect and split multiple audio tracks into separate video files.
- **Auto Merge**: Intelligent directory merging for sequential video parts.
- **Premium UI**: Attractive Red & Blue progress bars with premium emojis.
- **FFmpeg Integration**: Lossless processing using the custom `xtra` binary.
- **Multi-Service Support**: Gdrive, Rclone, YouTube, GoFile, and more.

---

## 🛠 Deployment Guide

### 1. VPS / Dedicated Server (Recommended)
#### Using Termius / SSH
1.  **Update System & Install Docker:**
    ```bash
    sudo apt update && sudo apt upgrade -y
    curl -fsSL https://get.docker.com -o get-docker.sh
    sh get-docker.sh
    ```
2.  **Clone the Repository:**
    ```bash
    git clone https://github.com/hemanthbreakerd/LEECHNEW hemanth && cd hemanth
    ```
3.  **Configure Environment:**
    - Edit `config.py` with your `BOT_TOKEN`, `OWNER_ID`, `TELEGRAM_API`, `TELEGRAM_HASH`, etc.
    - Or use the `/botsettings` command after the first run.
4.  **Build & Launch with Docker:**
    ```bash
    docker build . -t hemanth
    docker run -d --name hemanth-bot -p 80:80 hemanth
    ```

### 2. Termux (Android)
1.  **Prepare Termux:**
    ```bash
    pkg update && pkg upgrade
    pkg install git python ncurses-utils
    ```
2.  **Setup Docker (Requires Root or Proot):**
    - It is recommended to use a VPS for production, but for local testing:
    - Follow the VPS steps above within a Proot environment (like Ubuntu).
3.  **Run Directly (No Docker):**
    ```bash
    pkg install ffmpeg python-pip
    pip install -r requirements.txt
    python3 -m bot
    ```

### 3. Koyeb Deployment
1.  Sign up for a [Koyeb account](https://app.koyeb.com/).
2.  Click **Create Service** and select **GitHub** as the source.
3.  Choose your repository and the `main` branch.
4.  In **Build & Run Settings**, select **Docker**.
5.  Add your **Environment Variables** (matches `config.py` keys).
6.  Set **Expose Port** to `80` (TCP).
7.  Click **Deploy**.

### 4. Heroku Deployment
1.  [Fork](https://github.com/hemanthbreakerd/LEECHNEW/fork) the repo and star it.
2.  Open the **Actions** tab in your fork.
3.  Select **Deploy to Heroku** from the list on the left.
4.  Click **Run workflow** and enter:
    - `BOT_TOKEN`, `OWNER_ID`, `DATABASE_URL`, etc.
    - `HEROKU_APP_NAME`, `HEROKU_EMAIL`, `HEROKU_API_KEY`.
5.  Wait for the build to finish. Enable the worker in Heroku dashboard.

---

## 🎬 Video Tools Module (-vt)

The system automatically detects the required tool based on the flags provided.

### Commands:
- `/l -vt` : Basic video processing (Auto extraction if no args).
- `/l -vt -m` : **Merge Mode** (Merges videos in the same folder).
- `/l -vt -ss 00:00:10 -to 00:01:00` : **Trim Mode** (Fast & Accurate).
- `/l -as` OR `/l -audiosplit` : **Auto Audio Split** (Splits multi-audio tracks).

### Rules:
1.  **Merge Mode (-m)**: Only works if `-m` is explicitly enabled. Works only on folder inputs.
2.  **Trimming**: If multiple videos are in a folder and `-m` is off, it processes **only the first video**.
3.  **Efficiency**: Uses `-c copy` whenever possible to avoid re-encoding and maximize speed.

---

## ⚙ Configuration
Detailed variable explanations are available in `docs/CONFIGURATIONS.md`.

## 🤝 Support
- **Developer:** hemanth
- **Channel:** [@alonekingstar77](https://t.me/ALONEKINGSTAR77)

## 📄 License
MIT License.
