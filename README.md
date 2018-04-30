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
| artemis_home | string | ```/opt``` | Artemis home |
| artemis_brokers | list | see defaults | List of brokers to install (you can install multiple instances if you want to) |

### Broker instance default configuration

| Variable     | type | Default       | Description    |
| ------------ | ---- |------------- | -------------- |
| artemis_host | string | ```0.0.0.0``` | Artemis host |
| artemis_port_artemis | number | 61616 | Tcp port |
| artemis_port_amqp | number | 5672| Amqp port |
| artemis_port_stomp | number | 61613 | Stomp port |
| artemis_port_hornetq | number | 5445 | HornetQ port |
| artemis_port_mqtt | number | 1883 | Mqtt port |
| artemis_acceptors | list | see defaults | List of artemis acceptors for the broker (amqp, mqtt, ...) |
| artemis_web_port | number | 8161 | http web port (used for jolokia, console ui) |
| artemis_web_host | string | localhost | http web port (used for jolokia, console ui) |

## Example Playbook

### Basic install

```yaml
    - hosts: artemis-servers
      roles:
        - { role: artemis }
```

### Multi-instances

```yaml
    - hosts: artemis-servers
      roles:
        - { role: artemis }
```

## License

BSD
