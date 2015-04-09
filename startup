--INSTRUCTIONS

--Place bundled cable on back please
if rs.getBundledInput("back") == false then
    print("Please place bundled cable on back")
    os.exit()
end



--(TABLE)

--up == white
--down == black

--ground level == 1 == red
--level 1 == 2 == blue
--level 2 == 3 == orange
--level 3 == 4 == green

--VARIABLES -- where you set the variables


mon1 = peripheral.wrap("monitor_0")
mon2 = peripheral.wrap("monitor_1")
mon3 = peripheral.wrap("monitor_2")
mon4 = peripheral.wrap("monitor_3")

elevatorTo = 0 -- value of requested floor. 0 is standing by

elevatorAt = function()
    if rs.testBundledInput("back", colors.red) then
        return 1
    end
    if rs.testBundledInput("back", colors.blue) then
        return 2
    end
    if rs.testBundledInput("back", colors.orange) then
        return 3
    end
    if rs.testBundledInput("back", colors.green) then
	   return 4
    end

end -- on activation, checks where its at and returns position.

upOrDown = function()
    if elevatorTo >= 0 then
        
        local max = elevatorAt() - elevatorTo
        if max > 0 then
            sendLevel = "up"
        else if max < 0 then
            sendLevel = "down"
        else if elevatorTo == elevatorAt() then
            x2 = false
        end
        end
        
    end
end
end -- checks if it needs to go up or down
    

--FUNCTIONS -- where you make the functions for later

move = function()
  if sendLevel == "up" then
    rs.setBundledOutput("back", colors.white)
    os.sleep(2)
    rs.setBundledOutput("back", 0)
  else
    rs.setBundledOutput("back", colors.black)
    os.sleep(2)
    rs.setBundledOutput("back", 0)
  end
end

go = function()
    local o = true
    upOrDown()
    while o do
        move()
        elevatorAt()
        if elevatorAt() == elevatorTo then
            o = false
            elevatorTo = 0
            rs.setBundledOutput("back", 0)
        end
        os.sleep(2)
    end
end -- activates elevator with needed information

button1 = function()
    local disc = "Ground"
    mon1.setCursorPos(2,2)
    mon2.setCursorPos(2,2)
    mon3.setCursorPos(2,2)
    mon4.setCursorPos(2,2)

    mon1.setTextColor(1)
    mon2.setTextColor(1)
    mon3.setTextColor(1)
    mon4.setTextColor(1)

    mon1.setTextScale(2)
    mon2.setTextScale(2)
    mon3.setTextScale(2)
    mon4.setTextScale(2)

    mon1.setBackgroundColor(colors.blue)
    mon2.setBackgroundColor(colors.blue)
    mon3.setBackgroundColor(colors.blue)
    mon4.setBackgroundColor(colors.blue)

    mon1.write(disc)
    mon2.write(disc)
    mon3.write(disc)
    mon4.write(disc)
    
    local event, monitor, x, y = os.pullEvent("monitor_touch")
    
    if x >= 2 and x < (2 + string.len(disc)) and y == 2 then
        elevatorTo = 1
        mon1.setCursorPos(2,2)
        mon2.setCursorPos(2,2)
        mon3.setCursorPos(2,2)
        mon4.setCursorPos(2,2)
        mon1.setBackgroundColor(colors.green)
        mon2.setBackgroundColor(colors.green)
        mon3.setBackgroundColor(colors.green)
        mon4.setBackgroundColor(colors.green)
        os.sleep(2)
        mon1.setBackgroundColor(colors.blue)
        mon2.setBackgroundColor(colors.blue)
        mon3.setBackgroundColor(colors.blue)
        mon4.setBackgroundColor(colors.blue)
        go()
    end
end -- on pressed, sets level request and activates elevator

button2 = function()
    local disc = "Level 1"
    
    mon1.setCursorPos(2,4)
    mon2.setCursorPos(2,4)
    mon3.setCursorPos(2,4)
    mon4.setCursorPos(2,4)
    mon1.setTextColor(1)
    mon2.setTextColor(1)
    mon3.setTextColor(1)
    mon4.setTextColor(1)
    mon1.setTextScale(2)
    mon2.setTextScale(2)
    mon3.setTextScale(2)
    mon4.setTextScale(2)
    mon1.setBackgroundColor(colors.blue)
    mon2.setBackgroundColor(colors.blue)
    mon3.setBackgroundColor(colors.blue)
    mon4.setBackgroundColor(colors.blue)
    mon1.write(disc)
    mon2.write(disc)
    mon3.write(disc)
    mon4.write(disc)
    
    local button, monitor, x, y = os.pullEvent("monitor_touch")
    
    if x >= 2 and x < (2 + string.len(disc)) and y == 4 then
        elevatorTo = 2
        mon1.setCursorPos(2,4)
        mon2.setCursorPos(2,4)
        mon3.setCursorPos(2,4)
        mon4.setCursorPos(2,4)
        mon1.setBackgroundColor(colors.green)
        mon2.setBackgroundColor(colors.green)
        mon3.setBackgroundColor(colors.green)
        mon4.setBackgroundColor(colors.green)
        os.sleep(2)
        mon1.setBackgroundColor(colors.blue)
        mon2.setBackgroundColor(colors.blue)
        mon3.setBackgroundColor(colors.blue)
        mon4.setBackgroundColor(colors.blue)
        go()
    end
end

button3 = function()
    local disc = "Level 2"
    
    mon1.setCursorPos(2,6)
    mon2.setCursorPos(2,6)
    mon3.setCursorPos(2,6)
    mon4.setCursorPos(2,6)
    mon1.setTextColor(1)
    mon2.setTextColor(1)
    mon3.setTextColor(1)
    mon4.setTextColor(1)
    mon1.setTextScale(2)
    mon2.setTextScale(2)
    mon3.setTextScale(2)
    mon4.setTextScale(2)
    mon1.setBackgroundColor(colors.blue)
    mon2.setBackgroundColor(colors.blue)
    mon3.setBackgroundColor(colors.blue)
    mon4.setBackgroundColor(colors.blue)
    mon1.write(disc)
    mon2.write(disc)
    mon3.write(disc)
    mon4.write(disc)
    
    local button, monitor, x, y = os.pullEvent("monitor_touch")
    
    if x >= 2 and x < (2 + string.len(disc)) and y == 6 then
        elevatorTo = 3
        mon1.setCursorPos(2,6)
        mon2.setCursorPos(2,6)
        mon3.setCursorPos(2,6)
        mon4.setCursorPos(2,6)
        mon1.setBackgroundColor(colors.green)
        mon2.setBackgroundColor(colors.green)
        mon3.setBackgroundColor(colors.green)
        mon4.setBackgroundColor(colors.green)
        os.sleep(2)
        mon1.setBackgroundColor(colors.blue)
        mon2.setBackgroundColor(colors.blue)
        mon3.setBackgroundColor(colors.blue)
        mon4.setBackgroundColor(colors.blue)
        go()
    end
end

button4 = function()
    local disc = "Level 3"
    
    mon1.setCursorPos(2,8)
    mon2.setCursorPos(2,8)
    mon3.setCursorPos(2,8)
    mon4.setCursorPos(2,8)
    mon1.setTextColor(1)
    mon2.setTextColor(1)
    mon3.setTextColor(1)
    mon4.setTextColor(1)
    mon1.setTextScale(2)
    mon2.setTextScale(2)
    mon3.setTextScale(2)
    mon4.setTextScale(2)
    mon1.setBackgroundColor(colors.blue)
    mon2.setBackgroundColor(colors.blue)
    mon3.setBackgroundColor(colors.blue)
    mon4.setBackgroundColor(colors.blue)
    mon1.write(disc)
    mon2.write(disc)
    mon3.write(disc)
    mon4.write(disc)
    
    local button, monitor, x, y = os.pullEvent("monitor_touch")
    
    if x >= 2 and x < (2 + string.len(disc)) and y == 8 then
        elevatorTo = 4
        mon1.setCursorPos(2,8)
        mon2.setCursorPos(2,8)
        mon3.setCursorPos(2,8)
        mon4.setCursorPos(2,8)
        mon1.setBackgroundColor(colors.green)
        mon2.setBackgroundColor(colors.green)
        mon3.setBackgroundColor(colors.green)
        mon4.setBackgroundColor(colors.green)
        os.sleep(2)
        mon1.setBackgroundColor(colors.blue)
        mon2.setBackgroundColor(colors.blue)
        mon3.setBackgroundColor(colors.blue)
        mon4.setBackgroundColor(colors.blue)
        go()
    end
end

--PROGRAM -- where the program starts

mon1.clear()
mon2.clear()

while true do
    
    mon1.setBackgroundColor(colors.lightGray)
    mon2.setBackgroundColor(colors.lightGray)
    mon3.setBackgroundColor(colors.lightGray)
    mon4.setBackgroundColor(colors.lightGray)
    
    button1()
    button2()
    button3()
    button4()
    os.sleep(1)
end -- will run forever
