# Xplane

Read data from the simulator export to embedded devices and actuators ...

Experience, tips, how to, ... 

Collected by Twenkid.

Version: 10.4.2022


https://github.com/leecbaker/xplane_sdk/blob/master/sdk/CHeaders/XPLM/XPLMPlanes.h

От тук се прихваща управлението на обект самолет в симулатора:

```
XPLM_API int        XPLMAcquirePlanes(
                         char **              inAircraft,    /* Can be NULL */
                         XPLMPlanesAvailable_f inCallback,    
                         void *               inRefcon);    
```

И после може да му се прочетат напр. следните параметри, които мисля че може да се ползват за движение на уреди от самолет или за накланяне на платформи или пък да речем на модел на самолета с образователна цел.


```
typedef struct {
     /* The size of the draw state struct.                                         /
     int                       structSize;
     / A ratio from [0..1] describing how far the landing gear is extended.       /
     float                     gearPosition;
     / Ratio of flap deployment, 0 = up, 1 = full deploy.                         /
     float                     flapRatio;
     / Ratio of spoiler deployment, 0 = none, 1 = full deploy.                    /
     float                     spoilerRatio;
     / Ratio of speed brake deployment, 0 = none, 1 = full deploy.                /
     float                     speedBrakeRatio;
     / Ratio of slat deployment, 0 = none, 1 = full deploy.                       /
     float                     slatRatio;
     / Wing sweep ratio, 0 = forward, 1 = swept.                                  /
     float                     wingSweep;
     / Thrust power, 0 = none, 1 = full fwd, -1 = full reverse.                   /
     float                     thrust;
     / Total pitch input for this plane.                                          /
     float                     yokePitch;
     / Total Heading input for this plane.                                        /
     float                     yokeHeading;
     / Total Roll input for this plane.                                           */
     float                     yokeRoll;
} XPLMPlaneDrawState_t;
```

X-plane SDK 3 Tutorial - Build Your First Plugin in Visual Studio 2017 [Part 1]
https://www.youtube.com/watch?v=8hwPJnhYapo

Compile --> produces .xpl file --> move to the "plugins" folder of the selected plane of Xplane


https://developer.x-plane.com/code-sample/acquireplanetest/

https://developer.x-plane.com/sdk/XPLMDataAccess/

https://developer.x-plane.com/code-sample/sharedata/
