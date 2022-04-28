# Ansible Role: net_snow

Records change activity in ServiceNow. Intended for use with networking use cases, but could also be used for other tasks.

## Credentials

You are expected to provide the ServiceNow host and login information via environment variables, such as `SN_USERNAME`. Refer to the `servicenow.itsm` collection documentation.

FYI, there is a playbook available at https://github.com/zjpeterson/ansible-tower-credential-types/blob/main/playbook_servicenow.yml that will create a ServiceNow credential type in Ansible Tower.

## Defaults

Override these values as needed.

| Variable | Default | Description
| -------- | ------- | -----------
| snow_mode | incident | Either `incident` or `change`
| snow_group | Network | The group to assign the record to
| snow_category | network | The category for the record
| snow_req_user | ansible | The user to attach to the record
| snow_title | My Incident | The title for the record
| snow_description | My Description | The description for the record
| snow_notes | My Notes | What to place in the Work Notes before closing
| snow_urgency | medium | Incident urgency (`snow_mode==incident` only)
| snow_impact | medium | Incident impact (`snow_mode==incident` only)
| snow_priority | 3 | Incident priority (`snow_mode==incident` only)
