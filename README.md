# Welcome to OPKR

Table of Contents
==================

<img src="https://i.imgur.com/aOxwC8R.png" align="right"
     alt="OPKR" width="175" height="240">

* [Join Our Discord](#-join-our-discord-)
* [About This Fork](#-about-this-fork)
* [Main Features](#-main-features)
* [Branch Definitions](#-branch-definitions)
* [How To Install](#-how-to-install)
* [Settings Menu](#-setting-menu)
* [Special Thanks](#-special-thanks)
* [Donate](#-donate-)

Join our Discord
=================

Join The OPKR Server!

* https://discord.gg/pppFp2pVW3

About This Fork
================

This fork is focused on Hyundai, Kia, and Genesis Vehicles and for all people who love Comma's Openpilot.

Main Features
==============

 - Advanced UI with on-screen settings for most openpilot parameters.
 - Live Tune via UI
 - Change cruise mode pushing GAP Button at Cruise Standby status.(OpenpilotStock, Dist+Curv, Dist only, Curv only, OneWay mode, Speedlimit decelation mode only)
 - MapBox support, thanks to Dragonpilot
 - Showing IP Address/SSID name/cell carrier and signal strength
 - Cruise Button Spamming to adjust car set speed without longitudinal control, using OP target speed to keep certain distance to lead car. Variable scc speed control for smooth deceleration (better than stock) when you approach the lead car, and smooth acceleration.
 - SmartMDPS support for steering down to 0 mph.
 - Auto Recognition of SCC bus on CAN 2 for long control.
 - Variable color speed display, braking shades of red, acceleration shades of green, coasting (no brake, no gas) white.
 - OSM / Waze integration for auto SCC speed adjust via button spamming with custom speed offset UI.
 - Slow down for curve using Model, OSM or both with custom speed based on the CV (curve vector / angle of curve) in UI.
 - 2 Users presets for easy paramater saving and restore.
 - Auto lane mode selection (laneless or lanefull).
 - Multi-lateral control with auto lateral mode change based on speed or curve.
 - Auto gap adjust based on speed.
 - No ssh knowledge required, as most paramater can be adjusted via UI.
 - Always updated and current.

User-Friendly Control Mode(UFC)
 - Full time lateral control
 - Auto Resume while Driving
 - Seperate Lateral / Long control

Branch Definitions
====================

 - `OPKR:` main branch, stable, not latest. This will be updated if test branch is done.
 - `OPKR_test:` test branches, not stable, latest, for testing new functions, codes, or the other things. <br />
  ** old branches are in openpilot_bak repository.

How To Install
===============

 - `OPKR's fork installer:` Type https://opkr.o-r.kr/fork/opkr on custom URL window. (OPKR_test branch is https://opkr.o-r.kr/fork/test)
 - `SSH:` cd /data; mv openpilot openpilot_bak; git clone https://github.com/openpilotkr/openpilot.git -b OPKR; reboot <br />
  ** you can also use Shane's fork installer. (https://smiskol.com/fork)

Setting Menu
=============

 - `Device` (**Function Name:** Description)
   - **Driving Camera:** You can preview/unview Openpilot Driving Camera.

 - `Network` (**Function Name:** Description)
   - **HotSpot on Boot:** Turn on Hotspot when boot. (reboot required)
   - **Use Legacy SSH Key:** Use old ssh key access(below 0.8.2). (no reboot required)

 - `Toggles` (**Function Name:** Description)
   - **Enable Lane selector Mode:** Show a lane mode button on driving screen Laneline/LaneLess/AUTO. AUTO will automatically switch based on presents of lane marker. (no reboot required)
   - **Enable Driver Monitoring:** On/Off driver monitoring for the EON without filterless IR camera or Someone cannot use front cam due to certain reasons.(reboot required)
   - **Enable Driving Log Record:** Record driving logs to Local, not to online server. (reboot required)
   - **Enable Sending Log to Server:** Enable log upload to online server. (reboot required)
   - **Use Comma Stock UI:** this use original Comma's UI. Also this can be applied on driving screen in realtime (click MaxSpeed box at top-left corner). (no reboot required)

 - `Software` (**Function Name:** Description)
   - **Check for Updates:** You can confirm new commits of your fork, press ok will update and reboot.(like git pull).
   - **Commit(Local/Remote):** Commit name of local(EON) and Remote.(run once when boot in manager.py, search gitcommit.sh at the file, internet connection required)
   - Parameter Preset -
   - **Load Preset/Save Preset:** Load or Save Your Parameters. stored in /data/preset1 or /data/preset2. This function will save/load your    parameter settings.
   - **Parameter Init:** Remove your settings changes and restore initial values.
   - Git Branch Change -
   - **Git Pull On Boot:** Check for updates and update fork every boot.
   - **Change Repo/Branch:** You can install others fork by typing Git ID, Git Repository, Git Branch or change OPKR branch by pressing the reload button then select branch from dropdown box, device will reboot to selected branch.
   - **Git Reset:** Remove your local changes and inintalize to the original status of the branch.
   - **GitPull Restore :** Go back to previous version of fork if last update is not desired. (please note if you make special changes to OPKR fork, you will loose them if you use GitPull Restore).
   - Util Program-
   - **Panda Flashing (Old) :** Run Panda flashing command manually on pre Neos 18. Basically this is not necessary on normal operation.
   - **Panda Flashing (New) :** Run Panda flashing command manually on post Neos 18. Basically this is not necessary on normal operation.
   - **Remove Dash Err On Boot :** Use this to prevent dashboard alarms during boot, only required for some HKG models with C2.
   - **Open Android Settings :** This will go to device setting to access APN etc settings.
   - **SoftKey Run/Set :** Softkey is a utility app to make custom soft key on OPKR driver screen.
   - **Run Mixplorer :** Mixplorer is a versatile file manager app.
   - `UI Menu` (**Function Name:** Description)
   - **EON ForceShutdown:** The device will be shutdown by force at offroad status after set time.
   - **EON Volume Control(%):** set device volume manually.
   - **EON Brightness Control(%):** set device brightness automatically or manually.
   - **EON SCR Off Timer:** The Brightness at SCR Off(%) will be in effect after set time when driving.
   - **Brightness at SCR Off(%):** Work with (EON SCR Off Timer) setting, set screen brightness level %.
   - **DoNotDisturb Mode :** Dont wake the baby, not seen, not heard.
   - **EON Detach Alert Sound:** Will play alert sound when your car ignition is turned off. (Can be used as a reminder to remove device from mount to protect from sun, theft, etc.)
      - None
      - Korean
      - English
   - **Enable Battery Charging Control:** battery charging control, min and max battery setting. (Not applicable for batteryless unit.)
   - **Use Auto Screen Record:** At departure, screen recording starts automatically, when vehicle is stationary, screen recording stop.
   - **Number of Recorded Files:** Max mp4 files that will be recorded before oldest file is overwritten. (to prevent device storage full)
   - **Recording Quality:** Video quality of recordings
      - Low
      - Mid
      - High
      - U-High
   - **Delete All Recorded Files:** from device /sdcard/videos
   - **Delete All Driving Logs:** from device/sdcard/realdata
   - **Driver Monitoring Mode:** Default/Unsleep (no reboot required)
      - Default: This Comma's DM mode
      - Unsleep: If you choose Unsleep, dm will be more sensitive than default. <br />
        **You can switch the Mode on driving screen in realtime (touch monitoring face at bottom-left corner) <br />
        **no background is Default Mode. Light green background is Unsleep Mode. 
   - **E2E EYE Threshold:** Experimental setting.
   - **Normal EYE Threshold:** set the value below threshold of your face recognition.
   - **Blink Threshold:** For Driver Monitoring. Set the value below the threshold of your eyes blink recognition. Driver Monitoring camera shows the values of your face recognition, eyes and the other things. Preview 'Driver Camera' and then check the recognition value of your eye blink to modify the value on menu.
   - **Navigation Select:** 
      - Mappy (Korea)
      - iNavi (Korea)
      - Waze (Global)
      - TMapE (Korea, use TMap on external device, to free up system resource on device)
      - WazeE (Global, use Waze on external device, to free up system resource on device)
   - **ExternalDevIP:** IP address of external navi device that OPKR will retrieve traffic info from, must be sharing same netork with internet access.
   - **RUN Navigation on Boot:** Run your above selected navi app on boot. If it runs well, will go to background after few seconds.
   - **API Server:** Choose driver log server
      - OPKR
      - Comma
      - User's
   - **User's API:** Set User driver log server url.
   - **Enable Mapbox
   - **Mapbox Style:** Choose from three styles
      - Mapbox
      - Comma
      - OPKR (locallized in Korea) <br />
        **if you want to use your own, Edit the file with yours(/data/params/d/MapboxStyleCustom). <br />
        **You can make your mapbox style at https://studio.mapbox.com/. (If you publish the style you can use it.)
   - **Use GoogleMap For Mapbox:** Use google map when you search your destination at a web browser.
   - **Bottom Text View:** Show Date/Time/Roadname at bottom of drive screen.
   - **RPM Animation:** Show RPMs on UI with adjustable limit.
   - **AnimatedRPM Max:** max hundreds scale for animated rpm meter.
   - **Show Stop Line:** show stop line and stop signal, needed for opkr long control stop at stop signal feature (expermental).
   - **Hold Button for Setting Menu:** if active you wiil have to hold button to access setting menu, to prevent unwanted access.
   - **Enable RTShield Process:** enhancement for smoother op operation.
   - **Offline OSM (64G storage only):** OSM Korea only, device storage memory must be >= 64G.

 - `Driving Menu` (**Function Name:** Description)
   - **Use Auto Resume at Stop:** after standstill, op will auto resume when leadcar start moving.
   - **RES count at standstill:** some model need to be adjusted so car move when lead car start moving.(reboot required)
   - **Change Cruise Gap at Stop:** Cruise Gap changed to 1 step for departure faster, it gets back to orignal Gap after few second.
   - **Cruise Gap Change By Speed:** set your preferred following gap 1 - 4 automatically based on speed.
   - **Standstill Resume Alternative:** Some model like DH Genesis need this for Auto Resume at Stop.
   - **Depart Chime At Resume:** work with show stop line, will play chime when light change to green or lead car start moving.
   - **Use Cruise Button Spamming:** SCC set speed is changed up and down automatically. turn on to use many functions related to auto speed control.
   - **Button Spamming Level:** set how aggresive buttom spamming is adjusted, 0 - 16. (this affects acceleration & deceleration with speed limit change).
   - **CruiseSet With RoadLimitSpeed:** set SCC max speed based on road speed limit, independent of OPKR Navi/OSM info.
   - **Cruiseset RoadLimitSpd Ofs:** speed offset for above RoadLimitSpeed.  
   - **Cruise Start Mode:** Set your custom Cruise mode when boot. There are 6 modes. (OpenpilotStock/Dist+Curv/Dist/Curv/Oneway/CamSpeed) 
      - OpStock: Scc button will set scc speed, will work like stock button to set op. 
      - Dist+Curv: changed by distance to leadcar and curvature. 
      - Dist: distance only. 
      - Curvonly: curvature only. 
      - Oneway: change camera offset to approach the edge of a road. 
      - CamOnly: is changing set speed only by value of speed sign (OSM, iNavi, Mappy).
   - **LaneChange On/Off/Spd:** minimum lane change speed.
   - **LaneChange Delay:** adjust delay time before lane change
      - Nudge/Nudgeless/Set Seconds
   - **LaneChange Time(km/h: value):** How quick should lane change be completed, increase for faster, decrease for slower.
   - **LeftCurv Offset:** if you are not satisfy with Left Curve Section, this can move your car to left or right side.(no reboot required)
   - **RightCurv Offset:** if you are not satisfy with Right Curve Section, this can move your car to left or right side.(no reboot required)
   - **Show BSM Status:** Show when a car is in blindspot. need car BSM function.
   - Steer Control Method** Choose between normal and smooth.
   - **Max Steering Angle:** Default is 90. If you want more, increase this. Some car will not accept value above 90.
   - **Str Angle Adjust:** To keep car on a straight road, If the value of steering angle is not 0.0, adjust this to be 0.0
   - **Stop Steer Assist on Turn Signals:** Openpilot doesn't steer your car when turn signal is active.
   - **Reset MaxSpeed Over CurrentSpeed:** Sync scc speed with car current speed, the OP MaxSpeed synchronize to your car speed.
   - **Enable OSM:** use OSM feature
   - **Enable OSM SpeedLimit:** Use OSM SpeedLimit, active internet required. (reboot required).
   - **Use Stock SafetyCAM Speed:** Some cars have the signal in CAN message. not for all HKG cars.
   - **SpeedLimit Offset:** Use to set scc max speed above or below the navi / CAN reported speed. This can be % speed amount + / - or "c" for custom settings.
   - **CustomSpeedlimit([SL],[Target Speed]):** For custom offset speed SL is speed Limt & Target Speeds the offset limit.
   - **SafetyCam SignType:** You can select 2 options to show on the screen
      - Circular: (EU) type of speedlimit sign.
      - Retangular: (US) type of speedlimit sign.
   - **SafetyCamDist Adj(%):** Change the target distance if you are in the decel situation of speed limit or safetycam.
   - **Curve Decel Option :** Which curve decel you want to use,  Vision / OSM.
   - **VisionCurvDecel([CV],[Target Speed]):** set speed is changed by Curve Vector and Target Speed.
   - **OSMCurvDecel([TSL],[Target Speed]):** If OSM has the value of curv, set your target speed.
   - **SpeedBump Deceleration:** for Korea iNavi , not all navi app supply speed bump info.
   - **Early Slowdown with Gap:** will use auto gap setting to assist in deceleration with lead car.
   - **Use Auto Engagement:** When OP is in disengagement status, Auto engagement is enabled when your car is moving. Cruise Standby status is needed at least.
   - **Auto Engage Speed(km/h):** Auto Engagement is enabled at this speed.
   - **Use Auto RES while Driving:** SCC speed automatically resume when brake is release or gas is applied.(reboot required)
   - **AutoRES Option:** CruiseSet/MaxSpeedSet, MaxSpeedSet: Your OP MAX Speed set with RES Set speed. CruiseSet:only set to current set speed, not changed OP MAX Speed.
   - **AutoRES Condition:** RelBrake/OnGas, RelBrake: SCC speed set again when you release from brake pedal. OnGas: SCC speed set again when you step gas pedal.
   - **AutoRES Allow(sec):** If AutoRES does not occur before set time, then auto resume is cancelled.
   - **AutoRESDelay (sec):** AutoRes will not reume until set time elapse, to prevent premature resume.
   - **Set LaneWidth:** Adjust if road lane is narrow
   - **Speed LaneWidth:** [Spd(m/s)], [Lanewidth] Adjust speed based on lane width.
   - **Routine Drive by Roadname:** (WIP) will change drive characteristics based on road, eg if local or highway will handle curve differently.
   - **Driving Close to RoadEdge** for driving on narrow single lane road.
   - **To Avoid LKAS Fault** allow steer limit greater than 90 degree LKAS steering limit on HKG cars. Max Angle & Max Frame model dependent.
   - **Speed CameraOffset**

 - `Developer Menu` (**Function Name:** Description)
   - **DEBUG UI 1:** Show debug UI on screen. 2 lines bottom of screen.(no reboot required)
   - **DEBUG UI 2:** Show debug UI on screen. other lines except 2 lines bottom.(no reboot required)
   - **DEBUG UI 3:** Show debug UI on screen. more debug info.(no reboot required)
   - **Show TMUX Error:** Turn this on, if you want to show tmux error on screen related to process such as controlsd, plannerd and so on.(reboot required)
   - **Show LongControl LOG:** show long control log at DEBUG UI 1.(no reboot required)
   - **Use Smart Prebuilt:** Your device can be booted quickly. The file, Prebuilt is removed when you do push 'CHECK' button on the Menu or type 'gi' command on command line, after then it will be created again when boot&compile is completed.(reboot required)
   - **Use FingerPrint 2.0:** (reboot required)
   - **Support WhitePanda:** Turn this on if you use WhitePanda. this is related to issue stopping processes when you turn device off.(reboot required)
   - **Set BatteryLess Eon:** Screen doesn't show information of battery status.
   - **Turn Off Communication Issue Alarm:** Turn this on if you do not want alert of communication error. Sometimes you could get an commuication issue alert while using navi app or your custom UI is busy or rarely due to locationd(regarding GPS) process. I could use OP with the alert before without any issues. This is quite old issue. Currently I'm not sure if the error is still exist.
   - **Set LDWS Vehicles**
   - **Set DriveGear by Force:** for cars don't have dbc info of gear(reboot required)
   - **Ignore of Steering Warning:** Some cars have Steerwarning, so that not engaged.
   - **Ignore Can Error on ISG:** for ISG cars. In order to ignore can error, if you want to prevent disengagement.
   - **Enable FCA11 Message:** For some newer vechicle
   - **User-Friendly Control (UFC) Mode:** Full time lateral control.
   - **StockLKAS Enable at disengagement:** Use stock LKAS when op is disable.
   - **C2 with CommaPower:** Enable if you are using C2
   - **Joystick Debug Mode:** For debug Joystick testing.
   - **No Smart MDPS:** If your car does not support steering down to 0 mph (no smartmdps harness).
   - **FeatureNumber:** For user specific feature.
   - **Timezone setting:** (reboot required)
   - **Enable Calibration by Force:** developer for engagment test
   - **CAR Type:** If your car is not recognized, choose your car at this. (reboot required)
   - Panda Value - :** default setting is good for most user. (reboot required)
      - MaxSteer
      - RTDelta
      - MaxRateUp
      - MaxRateDown

 - `Tuning Menu` (**Function Name:** Description)
   - **CameraOffset:** set your camera offset
   - **PathOffset:** i'm not sure this. but i recommend if you move your camera offset, adjust this as the value.
   - **SteerActuatorDelay:** level how your car reacts to upcoming road curvature.
   - **Use Live SteerRatio:** Use Live Parameter value.
   - **TireStiffnessFactor:** lower value makes your steer more aggressive.
   - **SteerThreshold:** driver steering torque threshold.
   - **SteerLimitTimer:** timer how long op hold the steer. and timer for alert.
   - **Use LiveSteer Ratio:**
   - **LiveSR Adjust(%):** in some cases, live parameter is higher than original steeratio, i set this to minus value to not steer aggressively.
   - **SteerRatio:** Your default SteerRatio
   - **SteerRatioMax:** Max SteerRatio if you use Varaible SteerRatio not Live SR.
   - **SteerRateCost:** How your car make steer strong to turn with the road curvature. you want make it strong lower the value. too low values, it will make the steering little unstable.
   - **SteerMax/Variable Steermax Toggle:**
   - **SM Base SM Max:** SteerMax Base and Max value if you use variable SteerMax.
   - **SteerMaxV:** multiply to the output scale. it effects steer saturation or others.
   - **DeltaUpDown/Variable Deta Toggle** Use single Delta or Variable Delta, how fast steer outside in certain timing scope.
   - **DtUpBase:DtUpMax** Delta Up base / max value if you use variable steerdelta.
   - **DtDnBase:DtDnMax** Delta Down base / max value if you use variable steerdelta.
   - **SteerDeltaDownMax:** max value if you use variable steerdelta
   - **To Avoid LKAS Fault with More Steer:** more curve steer.
   - **DisiredCurvatureLimit:**
   - **Use LiveTune and Show UI:** this will show button on the screen, you can up/down the values of tune. it will be applied in realtime. you can also touch top-right corner(comma wheel icon) to show tune panel on the screen.
   - `LatControl(Reboot)`** Choose lateral control mode**
      - PID
      - INDI
      - Torque
      - LQR
      - Multi

   - `LONG CONTROL` **(RadarHareness required)**
      - **Custom TR Enable:**
      - **CruiseGap:** set TR of other Cruise Gaps
      - **Use DynamicTR:** TR changed by car speed.
      - **Dynamic:TR[Speed][TR
      - **Long Mode:** when your car approaches to lead car, use combined value both OP gas/brake and Radar one.
      - **Adjust Stopping Distance:** help stopping distance more close to lead car(not recommended)
      - **Stopping Distance(m):**
      - **Enable E2E Long:** Use Comma E2E long, sometimes it is not comfortable. think it's earlier to release.
      - **Stop At Stop Sign:**
      - **Use Stock Decel on SafetySection:**

Special Thanks
================

`Special Thanks:` ku7, xx979xx, tk211x, xps-genesis, atom(respect you), hoya, moksatang, mamul, neokii, oricialworks, dragonpilot, shane, kegman, dnv26, move-fast, D.Fyffe, Swish865 and everyone helping me or contributing for HKGs.

Donate
=======

If you enjoy any features of this fork and would like to show your support, feel free to donate to @multiKYD on PayPal.

Thank you!

=================


![](https://i.imgur.com/b0ZyIx5.jpg)

Table of Contents
=======================

* [What is openpilot?](#what-is-openpilot)
* [Running in a car](#running-in-a-car)
* [Running on PC](#running-on-pc)
* [Community and Contributing](#community-and-contributing)
* [User Data and comma Account](#user-data-and-comma-account)
* [Safety and Testing](#safety-and-testing)
* [Directory Structure](#directory-structure)
* [Licensing](#licensing)

---

What is openpilot?
------

[openpilot](http://github.com/commaai/openpilot) is an open source driver assistance system. Currently, openpilot performs the functions of Adaptive Cruise Control (ACC), Automated Lane Centering (ALC), Forward Collision Warning (FCW) and Lane Departure Warning (LDW) for a growing variety of [supported car makes, models and model years](docs/CARS.md). In addition, while openpilot is engaged, a camera based Driver Monitoring (DM) feature alerts distracted and asleep drivers. See more about [the vehicle integration](docs/INTEGRATION.md) and [limitations](docs/LIMITATIONS.md).

<table>
  <tr>
    <td><a href="https://youtu.be/NmBfgOanCyk" title="Video By Greer Viau"><img src="https://i.imgur.com/1w8c6d2.jpg"></a></td>
    <td><a href="https://youtu.be/VHKyqZ7t8Gw" title="Video By Logan LeGrand"><img src="https://i.imgur.com/LnBucik.jpg"></a></td>
    <td><a href="https://youtu.be/VxiR4iyBruo" title="Video By Charlie Kim"><img src="https://i.imgur.com/4Qoy48c.jpg"></a></td>
    <td><a href="https://youtu.be/-IkImTe1NYE" title="Video By Aragon"><img src="https://i.imgur.com/04VNzPf.jpg"></a></td>
  </tr>
  <tr>
    <td><a href="https://youtu.be/iIUICQkdwFQ" title="Video By Logan LeGrand"><img src="https://i.imgur.com/b1LHQTy.jpg"></a></td>
    <td><a href="https://youtu.be/XOsa0FsVIsg" title="Video By PinoyDrives"><img src="https://i.imgur.com/6FG0Bd8.jpg"></a></td>
    <td><a href="https://youtu.be/bCwcJ98R_Xw" title="Video By JS"><img src="https://i.imgur.com/zO18CbW.jpg"></a></td>
    <td><a href="https://youtu.be/BQ0tF3MTyyc" title="Video By Tsai-Fi"><img src="https://i.imgur.com/eZzelq3.jpg"></a></td>
  </tr>
</table>


Running in a car
------

To use openpilot in a car, you need four things
* This software. It's free and available right here.
* One of [the 150+ supported cars](docs/CARS.md). We support Honda, Toyota, Hyundai, Nissan, Kia, Chrysler, Lexus, Acura, Audi, VW, and more. If your car is not supported, but has adaptive cruise control and lane keeping assist, it's likely able to run openpilot.
* A supported device to run this software. This can be a [comma two](https://comma.ai/shop/products/two), [comma three](https://comma.ai/shop/products/three), or if you like to experiment, a [Ubuntu computer with webcams](https://github.com/commaai/openpilot/tree/master/tools/webcam).
* A way to connect to your car. With a comma two or three, you need only a [car harness](https://comma.ai/shop/products/car-harness). With an EON Gold or PC, you also need a [black panda](https://comma.ai/shop/products/panda).

We have detailed instructions for [how to install the device in a car](https://comma.ai/setup).

Running on PC
------

All of openpilot's services can run as normal on a PC, even without special hardware or a car. To develop or experiment with openpilot you can run openpilot on recorded or simulated data.

With openpilot's tools you can plot logs, replay drives and watch the full-res camera streams. See [the tools README](tools/README.md) for more information.

You can also run openpilot in simulation [with the CARLA simulator](tools/sim/README.md). This allows openpilot to drive around a virtual car on your Ubuntu machine. The whole setup should only take a few minutes, but does require a decent GPU.


Community and Contributing
------

openpilot is developed by [comma](https://comma.ai/) and by users like you. We welcome both pull requests and issues on [GitHub](http://github.com/commaai/openpilot). Bug fixes and new car ports are encouraged. Check out [the contributing docs](docs/CONTRIBUTING.md).

Documentation related to openpilot development can be found on [docs.comma.ai](https://docs.comma.ai). Information about running openpilot (e.g. FAQ, fingerprinting, troubleshooting, custom forks, community hardware) should go on the [wiki](https://github.com/commaai/openpilot/wiki).

You can add support for your car by following guides we have written for [Brand](https://blog.comma.ai/how-to-write-a-car-port-for-openpilot/) and [Model](https://blog.comma.ai/openpilot-port-guide-for-toyota-models/) ports. Generally, a car with adaptive cruise control and lane keep assist is a good candidate. [Join our Discord](https://discord.comma.ai) to discuss car ports: most car makes have a dedicated channel.

Want to get paid to work on openpilot? [comma is hiring](https://comma.ai/jobs/).

And [follow us on Twitter](https://twitter.com/comma_ai).

User Data and comma Account
------

By default, openpilot uploads the driving data to our servers. You can also access your data through [comma connect](https://connect.comma.ai/). We use your data to train better models and improve openpilot for everyone.

openpilot is open source software: the user is free to disable data collection if they wish to do so.

openpilot logs the road facing cameras, CAN, GPS, IMU, magnetometer, thermal sensors, crashes, and operating system logs.
The driver facing camera is only logged if you explicitly opt-in in settings. The microphone is not recorded.

By using openpilot, you agree to [our Privacy Policy](https://comma.ai/privacy). You understand that use of this software or its related services will generate certain types of user data, which may be logged and stored at the sole discretion of comma. By accepting this agreement, you grant an irrevocable, perpetual, worldwide right to comma for the use of this data.

Safety and Testing
----

* openpilot observes ISO26262 guidelines, see [SAFETY.md](docs/SAFETY.md) for more details.
* openpilot has software in the loop [tests](.github/workflows/selfdrive_tests.yaml) that run on every commit.
* The code enforcing the safety model lives in panda and is written in C, see [code rigor](https://github.com/commaai/panda#code-rigor) for more details.
* panda has software in the loop [safety tests](https://github.com/commaai/panda/tree/master/tests/safety).
* Internally, we have a hardware in the loop Jenkins test suite that builds and unit tests the various processes.
* panda has additional hardware in the loop [tests](https://github.com/commaai/panda/blob/master/Jenkinsfile).
* We run the latest openpilot in a testing closet containing 10 comma devices continuously replaying routes.

Directory Structure
------
    .
    ├── cereal              # The messaging spec and libs used for all logs
    ├── common              # Library like functionality we've developed here
    ├── docs                # Documentation
    ├── opendbc             # Files showing how to interpret data from cars
    ├── panda               # Code used to communicate on CAN
    ├── third_party         # External libraries
    ├── pyextra             # Extra python packages
    └── selfdrive           # Code needed to drive the car
        ├── assets          # Fonts, images, and sounds for UI
        ├── athena          # Allows communication with the app
        ├── boardd          # Daemon to talk to the board
        ├── camerad         # Driver to capture images from the camera sensors
        ├── car             # Car specific code to read states and control actuators
        ├── common          # Shared C/C++ code for the daemons
        ├── controls        # Planning and controls
        ├── debug           # Tools to help you debug and do car ports
        ├── locationd       # Precise localization and vehicle parameter estimation
        ├── logcatd         # Android logcat as a service
        ├── loggerd         # Logger and uploader of car data
        ├── modeld          # Driving and monitoring model runners
        ├── proclogd        # Logs information from proc
        ├── sensord         # IMU interface code
        ├── test            # Unit tests, system tests, and a car simulator
        └── ui              # The UI

Licensing
------

openpilot is released under the MIT license. Some parts of the software are released under other licenses as specified.

Any user of this software shall indemnify and hold harmless Comma.ai, Inc. and its directors, officers, employees, agents, stockholders, affiliates, subcontractors and customers from and against all allegations, claims, actions, suits, demands, damages, liabilities, obligations, losses, settlements, judgments, costs and expenses (including without limitation attorneys’ fees and costs) which arise out of, relate to or result from any use of this software by user.

**THIS IS ALPHA QUALITY SOFTWARE FOR RESEARCH PURPOSES ONLY. THIS IS NOT A PRODUCT.
YOU ARE RESPONSIBLE FOR COMPLYING WITH LOCAL LAWS AND REGULATIONS.
NO WARRANTY EXPRESSED OR IMPLIED.**

---

<img src="https://d1qb2nb5cznatu.cloudfront.net/startups/i/1061157-bc7e9bf3b246ece7322e6ffe653f6af8-medium_jpg.jpg?buster=1458363130" width="75"></img> <img src="https://cdn-images-1.medium.com/max/1600/1*C87EjxGeMPrkTuVRVWVg4w.png" width="225"></img>

[![openpilot tests](https://github.com/commaai/openpilot/workflows/openpilot%20tests/badge.svg?event=push)](https://github.com/commaai/openpilot/actions)
[![Total alerts](https://img.shields.io/lgtm/alerts/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/alerts/)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/context:python)
[![Language grade: C/C++](https://img.shields.io/lgtm/grade/cpp/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/context:cpp)
[![codecov](https://codecov.io/gh/commaai/openpilot/branch/master/graph/badge.svg)](https://codecov.io/gh/commaai/openpilot)
