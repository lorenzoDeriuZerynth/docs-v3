# Watchdog

Watchdogs are timers that reset the device if they are not manually restarte, a.k.a. kicked.
The watchdog is initialized by the bootloader thanks to some `config.yml` macros.
Moreover the watchdog is setup to a different time windows at startup.
In an infinite loop the sleeping time is always increased until it is longer than the watchdog window and the device resets.


More information about modules used in this demo:

- [Watchdog](../../libs/stdlib/watchdog.md)

```python
# main.py
import watchdog
import mcu

# Set Watchdog timeout after 15 seconds.
watchdog.setup(15000)

print("Hello Watchdog!")

# Check is the watchdog triggered.
trig = mcu.reset_reason() == mcu.RESET_WATCHDOG
print("Triggered: ", trig)

delay = 1000

while True:
    print("Delaying for ", delay)
    sleep(delay)
    watchdog.kick()
    delay = delay + 8000
```


By default the watchdog is set to 9000 milliseconds by the Zerynth OS.
In order to set a custom watchdog time during the early system startup, the macro `ZERYNTH_EARLY_WATCHDOG` can be added into `config.yml`

```yml
# config.yml
config:
    ZERYNTH_EARLY_WATCHDOG: 5000

```
