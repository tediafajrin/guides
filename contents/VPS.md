# VPS (Virtual Private Server)

## Niagahoster

- Register at https://niagahoster.co.id
- Choose VPS product as needed [here](https://niagahoster.co.id/cloud-vps-hosting)
- Login to your account [here](https://panel.niagahoster.co.id/login)
- Choose Layanan Anda > Cloud VPS > Kelola VPS
- Change **Root Password** with your new password
- Login to your VPS with : `ssh root@<ip>`

## Add new user

- `adduser debian`
- `usermod -aG sudo debian`
- `ssh debian@<ip>`

## SSH without password

- `ssh-keygen -t rsa`
- `ssh-copy-id -i ~/.ssh/id_rsa.pub debian@<ip>`

## Prevent SSH from disconnecting

- `ssh root@<ip>`
- `vim /etc/ssh/sshd_config`
- `ClientAliveInterval 60` & `ClientAliveCountMax 2`

## Run command as root

- `ssh root@<ip>`
- `visudo`
- `debian ALL=(ALL) NOPASSWD: ALL`

## Open port

- `ssh root@<ip>`
- `apt install ufw`
- `ufw allow 22` (for ssh)
- `ufw enable`
- `ufw allow 5432` (for single port)
- `ufw allow 8080:8090/tcp` (for range port)

## Fix locale

- `echo 'export LC_ALL=C' >> ~/.profile`
- `. ~/.profile`

#

&copy; [Tedi Fajrin](https://github.com/tediafajrin)