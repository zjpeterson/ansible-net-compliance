# ansible-net-compliance

This is a Network Compliance demo I put together for Red Hat Automation Everywhere events, showcasing the following capabilities of Ansible:
* ServiceNow CMDB used as dynamic inventory
* Network Fact Gathering
* ServiceNow CMDB data population
* Multi-vendor compliance checking and enforcement
* ChatOps via Slack
* Recording of change activity in ServiceNow

**Please refer to the individual role READMEs for specific information on how they work.**

## Roles

### net_compliance
Runs configuration compliance with select network resources (currently just `ntp_global`) as well as local users (which are not considered to be a "resource"). Makes changed data available for use in subsequent tasks (specifically the `net_snow` role). Generates a summary table of results.

### net_snow
Records change activity in ServiceNow. Intended for use with networking use cases, but could also be used for other tasks.

### table_format
Formats inputted data into an ASCII table with correct spacing, for use in ChatOps applications.

## Playbooks

## playbook_compliance_snow.yml
Invokes `net_compliance` and then `net_snow` to record what it did.

### playbook_table_slack.yml
Invokes `table_format` in Slack mode to print results from `net_compliance`.
