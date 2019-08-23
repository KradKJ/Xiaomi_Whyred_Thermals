INFERNO THERMALS

Modified thermal config files to solve slow charging issue on the Xiaomi Redmi Note 5 Pro/Global/CN (Amperage getting capped to 200/400ma randomly).
Mostly stock except some charging tweaks.

Check "Tweaking thermal-engine-normal.conf" commit for all the explanation about changes and other commits are based on that.

Main thermal file being used is "thermal-engine-normal.conf". This can be checked by going to sys -> class -> thermal -> thermal_message -> sconfig (0 means thermal-engine-normal.conf being used) and this mapping can be found in "thermal-engine-map.conf". Other file of relevance is "thermal-engine.conf" which is used in absence of "thermal-engine-normal.conf". Other files aren't used so they can be safely removed or just left as it is. For assurance, you can install MIUI global stable ROM and check the thermal files present in vendor -> etc or test yourself(both the above present and thermal-engine.conf empty by default). In China MIUI ROMs, you'll see an additional "thermal-engine-sgame.conf" but not used.

The above unused files can be put to use by apps that change the sconfig or with FK Kernel Manager's thermal profile section or I'm seeing ROMs these days which can switch thermal profiles for each app hence decided to keep them with each one slightly tweaked to fix slow charging.

Thanks to @NAHSEEZ and @MyCats for implementing these in their awesome ROMs. These are stock thermals with some charging tweaks so feel free to use these :)

Random Info:

-Won't work with kernels using simple thermals as they completely ignore thermal files.

-Phone starts charging slowly after 70-75ish% and as the battery gets full, charging speed reduces further. Completely normal behaviour and tested without any thermals at all and got the same result. For a temporary fix, unplug and plug charger and charging speed will slightly increase again. Don't want to fiddle with this as this behaviour is good for overall battery health.

-Please remove any other thermal mods/modules before installing as they'll interfere.
