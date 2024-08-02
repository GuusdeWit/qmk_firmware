# Personal QMK config for Ferris Sweep

## Making Changes with Configurator
- Update configurator.json: `qmk c2json -o configurator.json keymap.c`
- Use configurator.json with the [qmk configurator](https://config.qmk.fm/)
- After making changes, download the new json
- Run `qmk json2c configurator.json`
- Copy the relevant changes to keymap.c

## Building and flashing
- Run `qmk compile`
- Open QMK Toolbox
- Make sure "/Users/guusdewit/Utility/qmk_firmware/ferris_sweep_guus_dewit.hex" is selected
- MCU ATmegan32U4
- Enable auto-flash
- Connect left module while holding top left button, disconnect when flash done
- Repeat for right module, with top right button

## From the old Readme

### How do I edit and update the keymap? (check last step if needed)

The `keymap.json` file is generated from the qmk configurator interface and formatted for better readability in the context of the Ferris keyboard.

To edit it, you may:
* Edit it directly from a text editor.
* Edit it from the qmk configurator.

If you decide to use the latter workflow, here are the steps to follow:

* From the qmk configurator, hit the "import QMK keymap json file" button (it has a drawing with an up arrow on it).
* Browse to the location of your keymap (for example, `<your qmk repo>/keyboards/ferris/keymaps/default/keymap.json`)
* Perform any modification to the keymap in the web UI
* Export the keymap to your downloads folder, by hitting the "Export QMK keymap json file" button (it has a drawing with a down arrow on it)
* Override your original keymap with the output of formatting the exported keymap by running a command such as this one from the root of your qmk repo:
  ```
  ./keyboards/handwired/ferris/keymaps/json2crab.py --input <Your download directory>/default.json > ./keyboards/handwired/ferris/keymaps/default/keymap.json
  ```
  Note that you may first need to make json2crab executable by using `chmod +x` on it.
  Also note that you may then want to remove the exported keymap from your dowload directory.
