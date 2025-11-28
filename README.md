BKPatch

My Improvements:

Build in Zygisk

kpm module to hide all paths

App will reset boot hash and other props by itself





Any issues reach out : t.me/bklynrom



Source Code:

Original APatch

https://github.com/bmax121/APatch.git



YAPatch:

https://github.com/Yervant7/YAPatch.git





----------------------------------



In order for Module to work with build zygisk.



You will need to edit the customize.sh with the zip 



add the following lines.





&nbsp;   local BKPATCH\_ZYGISK\_ENABLED="/data/adb/.zygisk\_enabled"



&nbsp;   # Check if BKPatch Zygisk is enabled

&nbsp;   if \[ -f "$BKPATCH\_ZYGISK\_ENABLED" ]; then

&nbsp;       local enabled\_content

&nbsp;       enabled\_content=$(cat "$BKPATCH\_ZYGISK\_ENABLED" 2>/dev/null | tr -d '\[:space:]')

&nbsp;       if \[ "$enabled\_content" = "1" ]; then

&nbsp;           return 0

&nbsp;       fi

&nbsp;   fi





----------------------------



In order to get normal Environment on Native Detector



You will need to Embed bkpatch.kpm and flash the kernel.















