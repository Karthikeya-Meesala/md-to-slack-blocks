# md-to-slack-blocks

A simple python library to convert markdown to the Slack blocks.

## Install

```bash
pip install md-to-slack-blocks
```

## How to Use

```python
from md_to_slack_blocks import md_to_blocks, is_markdown

# Basic conversion
markdown_text = """
# Hello World

This is a simple message with **bold** text.
"""

blocks = md_to_blocks(markdown_text)

# Send to Slack using requests
import requests

response = requests.post(
    'https://slack.com/api/chat.postMessage',
    headers={'Authorization': 'Bearer YOUR_SLACK_TOKEN'},
    json={
        'channel': '#deployments',
        'blocks': blocks
    }
)

# Check if text contains markdown
has_markdown = is_markdown("**Bold text**")  # True
```

## What's Supported

- Headers (`# ## ###`)
- Bold (`**text**`) and italic (`*text*`)
- Code blocks (` ``` `)
- Inline code (`` `code` ``)
- Block quotes (`> text`)
- Links (`[text](url)`)
- Horizontal rules (`---`)
- Strikethrough (`~~text~~`)

## Contributing

Contributions are welcome! Feel free to open an issue or submit a PR with a clear description.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).


