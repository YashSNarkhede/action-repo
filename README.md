# action-repo

This is a simple GitHub repository created to trigger webhook events for the developer assessment task.

It is connected to my Flask-based webhook listener (`webhook-repo`) using a GitHub webhook.

## 🔗 Linked Repository

- [Webhook Receiver (webhook-repo)](https://github.com/YashSNarkhede/webhook-repo)

## 🧪 How It’s Used

This repository is used to generate GitHub events for testing:

- **Push events** – by committing changes (e.g., to `test.txt`)
- **Pull request events** – by opening PRs from one branch to another
- **Merge events** – by merging pull requests into `main`

These events are captured by the webhook and stored in MongoDB.

## 🚀 Sample Commands Used

```bash
echo "testing push" >> test.txt
git add .
git commit -m "Test push"
git push origin main
