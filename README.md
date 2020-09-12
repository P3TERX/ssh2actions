# SSH to GitHub Actions

This GitHub Action offers you connect to GitHub Actions VM via SSH for interactive debugging

## Features

- Support Ubuntu and macOS
- Provides two optional SSH connection methods, tmate and ngrok
- Proceed to the next step to stay connected
- Send SSH connection info to Telegram

## Usage

### Connect to Github Actions VM via SSH by using [tmate](https://tmate.io)

```yaml
- name: Start SSH via tmate
  uses: P3TERX/ssh2actions@main
  # Send connection info to Telegram (optional)
  # You can find related documents here: https://core.telegram.org/bots
  env:
    TELEGRAM_BOT_TOKEN: ${{ secrets.TELEGRAM_BOT_TOKEN }}
    TELEGRAM_CHAT_ID: ${{ secrets.TELEGRAM_CHAT_ID }}
```

### Connect to Github Actions VM via SSH by using [ngrok](https://ngrok.com)

```yaml
- name: Start SSH via ngrok
  uses: P3TERX/ssh2actions@main
  with:
    mode: ngrok
  env:
    # After sign up on the https://ngrok.com
    # You can find this token here: https://dashboard.ngrok.com/auth/your-authtoken
    NGROK_TOKEN: ${{ secrets.NGROK_TOKEN }}
    
    # ngrok server region [us, eu, au, ap, sa, jp, in] (optional, default: us)
    # You can find this server region here: https://ngrok.com/docs#global-locations
    NGROK_REGION: us

    # This password you will use when authorizing via SSH
    SSH_PASSWORD: ${{ secrets.SSH_PASSWORD }}

    # Send connection info to Telegram (optional)
    # You can find related documents here: https://core.telegram.org/bots
    TELEGRAM_BOT_TOKEN: ${{ secrets.TELEGRAM_BOT_TOKEN }}
    TELEGRAM_CHAT_ID: ${{ secrets.TELEGRAM_CHAT_ID }}
```

## Lisence

[MIT](https://github.com/P3TERX/ssh2actions/blob/main/LICENSE) © P3TERX
