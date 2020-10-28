# Sabertooth 2x32 usb motor driver [![Build Status](https://travis-ci.org/frankjoshua/ansible-role-ros-sabertooth-usb.svg?branch=master)](https://travis-ci.org/frankjoshua/ansible-role-ros-sabertooth-usb)<br>

Deploys Docker container with Sabertooth 2x32 usb motor driver

## Requirements

See [requirements.yml](requirements.yml)

## Role Variables

By default we assume that the master is the Robot and use the host ip. This can be changed by setting these variables.

```
ros_ip: "{{ ansible_default_ipv4.address | default('127.0.0.1') }}"
ros_master_uri: 'http://{{ ros_ip }}:11311'
docker_name: 'ros_sabertooth_usb'
pull_image: false
docker_image: 'frankjoshua/ros-sabertooth-usb:latest'
```

## Dependencies

[requirements.yml](requirements.yml)

## Example Playbook

```
    - hosts: robot
      roles:
         - { role: ansible-role-sabertooth-usb, ros_master_uri: "http://10.10.10.100:11311" }
```

## Testing

`molecule test`

To trouble shoot issues.

```
molecule converge
molecule verify
molecule login
```

## License

Apache 2.0

## Author Information

Joshua Frank [@frankjoshua77](https://www.twitter.com/@frankjoshua77)
<br>
[http://roboticsascode.com](http://roboticsascode.com)
