# TD-LaunchControl-utility
A utility for integrating Novation LaunchControl XL with TouchDesigner, allowing easy mapping of knobs and sliders.

## Japanese Documentation
[日本語版ドキュメント](README_JP.md) <br>
日本語版ドキュメントは英語版から情報を抜粋していたり、更新が遅れていたりすることがあります。<br>
参考までにご覧ください。正確な情報については以下の英語版をご覧ください。

## Usage

1. Connect LaunchControl XL to your computer.

2. Set your LaunchControl XL to `User Mode 1`.

3. In TouchDesigner, navigate to the `Dialogues` menu and select `MIDI Device Mapper`.

4. Create a new mapping and set the `Input Device` to `LaunchControl XL`.

5. Place `launchcontrol_master.tox` at the same level or a higher level in the directory hierarchy of the path where you will use this utility within your TouchDesigner project.

    For example, you may put it in `project1`.

6. In `launchcontrol_master.tox`, set the `Device ID` and `MIDI Channel` of your LaunchControl XL.

    If the utility doesn't work correctly, press `Reset` in `launchcontrol_master.tox`.

7. Place `launchcontrol_select.tox` anywhere you want to assign the value of the knobs or sliders.

8. Open `Custom` page in `launchcontrol_select.tox`.

9. Set the following parameters:

    - **Master OP Name**: Enter `LaunchControl_master`.
    - **Depth Level**: Set the number of levels up in the directory hierarchy from the current location of `launchcontrol_select.tox` to where `launchcontrol_master.tox` is located. For example, if `launchcontrol_master.tox` is located two levels up, set `Depth Level` to `2`.
    - **Control Group**: Select the group of the desired knob or slider.
    - **Control Number**: Select the number of the desired knob or slider.
    - **Output Mode**: Choose one of the following modes:
        - **Unipolar**: Output values linearly within the `Unipolar Range`.
        - **Bipolar** (Only for knobs): Output `Bipolar Center` when the knob is set to the center click position and output within the range of `Bipolar Range`.
        - **Exponential**: Output values exponentially with the ratio of `Exponential Min-Max Ratio` within `Exponential Range`.
    - **Output Lag**: Set the lag time for the output.
    - **Output Filter Width**: Set the width of the filter applied to the output.

10. Use the values from the knobs or sliders by either:

    - Connecting to the output of `launchcontrol_select.tox`.
    - Using Export CHOP directly from `launchcontrol_select.tox`.

## License
MIT License

## About Owner
monoton  
music producer, DJ & VJ, (virtual) experience design, generative visual design  
[Linktree](https://linktr.ee/monoton)

### Support me
If you find this project useful, please consider buying me a coffee!

<a href="https://www.buymeacoffee.com/monoton" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>
