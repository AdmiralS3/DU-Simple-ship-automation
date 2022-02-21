For this installation you will need the following items.

1. A programming board.
2. 4 Manual Switches, 1 for the programming board, 1 for the door(s), 1 for the landing gear, 1 for forcefield ramps.
3. 3 relays
4. A Telemeter
5. The ability to copy and paste in LUA
6. A very basic understanding of LUA.

Step 1. Press the B key while facing the ship you wish to use this on, and begin placing the items you have gathered where you want them.
Step 2. Remember to place the telemeter on the bottom of the ship.
Step 3. Link the items in the following order....
        Link the Command Chair, Cockpit or other controller to a Manual Switch, then link the switch to the programming board.
        Link the landing gear to a single relay, then link the switch you desire to the landing gear relay, then link the switch to the programming board.
        Link the door(s) to a different single relay, then link the switch you desire to the relay, then link the switch to the programming board.
        Link any forcefields to a different single relay, then link the switch you desire to the relay, then link the switch to the programming board and lastly
        Connect the Telemeter to the programming board.
        
 Step 4. Lets make the system operational. Face the Command Chair, press CTRL +L at the same time, this will open the LUA editor. Find "Unit" from the selection on the left.
 create 2 new filters for start and stop.
        In the new start filter add this code. pbSwitch.activate()
        In the new stop filter add this code. pbSwitch.deactivate()
        
 Step 5. One of the selections on the left will be marked "Slot##" this can be anything from 1 thru 10 depending on how many items you chave connected to the chair prior to this
 installation. Rename the "Slot##" to "pbSwitch", and now click apply.
 
 Step 6. Face the Programing board. press CTRL +L, this will open the LUA editor. On the left you should see 4 "slots" being used. Rename "Slot1" as "landingGearSwitch",
 Rename "Slot2" as "doorSwitch". and rename "Slot3" as "rampSwitch", lastly rename "Slot4" to "telemeter" be sure to use the capitalization just as i did.
 
 Step 7. Select "System" and create new filter "Update" copy and paste the following code into this new filter.

if telemeter.getDistance() < 30 and telemeter.getDistance() > 0 then
    landingGearSwitch.activate()
    doorSwitch.activate()
    rampSwitch.activate()
end
if telemeter.getDistance() > 40 then
    landingGearSwitch.deactivate()
    doorSwitch.deactivate()
    rampSwitch.deactivate()
   end
    
 Step 8. Click apply and exit build mode.

Step 9. If you did everythinbg right, on takeoff your doors will close, your ramps will retract and your landing gear will go up. On landing your ramps will automatically
deploy, your doors will open and your landing gear will deploy.

Troubleshooting:

Unless you are recieving a LUA script error, chances are you did not link something in the order listed above. Try fixing your links exactly as described above.
 
