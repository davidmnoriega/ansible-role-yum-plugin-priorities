# yum-plugin-priorities

Ansible role to manage yum repo priorities

## Requirements

None

## Role Variables

* `repositories`: A list of dictionaries that contain the name of the repo definition file, and the
various repos defined within and their priorities. The default data is of a fresh CentOS
installation.

* `additional_repos`(OPTIONAL): A list of the same form as `repositories`, its function is to allow
playbooks to specify additional repos that might be installed.

## Dependencies

None

## Example Playbook

This example playbook uses the role to set the priority of the EPEL repository to a priority of 10,
while also setting the base CentOS repositories to a priority of 1:
    - hosts: all
      become:
      vars:
        additional_repos:
          - name: epel
            priorities:
              - name: epel
                priority: 10
      roles:
         - yum-plugin-priorities

## License

MIT
