# Garrison Report

This macro will cycle through the WoD Garrison Report, Legion Class Hall report and the BfA Missions report. I minimized the script a bit to save on character count. The report frame would not refresh correctly until I added the tab switching at the end. 

```
/run if R==LE_GARRISON_TYPE_6_0 then R=LE_GARRISON_TYPE_7_0 elseif R==LE_GARRISON_TYPE_7_0 then R=LE_GARRISON_TYPE_8_0 else R=LE_GARRISON_TYPE_6_0 end;ShowGarrisonLandingPage(R);GarrisonLandingPageTab2:Click();GarrisonLandingPageTab1:Click()
```

## Breakdown

These are constants specifying the report type. To save more characters you could use the actual values instead.

```
LE_GARRISON_TYPE_6_0 == 2
LE_GARRISON_TYPE_7_0 == 3
LE_GARRISON_TYPE_8_0 == 9
```

| Code                                | Explanation                                           |
|-------------------------------------|-------------------------------------------------------|
| if R==LE_GARRISON_TYPE_6_0 then     | If the last report opened was the WoD report          |
|   R=LE_GARRISON_TYPE_7_0            |   Set the next report to be the legion report         |
| elseif R==LE_GARRISON_TYPE_7_0 then | Else if the last report opened was the Legion report  |
|   R=LE_GARRISON_TYPE_8_0            |   Set the next report to be the BfA report            |
| else                                | Else                                                  |
|   R=LE_GARRISON_TYPE_6_0            |   Set the next report to be the WoD report            |
| end                                 | End                                                   |
| ShowGarrisonLandingPage(R)          | Open the chosen report                                |
| GarrisonLandingPageTab2:Click()     | Switch to the second tab of the report                |
| GarrisonLandingPageTab1:Click()     | Switch back to the first tab of the report            |

