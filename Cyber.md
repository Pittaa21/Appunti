#### ssh connection:
```
ssh <user>@4.tcp.eu.ngrok.io -p 10264
```

#### togliere privilegi
```
sudo chmod 755 /home/<user>
sudo chown root:root /home/<user>
```

#### starting ssh
```
sudo systemctl enable --now sshd
sudo systemctl start sshd
```

#### starting ngrok
```
ngrok tcp 2200
```

#### users passwd
```
misc1   1234
misc2    //
  |     //
misc5   //

```
