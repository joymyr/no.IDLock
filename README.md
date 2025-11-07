# ID Lock Z-wave v2

This app adds support for ID Lock Z-wave devices made by [ID Lock AS](https://idlock.no/).
This version 2 is a fork from the original ID Lock app by TedTolboom, and adds support for adding PIN codes to the locks.

## Links:
[ID Lock v2 app on homey store](https://apps.athom.com/app/no.IDLock2)                     
[The original ID Lock app](https://apps.athom.com/app/no.IDLock)                     
[ID Lock v2 Github repository](https://github.com/TedTolboom/no.IDLock)  
[The original ID Lock Github repository](https://github.com/TedTolboom/no.IDLock)      

## Supported devices
* ID Lock 101 (incl. Z-Wave module board 01A)   
* ID Lock 150 (incl. Z-Wave module board 01A)    
* ID Lock 202 (incl. Z-Wave module board 01A)    

## Supported Languages:
* English
* Swedish
* Norwegian

## ID Lock 101, 150 and 202 Features

The ID Lock 101 / ID Lock 150 / ID Lock 202 driver supports the following capabilities:
* Door lock / unlocked
* Door open / closed (contact alarm)
* Heat alarm
* Tamper alarm
* battery (alarm)

Triggers:
* Someone unlocked the door (ID Lock 150 and 202 only)
* Someone locked the door (ID Lock 150 and 202 only)
* Door lock / unlocked
* Generic "an alarm triggered" trigger cards from devices, with additional logic AND condition isolating device
* Door jammed (ID Lock 150 and 202 only)

 Actions:
 * Door lock / unlock
 * Set lock mode (ID Lock 150 and 202 only)
 * Update PIN codes (Synchronized from app settings. Only tested with ID Lock 202)

## App features
In the app settings it's possible to add PIN codes along with name and index.
When synchronizing the lock using the maintenance button, the PIN codes at the selected indexes will be overwritten.
The name of the person who unlocks the door will be available as a tag in the "Someone unlocked the door" trigger. 

 ## Feedback:
Any requests please post them in the [ID Lock app topic on the Homey community Forum](https://community.athom.com/t/161)

## Change Log:

### v 1.4.2
* Fixed bug for z-wave modules pre 1.6

### v 1.4.1
* Added polling for door status as a workaround for instability

### v 1.4.0
* Added possibility to add PIN codes along with the user mapping, and a maintenance button for sending them to the lock

### v 1.3.0
* Updated to SDK3 🎉
* Added Norwegian localization.

### v 1.2.4
* ID Lock 150: Notification cards providing tokens with door unlock condition (Manual, RFID, Keypad or Automatic)
* ID Lock 150: Added "Someone locked the door" flow cards with user and lock condition (Manual, RFID, Keypad or Automatic)
* ID Lock 150: Added auto lock/relock nofication (and setting)
* ID Lock 150: Added "Lock jammed" flow card
* ID Lock 150: Added Action card to set lock mode (home/away)
* Removed unused capability and code
* Added new app setting to select updated indexing mode (use same index numbers as lock on users code/tag), enable the setting to start using, may then break your current flows
* Added Swedish localization.
* Update meshdriver to version 1.3.24 
* Added energy object with battery array.

### v 1.2.3
* Added new settings from firmware released in August 2020.
* Service Pin Mode, added Always valid and disable mode
* Added RFID mode
* Added Updater Mode
* Added Master PIN Mode

### v 1.2.2
* Fix issue where ID lock app is crashing due to missing `triggerSettings` object   

### v 1.2.1
* Add possibility to report different unlocking triggers (Homey / Code / Tag / Button (from inside)); credits to Mats Paulsen   
* Converted settings page to use languages definition (locale) files (english locale); credits to Mats Paulsen      
* Update meshdriver to version 1.2.32   

### v 1.2.0
* Add support for registering user codes and recognizing who unlocked the door (for ID Lock 150) (credits to Mats Paulsen)      
* Minor (cosmetical) modifications to make the app Homey SW v2.0.0 compatible      
* Update meshdriver to version 1.2.28   

### v 1.1.0
* Add support for ID Lock 150         
* Update meshdriver to version 1.2.22   

### v 1.0.2
* Administrative update; add link to community forum topic       

### v 1.0.1
* Remove (and overrule) default `getOnOnline` triggers to try to resolve battery draining issue    

### v 1.0.0
* App store release for ID lock 101 (including Z-Wave module board 01A)

## Future work:
* ID Lock 101: Device specific alarm triggers flow cards (incl. door open state)   
* ID Lock 101: Notification cards providing tokens with door unlock condition (manual, RFID, keypad etc)   
* ID Lock 150: Device specific alarm triggers flow cards (incl. door open state)   
