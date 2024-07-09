# Guide: Flashing the Aldi Bauhn ASPWC2-0624

## Preparation and Disassembly
1. Open the device by removing two triangle head screws.
2. Remove two small Phillips head screws located in the corners near the USB ports.
3. Carefully desolder the Live, Neutral, and Earth terminals.

## Connecting for Flashing
4. Connect the following:
   - 3.3V power supply
   - Ground
   - Receive and transmit lines to a serial converter

![Flashing Setup](https://github.com/jamesy0ung/ASPWC2-0624-Reversing/blob/main/Flashing-Setup.jpg?raw=true)

## Flashing Process
5. Download the flashing tool from [GitHub](https://github.com/openshwprojects/BK7231GUIFlashTool)).

![BK7231 Flasher Tool](https://github.com/jamesy0ung/ASPWC2-0624-Reversing/blob/main/Flashtool.png?raw=true)

6. Open the flashing tool and navigate to "UART Timeouts". Set all values to 5 seconds.
7. Set the baud rate to 115200.
8. Perform a firmware write (no backup needed as a configuration is already provided).

## Device Configuration
9. After flashing, connect to the open access point created by the device.

![Device Main Page](https://github.com/jamesy0ung/ASPWC2-0624-Reversing/blob/main/Mainpage.png?raw=true)

10. Navigate to the device's IP address. Click on "Wifi setup" and enter your network details. 
    **Important**: Ensure all details are correct to avoid having to erase and reflash.

![WiFi Setup Page](https://github.com/jamesy0ung/ASPWC2-0624-Reversing/blob/main/Wifipage.png?raw=true)

11. Return to the device's IP address, click "IMPORT", and paste the following configuration:

![Configuration Import Page](https://github.com/jamesy0ung/ASPWC2-0624-Reversing/blob/main/Configpage.png?raw=true)

```json
{
    "sel_pin_pin":"24",
    "rl1_lv":"1",
    "bt1_pin":"10",
    "net_trig":"2",
    "jv":"1.0.7",
    "netled1_lv":"0",
    "netled_reuse":"1",
    "ffc_select":"0",
    "vi_pin":"6",
    "resistor":"1",
    "over_cur":"17300",
    "bt1_lv":"0",
    "reset_t":"3",
    "netled1_pin":"8",
    "chip_type":"0",
    "lose_vol":"100",
    "over_vol":"300",
    "module":"CB2S",
    "ele_pin":"7",
    "ch_cddpid1":"9",
    "ch1_stat":"2",
    "ch_num":"1",
    "ele_fun_en":"1",
    "rl1_pin":"26",
    "vol_def":"0",
    "ch_dpid1":"1",
    "sel_pin_lv":"1",
    "crc":"45"
}
```

## Finishing up
12. Reboot the device.

13. Confirm that everything works correctly.

14. Carefully resolder the terminals and reassemble the device.
