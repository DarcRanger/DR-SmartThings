/**
 *  Thermostat Setpoints using Virtual Dimmers or Momentary Dimmers
 *
 *  Copyright 2015 Joseph Quander III
 *
 *  Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except
 *  in compliance with the License. You may obtain a copy of the License at:
 *
 *      http://www.apache.org/licenses/LICENSE-2.0
 *
 *  Unless required by applicable law or agreed to in writing, software distributed under the License is distributed
 *  on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License
 *  for the specific language governing permissions and limitations under the License.
 *
 *	Adapted/Inspired from App created by @mattjfrank
 *
 *	Date: 2015-08-28 Version 1.0 - Created App: Based on my Original version with Virtual Dimmer Switch.  
 *		Added several options.
 *			A.	You can select push notifications styles, either Alert push notifications or silent style notifications.  
 *        	Both versions will appear in event history within the SmartThings phone app.
 *
 *			B.	Added option to select device types for switchLevel Dimmer and my custom Momentary Dimmer.
 *					Caution: Be careful switching device types after installation.  The Momentary Dimmers will show under    
 *          the switchLevel Dimmer Type, but the switchLevel Dimmer will not appear under the Momentary device type.  
 *          At this time the app will let you move forward, but the selected switchLevel Dimmers will not appear     
 *          under the Momentary Dimmer selection screen.
 *					The app is coded to work around this issue, and you can still reselect your switch choice.
 *
 *			C.	Added setHeatingSetpoint()/setCoolingSetpoint() with quickSetHeat()/quickSetCool(), since the quick set
 *				command for the Thermostat device type has a much shorter delay action in the custom Thermostat device     
 *        type I am using. Other Thermostat device types do may not have quickSet option and may not have any build  
 *        in implemetation delays with the standard SetPoint commands.
 *
 * 	Date: 2015-09-09 Version 1.1
 *	  Added option to disable sync between thermostat and dimmer/momentary switch when the thermostat is changed.  
 *    Changing the dimmer level will still change the thermostat.  This is a workaround for possible issue with 
 *    celsius conversion with dimmer at temperatures below 30C.
 *
 *  To obtain my Customized Virtual Momentary Dimmer, please visit:
 *	https://github.com/DarcRanger/DR-SmartThings/tree/master/Custom-Devices
 *			
 *	
 *
 */
definition(
    name: "Thermostat Setpoints: V-Dimmer|Momentary Switches v1.1",
    namespace: "DR",
    author: "Joseph Quander III",
    description: "This app uses two custom virtual momentary dimmer switches to control Setpoint temperatures on a Thermostat.  This was develop to use with the Amazon Echo.",
    category: "Green Living",
    iconUrl: "https://s3.amazonaws.com/smartapp-icons/Meta/temp_thermo-switch.png",
    iconX2Url: "https://s3.amazonaws.com/smartapp-icons/Meta/temp_thermo-switch@2x.png",
    iconX3Url: "https://s3.amazonaws.com/smartapp-icons/Convenience/Cat-Convenience@2x.png"    
    )
    
preferences {

page(name: "mainPage") 
page(name: "Switches")
page(name: "Setpoints")
page(name: "SelectSwitches")

}

def mainPage() {
	dynamicPage(name: "mainPage", title: app.label + " is configured as follows:", nextPage: "Switches", uninstall:true){

section("This thermostat will be updated") {
	input "thermostat", "capability.thermostat", multiple: false, title: "Thermostat", required: true
}
    section("Notify me...") {
     input "pushNotification_Setpoint", "bool", title: "Thermostat Mode change with Push Notification", required: false, defaultValue: "false", submitOnChange:true
	
    if(pushNotification_Setpoint){
	input "pushNotification_Silent", "bool", title: "Push Notification with Silent Alert", required: false, defaultValue: "false", submitOnChange:true
}
}
        section([title:"Options", mobileOnly:true]) {
            label title:"Assign a name", required:false
        }
}
}

def Switches() {
dynamicPage(name: "Switches", title: "Switch Method", nextPage: "SelectSwitches") {

section("Switch Method: Traditional Virtual Dimmer or Custom Momentary Dimmer?") {
	input "switchMethod", "enum", multiple: false, title: "Select Switch Method", required: true, options:["Dimmer", "Momentary"], submitOnChange:true //, refreshAfterSelection:true
}
}
}

def SelectSwitches(){
log.debug ("switchMethod: $switchMethod")
if(switchMethod == "Momentary"){
state.switchType = "capability.momentary"
state.Dtitle = "Momentary Dimmer"
state.switchMethod = switchMethod
}
else if(switchMethod == "Dimmer"){
state.switchType = "capability.switchLevel"
state.Dtitle = "Dimmer"
state.switchMethod = switchMethod
}
log.debug "switchType: $state.switchType || Device: $state.Dtitle"

    dynamicPage(name: "SelectSwitches", title: "Select " + state.Dtitle + " Method", nextPage: "Setpoints"){
	section("Select Heating SetPoint " + state.Dtitle) { 
	input "Heating", state.switchType, multiple: false, title: "Heating " + state.Dtitle +" Switch...", required: true
    }
	section("Select Cooling SetPoint " + state.Dtitle) { 
	input "Cooling", state.switchType, multiple: false, title: "Cooling  " + state.Dtitle +" Switch...", required: true
    }       
    }
    }
    
def Setpoints() {
dynamicPage(name: "Setpoints", title: "setPoints are configured as follows:", install: true, uninstall: true) {
section("Setpoint Default Limits: Minimum/Maximum [50/80]") {
	input "setMinimum", "number", multiple: false, title: "Minimum Temperature", required: true, defaultValue: "50"
	input "setMaximum", "number", multiple: false, title: "Maximum Temperature", required: true, defaultValue: "80"
}

section("Thermostat setPoint method: setHeatingSetpoint()/setCoolingSetpoint() or quickSetHeat()/quickSetCool()") {
	input "setMethod", "enum", multiple: false, title: "Select Setpoint Method", required: true, options: ["Default", "quickSet"], defaultValue: "Default"
}
section("Sync Thermostat and $switchMethod") {
	input "setSync", "bool", title: "Turn on to Sync Thermostat and $switchMethod when Thermostat is changed", required: false, defaultValue: "false"
}

}
}

def installed()
{
	log.debug "Installed with settings: ${settings}"
    initialize()
}

def updated()
{
unsubscribe()
	log.info "subscribed to all of switches events"
	log.debug "Updated with settings: ${settings}"
    initialize()
}

def initialize(){
    subscribe(Heating, "switch.setLevel", switchSetLevelHandlerH)
    subscribe(Heating, "switch", switchSetLevelHandlerH)
    subscribe(Cooling, "switch.setLevel", switchSetLevelHandlerC)
    subscribe(Cooling, "switch", switchSetLevelHandlerC)
        subscribe(thermostat, "heatingSetpoint", heatingSetpointHandler)
        subscribe(thermostat, "coolingSetpoint", coolingSetpointHandler)
        //log.debug "Initialized with settings: ${settings}"
}

//------------------Level-Heat---------------------
def switchSetLevelHandlerH(evt){
def TempMode = "Heating"
state.TempMode = TempMode
if ((evt.value == "on") || (evt.value == "off" ))
	return
def level = evt.value.toFloat()
//log.debug "level: $level"
level = level.toInteger()
state.level = level

if(state.level<setMinimum){
state.level=setMinimum
Heating.setLevel(state.level)
log.debug "Thermostat SetLevel below limit: $level.  Reset to minimum Temperature: $setMinimum"
}else if(state.level>setMaximum){
state.level=setMaximum
Heating.setLevel(state.level)
log.debug "Thermostat SetLevel below limit: $level.  Reset to maximum Temperature: $setMaximum"
}

log.debug "switchSetLevelHandler Event: ${state.level} | TempMode: $TempMode"
    state.ThermoHPoint = thermostat.currentValue("heatingSetpoint")   
    if(setMethod == "Default"){
    thermostat.setHeatingSetpoint(state.level)
    }
    if(setMethod == "quickSet"){
    thermostat.quickSetHeat(state.level)
    }    
    log.debug "state.ThermoHPoint: $state.ThermoHPoint | Level: $state.level | setMethod: $setMethod"
    Heating.off(delay: 2500)
}

//------------------Level-Cool---------------------
def switchSetLevelHandlerC(evt){
def TempMode = "Cooling"
state.TempMode = TempMode
if ((evt.value == "on") || (evt.value == "off" ))
	return
def level = evt.value.toFloat()
//log.debug "level: $level"
level = level.toInteger()
state.level = level

if(state.level<setMinimum){
state.level=setMinimum
Cooling.setLevel(state.level)
log.debug "Thermostat SetLevel below limit: $level.  Reset to minimum Temperature: $setMinimum"
}else if(state.level>setMaximum){
state.level=setMaximum
Cooling.setLevel(state.level)
log.debug "Thermostat SetLevel below limit: $level.  Reset to maximum Temperature: $setMaximum"
}

log.debug "switchSetLevelHandler Event: ${state.level} | TempMode: $TempMode"
    state.ThermoCPoint = thermostat.currentValue("coolingSetpoint")
    if(setMethod == "Default"){
    thermostat.setCoolingSetpoint(state.level)
    }
    if(setMethod == "quickSet"){
    thermostat.quickSetCool(state.level)
    }
	log.debug "state.ThermoCPoint: $state.ThermoCPoint | Level: $state.level | setMethod: $setMethod"
    Cooling.off(delay: 2500)
}
//------------------SetPoint-Heating---------------   
   def heatingSetpointHandler(evt) {
      if(setSync) {
   def TempMode = "Heating"
   state.TempMode = TempMode
        log.debug ""
       // log.debug "heatingSetpoint: $evt, $settings"
    log.debug "heatingSetpoint Event Value: ${evt.value}" //  which event fired is here
	log.debug "heatingSetpoint Event Name: ${evt.name}"   //  name of device firing it here

  	def ThermoPoint = thermostat.currentValue("heatingSetpoint")
      //log.debug "ThermoPoint: $ThermoPoint " + TempMode
    def ThermoHeatPoint = evt.value.toFloat()
	ThermoHeatPoint = ThermoHeatPoint.toInteger()
	log.debug("current heatingsetpoint is $ThermoHeatPoint")
    state.ThermoPoint = ThermoPoint
     log.debug "HSP - state.ThermoPoint: $state.ThermoPoint | $state.level"
     if(state.ThermoPoint != state.level){
		Heating.setLevel(ThermoHeatPoint)
		Heating.off(delay: 2500)
        }
		Notification()
}
}

//------------------SetPoint-Cooling---------------

	def coolingSetpoint(evt) {
	   if(setSync) {
	def TempMode = "Cooling"
    state.TempMode = TempMode
		log.debug ""
		//log.debug "coolingSetpoint: $evt, $settings"
	log.debug "coolingSetpoint Event Value: ${evt.value}" //  which event fired is here log.info
	log.debug "coolingSetpoint Event Name: ${evt.name}"   //  name of device firing it here log.info

  	def ThermoPoint = thermostat.currentValue("coolingSetpoint")
     // log.debug "ThermoPoint: $ThermoPoint " + TempMode
    def ThermoCoolPoint = evt.value.toFloat()
	ThermoCoolPoint = ThermoCoolPoint.toInteger()
	log.debug("current coolingsetpoint is $ThermoCoolPoint")
    state.ThermoPoint = ThermoPoint
    log.debug "CSP - state.ThermoPoint: $state.ThermoPoint | Level: $state.level"
    if(state.ThermoPoint != state.level){
		Cooling.setLevel(ThermoCoolPoint)
        Cooling.off(delay: 2500)
        }
		Notification()
   }
   }

def Notification(){
          if (pushNotification_Setpoint && pushNotification_Silent) {
            log.debug "Notify --> Thermostat SetPoint: $state.ThermoPoint ($state.TempMode)"
            sendNotificationEvent("Thermostat SetPoint: $state.ThermoPoint " + state.TempMode)
        	}else if(pushNotification_Setpoint && pushNotification_Silent == false){
            sendPush("Thermostat SetPoint: $state.ThermoPoint " + state.TempMode)
}
  log.debug "NOTIFY---------------------------------------------"
  }
