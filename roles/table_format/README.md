# Ansible Role: table_format

Formats inputted data into an ASCII table with correct spacing, for use in ChatOps applications.

## Credentials

If using Slack, provide an appropriate API token in the variable `table_slack_token`.

## Defaults

Override these values as needed.

| Variable | Default | Description
| -------- | ------- | -----------
table_mode | debug | Either `debug` (console output) or `slack`
table_title | My Table | Title for the table
table_justify | `<` | Left or right justify data cells (`<` or `>`)
table_header | (list) | List of strings comprising the header row
table_data | (nested list) | Nested list of data rows to print
table_chat_channel | ansible | What channel to post in (`table_mode==slack` only)
table_slack_token | (Slack API token) | Slack API token (`table_mode==slack` only)
