if telemeter.raycast().distance < 30 and telemeter.raycast().distance > 0 then
    landingGearSwitch.activate()
    doorSwitch.activate()
    rampSwitch.activate()
end
if telemeter.raycast().distance > 40 then
    landingGearSwitch.deactivate()
    doorSwitch.deactivate()
    rampSwitch.deactivate()
   end
    
