seedid = 5640 --magplant remote

function hook(var, packet)
  if var[0] == "OnSDBroadcast" then
log("Blocking SDB")
    return true
  end
end
AddCallback("anti sdb","OnVarlist",hook)
EditToggle("MenuToggle", false)
EditToggle("ModFly", true)

local function Place(x, y)
  local player = GetLocal()
  local pkt_punch = {
    type = 3,
    int_data = seedid,
    pos_x = player.pos_x,
    pos_y = player.pos_y,
    int_x = x,
    int_y = y,
  }
  SendPacketRaw(pkt_punch)
end

for y = 0, 193 do 
for x = 0, 199 do
local tile = GetTile(x,y)
if tile.fg == 0 then
FindPath(x,y)
Sleep(100)
Place(x,y)
Sleep(100)

end
end
end

EditToggle("ModFly", false)
EditToggle("Stop Luascript", true)


