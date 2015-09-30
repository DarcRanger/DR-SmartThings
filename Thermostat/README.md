Thermostat Apps - READ ME
==============

Thermostat/Thermostat Mode-Fan:V-Switches v1.0
--
This smart app uses Virtual Switches to control the thermostat fan and the thermostat mode.  Create a virtual switch to adjust the FAN: ON/AUTO. 
Create three virtual switches to change the thermostat MODEL COOL[ON/OFF], HEAT [ON/OFF],and AUTO [ON/OFF].  Turning mode on will turn the other two off.  
The smart app is setup so that changes from the thermostat directly or via the virtual switches will stay in sync.
The is also an app touch feature that will post to IDE logs or you phone app activity log the current setting and conditions of your thermostat.
Push Notifications can be set separately for thermostat fan and the thermostat mode, and will reflect changes made to either.

Thermostat/Thermostat Setpoints: V-Dimmers Switch Option v1.1
--
This smart app is combines the functions of two of my Original Setpoint Smart Apps by giving the user the option to select which type of dimmer they want to use. The app adjust a thermostat's temperature setpoints for heating and cooling.  Choose between the standard dimmer device type and my custom Momentary Dimmer device type. My custom device type for a Virtual Momentary Dimmer can be found in my Custom-Device folder.
There are several additional options.
The Thermostat device type has the option of the standard setHeatingSetpoint and setCoolingSetpoint.  This may or may not have a built in time delay for activation.  Some Thermostat device types have another option called quickSetHeat and quickSetCool.  There is no delay built in to changing the setpoint temperatures, although still may be a short lag.  The app will also adjust the dimmer level of the virtual dimmers if the setpoints are changed directly from the device.
I also added options for a setPoint limiter for maximum/minimum. This way temperature setPoint request is out of range it will reset to the preset maximum/minimum.
Some thermostats have an issue with the syncing the virtual switch with the actually device. I have added a switch option to either allow the app to adjust the dimmer level of the virtual dimmers if the setpoints are changed directly from the device or no to sync between them.  Syncing is more of putting a bow on the dimmer sliders on the app, since the actual thermostat and the thermostat in the phone app are always in sync.  It is an aesthetic feature and not a requirement.
The other option I setup deals with notifications in the phone app.  There is current no option to receive a text message, but the app will give push notifications.  There are two options here one is the normal push notification that should show up on your phone’s normal notification screen.  The other is a silent notification that will only appear in the SmartThings Notification/Activity Logs.

Thermostat/Thermostat Setpoints: V-Momentary Step Change v1.1
--
This smart app uses two Virtual Momentary switches used to change setPoint incrementally for each momentary button push, one to increase and one for decrease. The steps for the incremental change are one to five [1-5] with a default of 1.  There is a step change option for increase and decrease.
I also added options for a setPoint limiter for maximum/minimum. This way temperature setPoint request is out of range it will reset to the preset maximum/minimum.
The other option I setup deals with notifications in the phone app.  There is current no option to receive a text message, but the app will give push notifications.  There are two options here one is the normal push notification that should show up on your phone’s normal notification screen.  The other is a silent notification that will only appear in the SmartThings Notification/Activity Logs.

Thermostat/ThermostatFan On_Auto V-Switch
--
This smart app uses Virtual Switches to control the thermostat fan.  Create a virtual switch to adjust the FAN: ON/AUTO. 
The smart app is setup so that changes from the thermostat directly or via the virtual switches will stay in sync.

Thermostat/OBSOLETE/Thermostat Setpoints: V-Dimmers v2
--
This smart app uses Virtual Dimmers to adjust a thermostat's temperature setpoints for heating and cooling. Although there is a short lag, the app will also adjust the dimmer level of the virtual dimmers if the setpoints are changed directly from the device. I also added options for a setPoint limiter for maximum/minimum. This way temperature setPoint request is out of range it will reset to the preset maximum/minimum. 

Thermostat/OBSOLETE/Thermostat Setpoints: V-Momentary Dimmers v2.1
--
This smart app uses my custom device type for a Virtual Momentary Dimmer, which can be found in my Custom-Device folder.
This functions the same way as the above smart app, Thermostat Setpoints: V-Dimmers v2 , with the standard dimmer device type.  The main difference is that it removes the need to program the app to turn the dimmer switch off after the request is made.
This smart app uses Virtual Momentary Dimmer to adjust a thermostat's temperature setpoints for heating and cooling. Although there is a short lag, the app will also adjust the dimmer level of the virtual dimmers if the setpoints are changed directly from the device. I also added options for a setPoint limiter for maximum/minimum. This way temperature setPoint request is out of range it will reset to the preset maximum/minimum.
