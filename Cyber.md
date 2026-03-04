#### ssh connection:
```
ssh <user>@100.100.120.122 -p 2200
```

#### starting ssh
```
sudo systemctl enable --now sshd
sudo systemctl start sshd
```

#### starting tailscaled
```
sudo systemctl enable --now tailscaled
sudo tailscale up
```
