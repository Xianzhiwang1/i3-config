
# My kmonad config

I have three layers (inspired by the `lily58` split keyboard layout,
and the `Corne` keyboard layout `https://mark.stosberg.com/markstos-corne-3x5-1-keyboard-layout/`):
the default: `qwerty` layer
numbers on the home row: `lower` layer
left down up right at hjkl: `raise` layer

### space key has dual functionality:

in the `qwerty` layer:
tap: acts as ordinary space key
hold: (more than 150 millisecond) toggles into the `raise` layer

in both `raise` layer and `lower` layer:
tap: acts as ordinary space key
hold: (more than 150 millisecond) toggles back to the `qwerty` layer

### `F1` key switches between `qwerty` layer and `lower` layer
### `F2` key switches between `qwerty` layer and `raise` layer

## the philosophy is we could use the thumb more,
use left thumb to hold the space key to toggle into `raise` layer,
then the right hand could easily type
`!@#$%`
    `12345`
        `_-+[{`,
and upon releasing the space key, we automatically gets back to the `qwerty` layer.

While use right thumb to hold the space key to toggle into `raise` layer,
then the left hand could easily type
            `^&*()`
                `67890`
                    `}],.=`,
and upon releasing the space key, we automatically gets back to the `qwerty` layer.

Hence, holding the space bar using our thumbs acts like Shift, but with different layers and keys.

use the following for `systemd`



# /etc/systemd/system/kmonad.service
[Unit]
Description=kmonad keyboard config

[Service]
Restart=always
RestartSec=3
ExecStart=/usr/bin/kmonad /etc/kmonad/keymap.kbd
Nice=-20

[Install]
WantedBy=default.target

