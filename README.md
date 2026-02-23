# structure

`inventory/hosts/` contains files specific to hosts, such as certain public
keys.  Contents here should be kept to a minimum.

`inventory/inventory.d/*.yml` are group definition files, one per group, named
for the group.

`inventory/inventory.d/vars` contains global variables.  The domain name and
time zone are set here, for example.

`inventory/inventory.d/host_vars/` contains host variable definition files, one
per host, named for the host, containing details like IP address, MAC address,
and platform.

# BUGS

Group names contain dashes.  Ansible will throw warnings and errors about this
by default, but those should be suppressed if possible.  Be careful, though:
Always refer to `groups['group-name']`, never to `groups.group-name`.  Python
variable names are not allowed to contain dashes.
