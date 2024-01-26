# Homeassistant

This role installs Home Assistant on a remote server with all required dependencies and configures it to run as a service.

## Requirements

No requirements

## Role Variables

| Name                      | Default Value      | Description                                                                                                                                                                                              |
| ------------------------- | ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ha_user`                 | homeassistant      | The user which would created and run the homeassistant installation and service                                                                                                                          |
| `ha_group`                | homeassistant      | The group which would created                                                                                                                                                                            |
| `ha_port`                 | 8123               | the webaccess port                                                                                                                                                                                       |
| `ha_conf_dir`             | /srv/homeassistant | The config path, where homeassistant woud be installed                                                                                                                                                   |
| `ha_version`              | None               | A specified homeassistant which would be installed, recommendly use for updated to a higher version if the new version is not next version from the current installation.                                |
| `ha_backup`               | None               | a defined backup file from a homeassistant backup, which would be restored. Put backup file in the files folder from role and set filename in th variable                                                |
| `ha_additional_pi_groups` | dialout,gpio,i2c   | addiotion requrired groups for the homeassitent installation on a rasperry pi, do not change or overwrite the values                                                                                     |
| `ha_check_delay`          | 45                 | delay in seconds for waiting if Home Assistent is available                                                                                                                                              |
| `ha_python`               | 3.11               | The python version for homeassistant, if not available on the system it will be installed check recommend version [Python](https://www.home-assistant.io/installation/macos#install-home-assistant-core) |

## Dependencies

None

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

## minimal playbook.yml example

    - hosts: homeassistant_server
      become: true

      roles:
        - homeassistant

## extendet playbook.yml example

    - hosts: homeassistant_server
      become: true
      vars:
        ha_user: homeassistant
        ha_group: homeassistant
        ha_port: 8123
        ha_conf_dir: /srv/homeassistant
        ha_version: 2023.11.
        ha_backup: core_2022_9_7.tar
        ha_python: 3.11

      roles:
        - homeassistant

## License

MIT

## Author Information

Jan Roepke
have fun with it, and feel free to contribute or contact me.
