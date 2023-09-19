# ms912x-python
Control a MacroSilicon ms912x-based USB-VGA/HDMI adapter (534d:6021) using Python

This program is completely based on rhgndf's [ms912x](https://github.com/rhgndf/ms912x) Linux DRM driver. Because I wasn't able to make it work and only needed to display some static images anyway, I tried to rewrite its functionality in Python using `pyusb`.

This is not a "driver" for the adapter, so you can't use it to display your desktop or anything like that.

So far this ipynb notebook is just a weird collection of half-working code that I'm using to try and figure out how it works, I'm still working on it and hopefully a cleaner version will come out soon.

After plugging it in, I currently need to click "restart kernel and run all cells" three times until it works (I have no idea how USB is supposed to work)
1. `USBError: [Errno 19] No such device (it may have been disconnected)` when calling power_on()
2. `USBTimeoutError: [Errno 110] Operation timed out` when calling ep.write()
3. On the third try, it magically works
