# Personal QMK config for Piantor Pro

## Making Changes with Configurator
- Update configurator.json: `qmk c2json -o configurator.json keymap.c`
- Use configurator.json with the [qmk configurator](https://config.qmk.fm/)
- After making changes, download the new json
- Run `qmk json2c configurator.json`
- Copy the relevant changes to keymap.c

## Building and flashing
- Run `make beekeeb/piantor_pro:guus_dewit` from home qmk folder
- Attach (left) keyboard and start boot loader
    - Use both layer buttons + Q
    - Unscrew back of case, and double tap reset button
- Copy over the generated uf2 file