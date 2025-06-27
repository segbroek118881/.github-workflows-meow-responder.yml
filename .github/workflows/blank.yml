name: Meow Discord Autoresponder

on:
  issue_comment:
    types: [created]

jobs:
  respond_to_meow:
    runs-on: ubuntu-latest
    steps:
      - name: Check for "meow" and send "hi" to Discord
        env:
          DISCORD_WEBHOOK_URL: https://discord.com/api/webhooks/1388114306390032445/WEfgjR0sesNCffYZ0LLlLKnqzt-p9mXvRZa18gEYuJJ5iVaTDTUmEBtb7ICx6oJP99DL
        run: |
          COMMENT_BODY="${{ github.event.comment.body }}"
          if [ "$(echo "$COMMENT_BODY" | tr '[:upper:]' '[:lower:]')" = "meow" ]; then
            curl -H "Content-Type: application/json" -X POST -d '{"content": "hi"}' "$DISCORD_WEBHOOK_URL"
          fi
