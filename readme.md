# XIAO BLE 10440 (AAA) adapter for Bastard Keyboard Dactyls

Wireless XIAO Bluetooth holder PCB for Bastard Keyboards TBK Mini and Skeletyl (not tested). Scylla should otherwise work too, but the power switch can't be operated.

Modified from the [original Elite-C-holder](https://github.com/Bastardkb/Elite-C-holder) by [Bastard Keyboards](https://bastardkb.com/), Quentin Lebastard and Alexander Krikun.

It encompasses an AAA battery holder for 3.7V 10440 Li-ion battery. As most of the 10440 Li-ions I found don't have protection circuits built in, I added a protection circuit for the battery based on the reference design of a [AP9101CAK6](https://www.mouser.fi/ProductDetail/621-AP9101CAK6BVTRG1) protection IC.

**I have no idea what I'm doing, so this is probably not safe and fine!**. Use at your own risk, or better yet, don't use at all. I claim no responsibility of any damage caused by this.

The original Elite C adapter supports Nice!nano and LiPO. Please consider using it instead.

![holder](pics/xiao-aaa-kicad.png)

The power switch is accessible through the open side of the TBK Mini and Skeletyl.

![power switch position](pics/xiao-aaa-power-switch.jpg)


## Status

Initially tested as working.


## Firmware

ZMK Module coming soon.


## BOM & building

@TODO BOM


As the XIAO is mounted flush with the adapter pcb, there are two through-holes for XIAO positive battery and reset connections. They are meant to be soldered from the connector to the plated side wall of the through-hole.

![xiao bottom connections](pics/xiao-bottom-connections.jpg)


## Removed features

I made this for my specific use case with my TBK mini, not as universal solution. As the XIOA has much less pins than the Elite C based MCUs, the features were heavily cut to a minimum.

I also don't generally use or need the removed features in wireless builds because of missing support or battery drain, although they would make more sense here with the added capacity of the 10440 battery. Maybe in a future revision?

It would be possible to have more pins and therefore retain the features by using a shift register (ZMK supports this), but at least for this first version, I was in a hurry and did not bother.

- Removed audio socket (as ZMK and batteries are wireless only).
- Removed RGB support.
- Removed Trackball support.
- Removed handedness resistor.


## Future improvements

Things I'd like to change if doing it again.

- Find a toggle push button fitting through the unused audio socket hole to be used as the power switch.
- If still using the current slide power switch, swap it around so that "on" is facing away from you.
- Add RGB support either by dropping the row pin unused by TBK Mini and Skeletyl (dropping Scylla support) or by using a shift register for the matrix.
  - 10440 might have enough capacity for this to make some sense after all?
  - The leds have a minimum supply voltage of ~3.4V, how could that be handled?


# License

CERN Open Hardware Licence Version 2 - Weakly Reciprocal
