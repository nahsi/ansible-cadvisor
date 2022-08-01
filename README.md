# cadvisor

Install, configure and maintain
[cadvisor](https://github.com/prometheus/cadvisor)

## Role Philosophy

Please see
[ansible-consul](https://github.com/nahsi/ansible-consul#role-philosophy).

## Role Variables

See [defaults/](https://github.com/nahsi/ansible-cadvisor/blob/master/defaults/)
for details.

#### `cadvisor_version`

- version to use

#### `cadvisor_checksum`

- cadvisor binary checksum, you can get it from the [release page](https://github.com/google/cadvisor/releases)
- example:

```yaml
cadvisor_checksum: "sha256:65109ea14132bce91bb2a92dc70248c705ba26fb2a7d55e295bf4192940a396c"
```

#### `cadvisor_dirs`

- a map of directories to create
- default:

```yaml
cadvisor_dir: "/opt/cadvisor"
cadvisor_dirs:
  certs:
    path: "{{ cadvisor_dir }}/certs"
  textfile:
    path: "{{ cadvisor_dir }}/textfile"
  logs:
    path: "/var/log/cadvisor"
```

#### `cadvisor_options`

- [options](https://github.com/google/cadvisor/blob/master/docs/runtime_options.md)

#### `cadvisor_port`

- default:

```yaml
cadvisor_port: 9280
```

#### `cadvisor_user`

- owner of cadvisor process and files
- default: `cadvisor`

#### `cadvisor_group`

- group of `cadvisor_user`
- default: `cadvisor`

#### `cadvisor_groups`

- list of groups to add cadviser user to

#### `cadvisor_service`

- openrc service file

#### `cadvisor_unitfile`

- systemd unit file
- default: see
  [defaults/main.yml](https://github.com/nahsi/ansible-cadvisor/blob/master/defaults/main.yml)

#### `skip_handlers`

- skip restart/reload - useful when building images with Packer
- default: `false`

## Tags

- `config` - update cadvisor unit/service

## Author

- **Anatoly Laskaris** - [nahsi](https://github.com/nahsi)
