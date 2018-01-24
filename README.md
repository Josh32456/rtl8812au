# RTL8812AU/21AU and RTL8814AU linux driver with monitor mode and frame injection
`The master branch is based on https://github.com/ulli-kroll/rtl8821au branch v4.3.22-beta/rework.
According to rtw_version.c the real driver version is 4.3.20.`

# Info
`We recommend building from the v5.1.5 branch, which got kernel v4.12 support & more adapters supported. 
Both the 8812AU & 8814AU is supported on the v5.1.5 branch.`


The branch v4.3.21 may also be built for RTL8814AU or RTL8812AU/RTL8821AU chipset. 
Notice, kernel v4.12 support is still missing on the v4.3.21 branch.

for building RTL8812AU/RTL8821AU driver type:

`$ make`


for building RTL8814 driver type:

`$ make RTL8814=1`


for building driver with debug output type:

`$ make DEBUG=1`

or

`$ make RTL8814=1 DEBUG=1`

### TerraMon-NG (Monitor mode)

Installation:
```
# sudo cp terramon-ng /usr/bin
# sudo chmod +x /usr/bin/terramon-ng
```
You can then do
```
# terramon-ng --help
```
for more info

for setting TX power (v4.3.21 branch only):
```
$ sudo iwconfig wlan0 txpower 30
```
or
```
$ sudo iw wlan0 set txpower fixed 3000
```

to inject frames with b/g rates use the Rate field in the radiotap header

to inject frames with n rates use the MCS field in the radiotap header

to inject frames with ac rates use the VHT field in the radiotap header 

