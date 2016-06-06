Rule Machine User Guide

Rule Machine460 is a powerful automating tool for SmartThings. 

The Rule Machine User Guide has four sections below:
•Conditions and Trigger Events
•Actions
•Expert Features: Custom Commands
•Restrictions

Conditions and Trigger Events

Rules and Triggers respond to events on the selected devices. In the case of a Rule, it evaluates its rule upon any event affecting its Conditions. In the case of a Trigger, it is fired whenever the selected event occurs.

Devices with the following capabilities may be Conditions or Trigger Events: [with noted exceptions]


Acceleration
  "active" or  "inactive"

Battery 
  value

Button [Only available as Trigger Event]
 "number":  "pressed"or "held"

Contact:
  "open" or "closed"

Certain Time [Only available as Trigger Event]
  at a certain time, including sunrise or sunset with offset

Days of week [Only available as Condition]
  "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"

Dimmer level
 value

Door
 "open", "closed", "opening", "closing", "unknown"

Energy meter
 value

Garage door
  "open", "closed", "opening", "closing", "unknown"

Humidity
  value

Illuminance
  value

Lock
  "locked" or "unlocked"

Mode
  any of your location’s modes

Motion
  "active" or "inactive"

Music player
  "playing", "paused", or "stopped"

Periodic [Only available as Trigger Event]
  Allows periodic schedules for minutes, hourly, daily, weekly, monthly or yearly

Physical switch [only available as Trigger Event]
  "on" or "off"

Power meter
  value

Presence
  "present" / "not present"  or  "arrives" / "leaves"

Private Boolean
  "true" or "false"

Routine [only available as Trigger Event]
   runs

Rule truth
   "true" or "false"

Smart Home Monitor
   "Arm (away)", "Arm (stay)" or "Disarm"

Switch
  "on" or "off"

Temperature
  value

Thermostat mode
  "heat", "cool", "auto", "off" or "emergency heat"

Thermostat state
  "heating", "cooling", "fan only", "idle", "pending heat" or "pending cool"

Time of day [Only available as Condition]
  between two times, including sunrise or sunset with offsets

Water sensor
  "dry" or "wet"

Note: value means compare current value to a number or to another device with an offset

Limitation: a rule may only have at most one each of Days of week, Mode, or Time of day as conditions. If you need logic for two different Time of day periods, that would have to be done in two separate rules. A trigger can have at most one each of Certain Time or Mode change, and at most two Periodic schedules as trigger events. If you need more time events, that would have to be done in separate triggers.

Actions
•Rules, Triggers, Conditional Triggers and Actions run selected Actions. 
•Rules and Conditional Triggers run Actions for True or Actions for False depending on Rule evaluation outcome. 
•Triggers and Actions just run Actions.


Delay these actions [by minutes, seconds, or milliseconds, with optional cancel on change, or random time]

This selection causes all of the selected actions in a Rule (for Actions for True, Actions for False, or simply Actions) to be delayed. A delay of minutes or seconds may apply for any action. Delays of less than 60 seconds may not work reliably. A delay of milliseconds only applies for actions on, off, dim level, open, and close. For delays in Rules of minutes or seconds, an option to Cancel on truth change is available. If selected, should the rule truth change before expiration of the delay, the delayed actions are cancelled. A random delay is also available. This will be for a random number of seconds up to the delay time selected.

Turn on these switches
  This action turns on the selected switches.

Turn off these switches
  This action turns off the selected switches.

Toggle these switches
  If the selected switches are on, this action turns them off, and if they are on, it turns them off.

Turn on or off these switches after a delay
  This action turns on or turns off the selected switches after a delay. The choice between on or off is available, with off being the default. Delays of minutes, seconds or milliseconds may be selected. Delays of less than 60 seconds may be less reliable. Delays of up to 5000 milliseconds seem to be fairly reliable.

Turn on or off these switches after a delay, pending cancellation
  This action turns on or turns off the selected switches after a delay, pending a change of rule truth. Should rule truth change before the expiration of the delay, the delayed action is cancelled. The choice between on or off is available, with off being the default. This action is not available for Triggers or Actions, only for Rules. (Rules Rule!)

Set these dimmers
  This action sets the selected dimmers to the selected level, or tracks another dimmer's level. 

Track event dimmer works along with a Condition or Trigger Event of “Dimmer level”. When this dimmer level event causes the rule to run this action, the selected dimmers are set to the same level as the dimmer that triggered the rule. This can be used in automations where a group of dimmers follow another dimmer as it changes level. The typical usage for a Trigger is to have a Trigger Event of "Dimmer level >= 0", and then Track Dim as the action.

Set these other dimmers
  This action sets the selected dimmers to the selected level, allowing a second dimmer level for each rule.

Toggle these dimmers
  If the selected dimmers are on, this action turns them off. If the selected dimmers are off, it sets them to the selected level.

Adjust these dimmers
  This action adjusts the selected dimmers’ level up or down by the selected amount. Dimmer values range from 0 to 99. Adjusting to 0 does not necessarily mean that the device is turned off.

Set these dimmers per mode
  This action sets the selected dimmers to the level selected for the current mode. Multiple modes with corresponding dimmer levels can be selected. 

Capture the state of these switches
  This action captures the state of the selected switches, including on/off, hue, saturation and level. The captured state can be used in the "Restore the state of captured switches" action.

Restore the state of captured switches
  This action restores the state to the devices selected in the "Capture the state of these switches" action, restoring the devices to the state captured by the most recent Capture action run. It is up to the user to design and use the rule such that Capture occurs prior to Restore. It is possible to select a delay for Restore, and optionally to Cancel such a delay on rule truth change.

Set color temperature for these bulbs
  This action sets the colour temperature for the selected bulbs. {a sic compromise}

Set color for these bulbs
  This action sets the colour and level for the selected bulbs.

Open these garage doors
  This action opens the selected garage doors.

Close these garage doors
  This action closes the selected garage doors.

Locks to lock
  This action locks the selected locks.

Locks to unlock
  This action unlocks the selected locks.

Adjust this fan — Low, Medium, High, Off
  This action adjusts a fan switch with successive trigger events first to low, then medium, then high, then off. To simply set a fan switch to low, medium or high, treat it as a dimmer and set the dimmer level to 20, 50, or 80 respectively.

Open these valves
  This action opens the selected valves.

Close these valves
  This action closes the selected valves.

Set these thermostats
  This action sets various settings of a thermostat. The thermostat mode, heating setpoint, cooling setpoint, and fan setting can be selected. It is possible to adjust the heating or cooling setpoints up or down by a selected amount. For thermostat mode, the choices are "auto", "heat", "cool", "off" and "emergency heat". For the setpoints and adjustments, the number input may have a decimal fraction, e.g. 21.5, which is helpful with degrees Celsius devices. For fan setting, the choices are "on" and "auto".

Set the alarm state
  This action sets the Smart Home Monitor alarm state to “Arm (away)”, “Arm (stay)”, or “Disarm”.

Set the mode
  This action sets the location mode to the selected mode.

Run a Routine
  This action causes the selected Routine to run.

Send or speak a message
  This action sends a push or notification, as selected, and optionally includes the name of the device that triggered the actions. It can also send an SMS to multiple phones (separate the numbers with *). This action also supports devices that speak or process text to speech.

Take photos
  This action takes a burst of photos with the selected camera.

Evaluate Rules
  This action causes the selected Rules to be evaluated.

Run Rule Actions
  This action causes the Actions for True or Actions for the selected Rules to be run.

Update Rules
  This action causes the selected Rules to be updated to refresh subscriptions and schedules.

Evaluate Rules after delay
  This action causes the selected Rules to be evaluated after a delay of a selected number of minutes. This action allows the Rule it is used in to be the Rule selected to be evaluated after the delay; this is a looping mechanism. 

Set private Boolean
  This action sets the Rule’s private Boolean variable to true or false, and/or the private Boolean variable of other Rules to true or false. There is an option to delay this. If the action is to set the rule's own private Boolean with a delay, the delayed action is treated as an event, causing rule evaluation or possibly a trigger event. Setting a private Boolean of another rule is treated as an event by that rule. Setting a rule's own private Boolean is not an event unless it is delayed. Private Boolean with a delay may be used to create a looping mechanism. It is possible to have a delay cancelled upon rule truth change.

Run custom commands
  This action runs selected custom commands. Custom commands must first be created and saved in the Expert Features section of Rule Machine.

Expert Features: Custom Commands

With custom commands, you can explore any device you have to see the commands that it offers. There are two steps required to use those commands in your rules, and then a third to manage your commands.
1.Create, test and save your custom command with "Tap to create Custom Commands" on the Rule Machine main page
2.Incorporate the saved custom command into your rules with "Run custom commands"
3.Manage custom commands with "Delete saved commands" and "Test saved command on..."


1. Create, test and save your custom command
•Open Rule Machine
•Under Expert Features "Tap to create Custom Commands"
•Select a capability for devices to test for available commands (if unsure, try Actuator)
•Select a device of that capability to test for commands
•Select New custom command to see the available commands, then select the command you want
•Once selected, the command will be tested on the selected device and the results of the command execution shown
•Add any required parameters to the command
•After the command is executing against the device as expected, select Save command now, then Done, then Done again to return to the Custom Commands page
•The saved custom command will now be available in your new and existing rules

2. Select the custom command to run in your rule and the devices to run it on
•Create a new rule or edit an existing one
•In the Actions section (at the very bottom), select Run custom command, then select the custom command (saved above) and the devices to run it on

Be sure that each device selected supports the selected command; any errors will be trapped and shown in the logs.

3. Manage custom commands
One or more custom commands can be removed by selecting them in Delete Custom Commands, then Delete commands now, then Done. You can also test saved custom commands against other devices you might select.

Restrictions

The Restrictions section of defining a rule allows you to restrict when or under what conditions the rule may run. When restricted, the rule does nothing and timers are ignored. Restrictions may seem similar to some Conditions, but they are actually quite distinct. Restrictions do not participate in the logic of the Conditions and the Rule in any way. Restrictions simply enable or disable the rule from doing things. Conditions, on the other hand, are subscribed to their events, and those events cause rule evaluations to occur, and possibly actions to run. A restriction doesn't do any of those things, it merely restricts.

The restriction options are:

•Only during a certain time [including sunrise or sunset with offsets

This setting restricts when a rule may run to a certain time period, start and stop. Outside of the selected time period, the rule will do nothing, all outstanding timers are ignored.

•Only on certain days of the week

This setting restricts when a rule may run to certain days of the week. On days not selected, the rule will do nothing, all outstanding timers are ignored.

•Only when mode is ...

This setting restricts the rule to only run when the location's mode is one of the modes selected. At any time when not in one of the selected modes, the rule will do nothing, all outstanding timers are ignored.

•Switch to disable Rule

This setting selects a switch device, possibly virtual, which if on disables the rule. If off, the rule is enabled. There is an option to reverse the meanings of on and off, so that on means enable, and off means disable. When the rule is disabled, the rule will do nothing, all outstanding timers are ignored.

•Enable/Disable with private Boolean?

This setting allows the rule's private Boolean variable to act as an enable / disable selector. If this option is selected, then the rule is enabled when its private Boolean is true, and is disabled when its private Boolean is false. Other rules may set the rule's private Boolean. The private Boolean variable is initialized to true when a rule is created, so when selecting this option to use private Boolean to disable, the rule will start out enabled. When the rule is disabled, the rule will do nothing, all outstanding timers are ignored.
