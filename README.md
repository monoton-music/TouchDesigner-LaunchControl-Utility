# TD-LaunchControl-utility
A utility for integrating Novation LaunchControl XL with TouchDesigner, allowing easy mapping of knobs and sliders.

## Usage

1. Connect LaunchControl XL to your computer.

2. Set your LaunchControl XL to `User Mode 1`.

3. In TouchDesigner, navigate to the `Dialogues` menu and select `MIDI Device Mapper`.

4. Create a new mapping and set the `Input Device` to `LaunchControl XL`.

5. Place `launchcontrol_master.tox` at the same level or a higher level in the directory hierarchy of the path where you will use this utility within your TouchDesigner project.

    For example, you may put it in `project1`.

6. In `launchcontrol_master.tox`, set the `Device ID` and `MIDI Channel` of your LaunchControl XL.



## License
MIT Lisence

## About Owner
monoton
music producer, DJ & VJ, (virtual) experience design, generative visual design <br>
[Linktree](https://linktr.ee/monoton)

### Support me
If you find this project useful, please consider buying me a coffee!

<a href="https://www.buymeacoffee.com/monoton" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>
