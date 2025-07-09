# Webhook Receiver – GitHub Event Tracker

This repository ([webhook-repo](https://github.com/YashSNarkhede/webhook-repo)) contains a Flask-based application that listens for GitHub events via webhooks, stores them in MongoDB, and displays the latest activity on a minimal frontend.

## 🔗 Related Repository

This project is connected to my GitHub repository [action-repo](https://github.com/YashSNarkhede/action-repo), which triggers webhook events on Push, Pull Request, and Merge actions.

---

## 💡 Features

- Handles GitHub **Push**, **Pull Request**, and **Merge** events
- Stores formatted messages in **MongoDB**
- Frontend polls and displays latest events every 15 seconds
- Clean, minimal UI (HTML + JS)

---

## ⚙️ Tech Stack

- Python 3.11
- Flask
- MongoDB (Atlas)
- Ngrok (for local tunnel)
- GitHub Webhooks

---

## 📋 Event Message Format

- **Push**  
  `{author} pushed to {branch} on {timestamp}`  
  ➤ Example: `"YashSNarkhede pushed to main on 9 July 2025 - 08:23 AM UTC"`

- **Pull Request (Opened)**  
  `{author} submitted a pull request from {from_branch} to {to_branch} on {timestamp}`

- **Merge**  
  `{author} merged branch {from_branch} to {to_branch} on {timestamp}`

---

## 🚀 How to Run Locally

1. Clone this repo and install requirements:
    ```bash
    git clone https://github.com/YashSNarkhede/webhook-repo.git
    cd webhook-repo
    pip install -r requirements.txt
    ```

2. Add your MongoDB connection string in `config.py`:
    ```python
    MONGO_URI = "mongodb+srv://<xxxx>:<xxxx>@cluster0.yfxg5ck.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0"
    ```

3. Start Flask:
    ```bash
    python app.py
    ```

4. In another terminal, run ngrok:
    ```bash
    ngrok http 5000
    ```

5. Copy the HTTPS Ngrok URL and add it as a webhook to your `action-repo`:
    - Payload URL: `https://8495e4c91797.ngrok-free.app/webhook`
    - Content type: `application/json`
    - Events: Push, Pull request

6. Visit [http://localhost:5000](http://localhost:5000) to view updates

---


