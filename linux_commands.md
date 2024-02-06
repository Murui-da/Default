# Linux Command Lines

## Add a sudouser

```bash
username="ubuntu"
password="foxy1"
useradd -m \
    -p "$(openssl passwd -1 ${password})" \
    -G sudo \
    -d /home/${username} \
    -k /etc/skel \
    -s /bin/bash \
    $username
echo $username ALL=\(root\) ALL > /etc/sudoers.d/$username
chmod 0440 /etc/sudoers.d/$username
```
