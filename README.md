# Ansible Activemq Artemis

Install and configure activemq artemis broker.

## Requirements

* *java* : artemis needs java to run.

## Role Variables

### Service configuration

| Variable     | type | Default       | Description    |
| ------------ | ---- |------------- | -------------- |
| artemis_version | string | ```2.3.0``` | Artemis version |
| artemis_download_url | string | | Download Artemis archive url |
| artemis_group | dictionnary | see defaults| Artemis service group |
| artemis_user | dictionnary | see defaults | Artemis service user |
| artemis_install_dir | string | ```/opt``` | Artemis installation directory |
| artemis_home | string | ```{{ artemis_install_dir }}/apache-artemis-{{ artemis_version }}``` | Artemis home directory |
| artemis_brokers | list | see defaults | List of brokers to install (you can install multiple instances if you want to) |

### Broker default configuration

| Variable     | type | Default       | Description    |
| ------------ | ---- |------------- | -------------- |
| artemis_host | string | ```0.0.0.0``` | Artemis host |
| artemis_port_artemis | number | 61616 | Tcp port |
| artemis_port_amqp | number | 5672| Amqp port |
| artemis_port_stomp | number | 61613 | Stomp port |
| artemis_port_hornetq | number | 5445 | HornetQ port |
| artemis_port_mqtt | number | 1883 | Mqtt port |
| artemis_acceptors | list | see defaults | List of artemis acceptors for the broker (amqp, mqtt, ...) |
| artemis_journal_type | string | NIO | Journal type |
| artemis_journal_pool_files | string | 10 | Upper threshold of the journal file pool |

## Example Playbook

### Basic install

    - hosts: artemis-servers
      roles:
        - { role: artemis }

## License

BSD
