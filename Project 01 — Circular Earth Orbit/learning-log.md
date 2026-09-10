\# Goal: 

Make a spacecraft in a circular Earth orbit and propagate it

\# What we need:

\- Spacecraft - our spacecraft

\- CoordinateSystem - defines how we describe the position and orientation

\- ForceModel - Defines force acting on it

\- Propagator - Calculate how the orbit changes

\- Propagate - Starts the simulation



\*\*\*



\# 9/8/26

\- Created circular-orbit.script

\- First run gave warning:

```

Interpreting scripts from the file.

\*\*\*\*\* file: C:\\Users\\comp\\CODE\\GMAT-Portfolio\\Project 01 — Circular Earth Orbit\\circular-orbit.script

Successfully interpreted the script

\*\*\* WARNING \*\*\*  BeginMissionSequence command is missing. One will be required in future release. There is no command detected.

Running mission...



Mission run completed.

===> Total Run Time: 0.107 seconds

```

\- Added "BeginMissionSequence;"



```

Interpreting scripts from the file.

\*\*\*\*\* file: C:\\Users\\comp\\CODE\\GMAT-Portfolio\\Project 01 — Circular Earth Orbit\\circular-orbit.script

Successfully interpreted the script

Running mission...



Mission run completed.

===> Total Run Time: 0.078 seconds

```

\*\*\*



\# 9/9/26

\- Added what state we want the spacecraft to start in

\- Orbital Elements: 

&#x20; - SMA is the semi-major axis

&#x20; - ECC is the eccentricity ( the stretch of orbit)

&#x20; - INC is the inclination (tilting)

&#x20; - RAAN is right ascension of ascending node (orientation of plane)

&#x20; - AOP is argument of periapsis (orientation within the plane)

&#x20; - TA is "True anomaly" (where the SC is in orbit)



\- Added SMA and ECC to spacecraft

&#x20; - SC.SMA = 7000 means that we are only about 622km above the Earth's Altitude since Earth's radius is 6378km.

&#x20; - SC.ECC = 0 makes our orbit circular

\- ECC descriptions:

&#x20; ```

&#x20; ECC = 0        → circular

&#x20; 0 < ECC < 1    → elliptical

&#x20; ECC = 1        → parabolic

&#x20; ECC > 1        → hyperbolic

&#x20; ```



\- Added INC using SC.INC = 28.5;

&#x20; - INC is measured in degrees

\- Added RAAN to equal 0;

&#x20; - Still unfamiliar with concept of RAAN and INC

\- Added AOP, but orbit is circular so no particular points yet needed

\- Added TA, starting location at 0 degrees (Periapsis)

\- Current Script:

&#x20; ```

&#x20; Create Spacecraft SC;

SC.DisplayStateType = Keplerian;

SC.SMA = 7000;

SC.ECC = 0;

SC.INC = 28.5;

SC.RAAN = 0;

SC.AOP = 0;

SC.TA = 0;

BeginMissionSequence;

&#x20; ```

\- Outcome:

&#x20; ```

&#x20; Interpreting scripts from the file.

\*\*\*\*\* file: C:\\Users\\comp\\CODE\\GMAT-Portfolio\\Project 01 — Circular Earth Orbit\\circular-orbit.script

Successfully interpreted the script

Running mission...

Mission run completed.

===> Total Run Time: 0.053 seconds

&#x20; ```

























