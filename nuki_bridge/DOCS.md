# Home Assistant Virtual Nuki Bridge

Use this instead of the [Nuki Bridge](https://nuki.io/en/bridge/) device.

> Important - if you are experiencing delays using RPI, it is advised to use a bluetooth dongle instead of the builtin bluetooth hardware.
> [TP-LINK UB400](https://www.tp-link.com/us/home-networking/usb-adapter/ub400/) is verified to be working.

## Pairing

1. Press the button of the Nuki Smart Lock for 6 seconds. It should light up.
2. Run

   1. If installed as addon, click `start`
   2. If installed outside HA, run

      `python .`

3. Look in logs for:

   ```
   ********************************************************************
   *                                                                  *
   *                         Pairing completed!                       *
   *                            Access Token                          *
   * abcabcabcabcabcabcabcabcabcabcabcabcabcabcabcabcabcabcabcabcabca *
   *                                                                  *
   ********************************************************************
   ```

4. Copy the `Access Token` for a following step.

   In case you missed it, restart the service and check again.

5. Before moving on, you might need to restart the addon. First run is less stable.

## Nuki Addon

1. Install either
   1. [Official Home Assistant Nuki integration](https://www.home-assistant.io/integrations/nuki/)
   2. [hass_nuki_ng](https://github.com/kvj/hass_nuki_ng)
2. Configure the Nuki Addon:
   1. Paste your token from the log above
   2. Address is `127.0.0.1`

## Configuration

**Note**: _Remember to restart the add-on when the configuration is changed._

### Option: `adapter`

The `adapter` option points to the hci device id (i.e `hci0`)

### Option: `retry`

The `retry` sets the number of retires when sending commands to the Nuki device

### Option: `connection_timeout`

The `connection_timeout` sets the timeout on the connection attempt the Nuki device

### Option: `command_timeout`

The `command_timeout` sets the timeout on the command attempt the Nuki device
