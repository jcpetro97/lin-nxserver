# ivansible.lin_nxserver

[![Github Test Status](https://github.com/ivansible/lin-nxserver/workflows/test/badge.svg?branch=master)](https://github.com/ivansible/lin-nxserver/actions)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-ivansible.lin__nxserver-68a.svg?style=flat)](https://galaxy.ansible.com/ivansible/lin_nxserver/)

This role provisions [nomachine](https://www.nomachine.com/) nxserver on a linux box.
Optionally, it installs `xvfb`.


## Requirements

None


## Role Variables

Available variables are listed below, along with default values.

    allow_reboot: true

If `true`, the script will reboot target host after critical upgrade.
Otherwise, the script will print a warning message and skip rebooting.

    lin_nxserver_deb_url: https://download.nomachine.com/download/6.6/Linux/nomachine_6.6.8_5_amd64.deb
URL of nxserver package.

    lin_nxserver_display: 1001
The role will add this `DISPLAY` variable to the user `bashrc` file.

    lin_nxserver_ports: [4000, 5353]
You will not usually change this.

    lin_nxserver_direct: true
If true, ports will be open for all. If false, ports will be blocked
from external networks.


## Tags

- `lin_nx_server` -- install nxserver package and open ports
- `lin_nx_user` -- authorize user
- `lin_nx_firewall` -- configure firewall for nxserver
- `lin_nx_desktop` -- install `xfce4` desktop environment
- `lin_nx_audio` -- enable audio interface in nxserver
- `lin_nx_all` -- all of above


## Dependencies

None


## Example Playbook

    - hosts: nxhost
      roles:
         - role: ivansible.lin_nxserver
           allow_reboot: false


## License

MIT

## Author Information

Created in 2018-2021 by [IvanSible](https://github.com/ivansible)
