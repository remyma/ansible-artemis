# Ansible Activemq Artemis

Install and configure activemq artemis broker.

## Requirements

* *java* : artemis needs java to run.

## Role Variables

| Variable     | Default       | Description    |
| ------------ | ------------- | -------------- |
| artemis_version | ```2.3.0``` | Artemis version |
| artemis_download_url | | Download artemis archive url |

## Example Playbook

### Basic install

    - hosts: artemis-servers
      roles:
        - { role: artemis }

## License

BSD
