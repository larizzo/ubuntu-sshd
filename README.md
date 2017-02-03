# ubuntu-sshd

Dockerized SSH service, built on top of [official Ubuntu](https://registry.hub.docker.com/_/ubuntu/) images.

## Installed packages

Base:

- [trusty (14.04) minimal](http://packages.ubuntu.com/trusty/ubuntu-minimal)

Image specific:
- [openssh-server](https://help.ubuntu.com/community/SSH/OpenSSH/Configuring)

Config:

  - `PermitRootLogin yes`
  - `UsePAM no`
  - exposed port 22
  - default command: `/usr/sbin/sshd -D`
  - root password: `R]E7FxHK`

## Run example

```bash
$ sudo docker run -d -P --name test_sshd larizzo/ubuntu-sshd
$ sudo docker port test_sshd 22
  0.0.0.0:49154

$ ssh root@localhost -p 49154
# The password is `R]E7FxHK`
root@test_sshd $
```
