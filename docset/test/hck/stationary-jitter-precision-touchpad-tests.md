---
author: joshbax-msft
title: Stationary Jitter
description: Stationary Jitter
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 63d27295-3ee3-4df7-9b77-5bbccf745c0b
---

# Stationary Jitter


## Test name


-   **Test.StationaryJitter.json**

-   **Test.StationaryJitterMultiple.json**

## Core requirements tested


Device.Input.PrecisionTouchpad.Precision.StationaryJitter

## Tools required


-   **PTLogo.exe**

-   PT3 with Precision Touchpad modifications

## Validation steps


1.  Start **Test.StationaryJitter.json**.

2.  Follow the instructions in [Windows Precision Touchpad Device Validation Guide](windows-precision-touchpad-device-validation-guide.md#gen) to make sure that the touchpad is perfectly aligned, with the bottom edge facing the tester.

3.  Make sure both axes are locked on the PT3, so that the contact(s) can only move up and down.

    ![pt3 axis locking](images/hck-winb-pt3axislocking.jpg)

    **Figure 1 PT3 Axis Locking**

4.  Carefully lower one contact straight down anywhere on the digitizer surface.

    **Note**  
    Some PT3 tips might bounce slightly if brought down quickly. To avoid this, lower the tip slowly onto the digitizer surface.

     

5.  Wait ten seconds, using the timer in the upper-right corner of PTLogo.

6.  Carefully raise the contact.

7.  If no jitter is detected, PTLogo will pass the iteration and move on to the next. Otherwise, it will fail the test and give an error.

8.  Repeat for five iterations, each at a different location on the touchpad.

9.  Start **Test.StationaryJitterMultiple.json**.

10. Add contacts to the PT3, so that there are three to five contacts (as supported by the device) at a separation distance of 11mm.

    ![stationary jitter test - 3 contacts](images/hck-winb-stationaryjittertest3contacts.jpg)

    **Figure 2 Stationary Jitter Test with Three Contacts**

11. Carefully lower the contacts down anywhere on the touchpad, until all contacts are visualized in PTLogo.

    For pressure pads, lower the contacts until they are just above the maximum *z* height (1mm), and bring down quickly but smoothly until all contacts are visualized in PTLogo.

12. Wait ten seconds, using the timer in the upper-right corner of PTLogo.

13. Carefully raise the contacts.

14. If no jitter is detected, PTLogo will pass the iteration and move on to the next. Otherwise, it will fail the test and give and error.

15. Repeat for five iterations, each at a different location on the touchpad, but always with the contacts aligned horizontally on the digitizer surface as shown in *Figure 2 Stationary Jitter Test with Three Contacts*.

## Common errors


-   \[12\] interaction too short: \#\#\#\#\#

    -   Contact was down for less than the required duration.

    -   The value provided is the duration of the contact in milliseconds.

    ![stationary jitter interaction too short](images/hck-winb-stationaryjitteryfailure-interactiontooshort.png)

    **Figure 3 Stationary Jitter Failure - Interaction Too Short**

-   11\] contact displacement too large: \#\#\#

    -   Contact moved or jittered greater than the allowed tolerance of 0.5mm.

    -   The value provided is the himetric displacement.

    ![stationary jitter failure contact displacement](images/hck-winb-stationaryjitterfailure-contactdisplacementtoolarge.png)

    **Figure 4 Stationary Jitter Failure - Contact Displacement Too Large**

## Passing


A total of 10/10 (100%) iterations must pass in order to complete with passing status.

## Related topics


[Precision Touchpad Tests](precision-touchpad-tests.md)

 

 






