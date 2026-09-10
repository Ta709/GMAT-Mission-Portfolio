# Goal: 
Make a spacecraft in a circular Earth orbit and propagate it
# What we need:
- Spacecraft - our spacecraft
- CoordinateSystem - defines how we describe the position and orientation
- ForceModel - Defines force acting on it
- Propagator - Calculate how the orbit changes
- Propagate - Starts the simulation

***

# 9/8/26
- Created circular-orbit.script
- First run gave warning:
```
Interpreting scripts from the file.
***** file: C:\Users\comp\CODE\GMAT-Portfolio\Project 01 — Circular Earth Orbit\circular-orbit.script
Successfully interpreted the script
*** WARNING ***  BeginMissionSequence command is missing. One will be required in future release. There is no command detected.
Running mission...

Mission run completed.
===> Total Run Time: 0.107 seconds
```
- Added "BeginMissionSequence;"

```
Interpreting scripts from the file.
***** file: C:\Users\comp\CODE\GMAT-Portfolio\Project 01 — Circular Earth Orbit\circular-orbit.script
Successfully interpreted the script
Running mission...

Mission run completed.
===> Total Run Time: 0.078 seconds
```
***

# 9/9/26
- Added what state we want the spacecraft to start in
- Orbital Elements: 
  - SMA is the semi-major axis
  - ECC is the eccentricity ( the stretch of orbit)
  - INC is the inclination (tilting)
  - RAAN is right ascension of ascending node (orientation of plane)
  - AOP is argument of periapsis (orientation within the plane)
  - TA is "True anomaly" (where the SC is in orbit)

- Added SMA and ECC to spacecraft
  - SC.SMA = 7000 means that we are only about 622km above the Earth's Altitude since Earth's radius is 6378km.
  - SC.ECC = 0 makes our orbit circular
- ECC descriptions:
  ```
  ECC = 0        → circular
  0 < ECC < 1    → elliptical
  ECC = 1        → parabolic
  ECC > 1        → hyperbolic
  ```

- Added INC using SC.INC = 28.5;
  - INC is measured in degrees
- Added RAAN to equal 0;
  - Still unfamiliar with concept of RAAN and INC
- Added AOP, but orbit is circular so no particular points yet needed
- Added TA, starting location at 0 degrees (Periapsis)
- Current Script:
  ```
  Create Spacecraft SC;
  SC.DisplayStateType = Keplerian;
  SC.SMA = 7000;
  SC.ECC = 0;
  SC.INC = 28.5;
  SC.RAAN = 0;
  SC.AOP = 0;
  SC.TA = 0;
  BeginMissionSequence;
  ```
- Outcome:
  ```
  Interpreting scripts from the file.
  ***** file: C:\Users\comp\CODE\GMAT-Portfolio\Project 01 — Circular Earth Orbit\circular-orbit.script
  Successfully interpreted the script
  Running mission...
  Mission run completed.
  ===> Total Run Time: 0.053 seconds
  ```











