
### auto scan wifi (event has connected)

```ini
! turn it off to make laptop stop scanning wifi connect
netsh wlan set autoconfig enabled=no interface="Wi-Fi"

! turn on
netsh wlan set autoconfig enabled=true interface="Wi-Fi"
```