# UCR-Plugins
Experimental and niche plugins for UCR

## Using these plugins
Download a release from the [releases page](https://github.com/HidWizards/UCR-Plugins/releases), and extract the `.dll` files within to the UCR plugins folder  
You may need to unblock the DLLs in order for them to work - you can run `Unblocker.ps1` **as admin** to do this for you.  

## Experimental Core Plugins
### AxisToDelta
Joystick to Mouse.  
Known unstable. Keep profile GUI minimized while using to reduce CPU usage

### DeltaToAxis
Mouse to Joystick.  
Known unstable. Keep profile GUI minimized while using to reduce CPU usage

### ButtonToButtonsLongPress
Long Press version of ButtonToButton  

## Niche Plugins
### AxesRangeToButton  
Allows you to define a position in X/Y space that triggers a button.  
Intended for use with eg rose selection menus, virtual H shifters etc.

### AxesToAxesRotation
Rotates a joystick by a certain number of degrees.  
This is to try and counter the issue using console controller thumbsticks where your thumb axis does not line up with the stick axis, typically resulting in you inputting up-right when you meant to input up.  

### AxesToAxesTrim
Allows you to set the center point of a stick on the fly.  
Has two axis inputs, plus a "Trim" button and a "Reset Trim" button.  
At the instant you press the trim button, the current stick position is recorded.  
Upon release of the trim button, this trim is applied to the stick.  
Subsequent trims will alter the existing trim setting.  
The Reset button removes all trim.  
Requested by hon0 in Discord.

### AxisToAxisCumulative
Allows you to map one axis to another in "Cumulative" mode.  
When you move the input axis, the amount of deflection determines how quickly the output axis moves in that direction.  
Useful, for example, if you wish to use a stick which springs back to center to control a throttle.  
Requested by Spadino

## Developer Notes
### Building  
The `_Build` project references `UCR.Core.dll` and when built, copies it into it's solution folder.  
All the plugins then reference that DLL, so that if you wish to target a different `UCR.Core.dll`, you only have to change it in one place.  
If you clone this repo to the same parent folder as the `UCR` repo, then the reference in `_Build` should just work (As it uses `..\..`)
