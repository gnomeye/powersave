## powersave

My configuration for maximizing the battery life on my Thinkpad T430s.

Dependencies: [http://github.com/vodik/backlight utilities][backlight-utilities from vodik].

A `PKGBUILD` is included as a convenience.

### /etc/udev/rules.d/50-powersave.conf

start powersave script on power_supply=0/1

### /usr/bin/powersave

powersave script with powersaving settings

