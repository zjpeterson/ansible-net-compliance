# Ansible Role: net_compliance

Runs configuration compliance tasks:
* Select network resources (currently just `ntp_global`)
* Purges all local users other than `admin`

Makes changed data available for use in subsequent tasks (specifically the `net_snow` role).

Generates a summary table of results.

## Credentials

As the inventory items running with this role will be network devices, provide a Machine credential (Tower/Controller) or set `ansible_user` / `ansible_password`.

## Defaults

**See `defaults/main.yml` for default values**

| Variable | Type | Description
| -------- | ---- | -----------
net_set_table | boolean | Whether or not to generate the summary table
net_sw_ver | dictionary | Intended software versions by network OS
net_ntp_vrf | string | NTP VRF (`ansible_network_os==cisco.nxos.nxos` only)
net_ntp | complex | See module documentation for `<ansible_network os>_ntp_global`
