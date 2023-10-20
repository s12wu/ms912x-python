# ms912x-python
Control a MacroSilicon ms912x-based USB-VGA/HDMI adapter (534d:6021) using Python

This program is completely based on rhgndf's [ms912x](https://github.com/rhgndf/ms912x) Linux DRM driver. Because I wasn't able to make it work and only needed to display some static images anyway, I tried to rewrite its functionality in Python using `pyusb`.

This is not a "driver" for the adapter, so you can't use it to display your desktop or anything like that.

The usb device behaves very strangely, it seems to disconnect itself on setup. For example, I wasn't able to reliably forward it to a virtual machine (to test the official driver under Windows and rhgdnf's driver [under Ubuntu 20.04](https://github.com/rhgndf/ms912x/issues/2#issuecomment-1707399179)).

Because of this, this Python program does a series of `dev.reset()`s and repeats `usb.core.find`, for me it works pretty reliably like that.

