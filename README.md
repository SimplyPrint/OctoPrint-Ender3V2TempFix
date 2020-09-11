# OctoPrint-Ender3V2TempFix
Fixes the double temperature reporting from the Creality Ender-3 v2 printer described in [this OctoPrint forum issue](https://community.octoprint.org/t/temperature-reporting-now-working-with-new-ender-3-v2/21053).

Some of the newer Creality firmware has an issue where, when reporting its temperature, it writes everything twice.
Example; _should report tool; 27.76, bed; 39.35
```
TT::27.7627.76  //0.000.00  BB::39.3539.35  //0.000.00  @@::00  BB@@::00
```

This plugin turns the input into the correct format, like this;
```
T:23.84 /0.00 B:24.05 /0.00 @:0 B@:0
```


**This fix is confirmed to work for the following printers:**
- Creality Ender-3 Pro v2
- Creality CR-6
