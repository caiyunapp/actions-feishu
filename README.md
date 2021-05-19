# actions-feishu

[![Lint](https://github.com/xiachufang/actions-feishu/actions/workflows/lint.yml/badge.svg)](https://github.com/xiachufang/actions-feishu/actions/workflows/lint.yml)

通过 GitHub Actions 来发送消息到飞书

# Quick start

Actions 配置样例：

```yaml
    - name: feishu notify
      uses: xiachufang/actions-feishu@v1.2
      with:
        webhook: ${{ secrets.FEISHU_WEBHOOK }}
        title: I'm title
        content: |
          I'm message body

          from: ${{ github.repository }}

```

# Configuration

## Inputs

| Variable | Required | Description |
| :---: | :---: | :----: |
| `webhook`| **true** | webhook address |
| `title` | **false** | title of message|
| `content` | **true** | content of message|
| `message_type`| **false**| message type, optional: `post`, `text`, `__custom__req__`, default: `post`|
| `msg_template_path`| **false**| message template path, only work when `message_type` is `__custom__req__`|
| `msg_template_values`| **false**| message template fillings, , only work when `message_type` is `__custom__req__`|

## Outputs

| Variable  | Description |
| :---:  | :----: |
| `response` | API response from feishu |
