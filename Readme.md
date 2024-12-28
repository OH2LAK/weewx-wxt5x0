## wxt5x0 - driver for Vaisala WXT-series Weather Transmitters for WeeWX

Copyright 2017-2024 Matthew Wall

Modifications by Erik Finskas 2024 to add TCP option to connect to a TCP serial server instead of using a local serial port

Distributed under terms of the GPLv3

### Installation

#### 1) Install the the driver

```
weectl extension install https://github.com/OH2LAK/weewx-wxt5x0/archive/master.zip
```

#### 2) Configure weeWX to use the driver
```
weectl station reconfigure
```
> [!TIP]
> If you are having difficulties getting the WXT5x0 driver to show on the list of available drivers use this workaround:
> ```
> ln -s /etc/weewx/bin/user/wxt5x0.py /usr/share/weewx/weewx/drivers/wxt5x0.py
> ```
> For some reason the user driver installation path is not visible for the configuration script, this symbolic linking will link the installed user driver to the built-in driver directory to enable the configuration of the wxt5x0 driver.
>
> Rerun the command `weectl station reconfigure` after linking and the wxt5x0 driver should be visible as 13th driver on the list

#### 3) Restart weeWX
```
sudo systemctl restart weewx
```
