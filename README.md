# TouchDesigner-LaunchControl-Utility

A utility for integrating Novation LaunchControl XL with TouchDesigner, allowing easy mapping of knobs and sliders.

## Trademark
Launch Conrtol is a registered trademark of Focusrite. This project is not affiliated with or endorsed by Focusrite.

## Japanese Documentation
日本語のドキュメント（参考版）もあります。  
[日本語ドキュメント](README_JP.md)

## Compatibility
This tool is confirmed to work with Novation LaunchControl XL MK2. Other types of LaunchControl XL may not be compatible with this tool. The tox files and the example project file were made with TouchDesigner in version 2023.11600.

## Usage
For usage examples, see inside the `example.toe`.

### Step 1: Connect LaunchControl XL to your computer
- Set your LaunchControl XL to `User Mode 1`.

### Step 2: Configure MIDI Device Mapper in TouchDesigner
- Navigate to the `Dialogues` menu and select `MIDI Device Mapper`.
- Create a new mapping and set the `Input Device` to `LaunchControl XL`.

### Step 3: Set up the Master Component
- Place `launchcontrol_master.tox` at the same level or a higher level in the directory hierarchy of the path where you will use this utility within your TouchDesigner project. For example, place it in `project1`.

### Step 4: Configure the Master COMP
- In `launchcontrol_master.tox`, set the `Device ID` and `MIDI Channel` of your LaunchControl XL.
- If the utility doesn't work correctly, press `Reset` in `launchcontrol_master.tox`.

### Step 5: Set up the Selector Component
- Place `launchcontrol_select.tox` anywhere you want to assign the value of the knobs or sliders.

### Step 6: Configure the Selector Component
- Open the `Custom` page in `launchcontrol_select.tox` and set the following parameters:
    - **Master OP Name:** Enter `LaunchControl_master`.
    - **Depth Level:** Set the number of levels up in the directory hierarchy from the current location of `launchcontrol_select.tox` to where `launchcontrol_master.tox` is located. For example, if `launchcontrol_master.tox` is located two levels up, set `Depth Level` to `2`.
    - **Control Group:** Select the group of the desired knob or slider.
    - **Control Number:** Select the number of the desired knob or slider.
    - **Output Mode:** Choose one of the following modes:
        - **Unipolar:** Output values linearly within the `Unipolar Range`.
        - **Bipolar** (Only for knobs): Output `Bipolar Center` when the knob is set to the center click position and output within the range of `Bipolar Range`.
        - **Exponential:** Output values exponentially with the ratio of `Exponential Min-Max Ratio` within `Exponential Range`.
    - **Output Lag:** Set the lag time for the output.
    - **Output Filter Width:** Set the width of the filter applied to the output.

### Step 7: Use the Values from the Selector Component
- You can use the values by either:
    - Connecting to the output of `launchcontrol_select.tox`.
    - Using Export CHOP directly from `launchcontrol_select.tox`.

## License
This project is licensed under the MIT License.

## About the Developer
### monoton  
music producer, DJ & VJ, (virtual) experience design, generative visual design  
[Linktree](https://linktr.ee/monoton)

### Support
If you find this project useful, please consider buying me a coffee!

<a href="https://www.buymeacoffee.com/monoton" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>
