

local mobs = {} 
getgenv().mob = nil 

for _,v in pairs(game:GetService("Workspace").NPC:GetChildren()) do
    insert = true 
    for _,v2 in pairs(mobs) do if v2 == v.Name then insert = false end end 
    if insert then table.insert(mobs, v.Name) end 
end

-- MOBS
for _,v in pairs(game:GetService("Workspace").NPC:GetChildren()) do
    insert = true 
    for _,v2 in pairs(mobs) do if v2 == v.Name then insert = false end end 
    if insert then table.insert(mobs, v.Name) end 
end
-- CREDIT Kavo Libary

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("GLUE", "DarkTheme") 

-- auto farm
local Main = Window:NewTab("Main")
local MobFarmSection = Main:NewSection("Mob Farm")

local mobdropdown = MobFarmSection:NewDropdown("Choose Mob", "Chooses the mob to autofarm", mobs, function(v)
    getgenv().mob = v
end)

MobFarmSection:NewToggle("Start Mob Farm", "Toggles the autofarming of the mobs", function(v)
    getgenv().autofarmmobs = v
    while wait() do
        if getgenv().autofarmmobs == false then return end 
        if getgenv().mob == nil then 
            game.StarterGui:SetCore("SendNotification", {
                Title = "!! FAIL !!", 
                Text = "Please choose your MOBS",
                Icon = "",
                Duration = 2.5
            })
            getgenv().autofarmmobs = false
            return
        end
        local mob = game:GetService("Workspace").NPC:FindFirstChild(getgenv().mob)
        if mob == nil then
            game.StarterGui:SetCore("SendNotification", { 
                Title = "Info!",
                Text = "There is currently no spawned mobs of this type!\nJust wait until they spawn", 
                Icon = "", 
                Duration = 2.5
            })
            while wait() do 
                wait() 
                if getgenv().autofarmmobs == false then return end 
                if game:GetService("Workspace").NPC:FindFirstChild(getgenv().mob) ~= nil then break; end
            end 
        else
            local mob2 = mob
            while wait() do
                mob = game:GetService("Workspace").NPC:FindFirstChild(getgenv().mob)
                if mob ~= mob2 then break; end
                if getgenv().autofarmmobs == false then return end
                if mob ~= nil then
                    if mob:FindFirstChild("Humanoid") then
                        if mob.Humanoid.Health == 0 then wait(0.1) mob:Destroy() break; end 
                    end
                    if mob:FindFirstChild("HumanoidRootPart") then
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = mob.HumanoidRootPart.CFrame * CFrame.new(0,0,4) 
                        
                          game:GetService'VirtualUser':CaptureController()
game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                    end
                end
            end
        end
    end
end)

local Tab = Window:NewTab("Auto Equip")
local Section = Tab:NewSection("Auto Equip")

local Weaponlist = {}
local Weapon = nil

for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    table.insert(Weaponlist,v.Name)
end

Section:NewDropdown("select weapon", " ", Weaponlist, function(currentOption)
    Weapon = currentOption
end)

Section:NewToggle("Auto Equip", " ", function(a)
AutoEquiped = a
end)

spawn(function()
while wait() do
if AutoEquiped then
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))
end)
end
end
end)

Section:NewKeybind("KeybindText", "KeybindInfo", Enum.KeyCode.RightControl, function()
	Library:ToggleUI()
end)




-- UPDATE MOBS

game:GetService("Workspace").NPC.ChildAdded:Connect(function() 
    for _,v2 in pairs(mobs) do table.remove(mobs, _) end
    
    for _,v in pairs(game:GetService("Workspace").NPC:GetChildren()) do
        insert = true 
        for _,v2 in pairs(mobs) do if v2 == v.Name then insert = false end end
        if insert then table.insert(mobs, v.Name) end 
    end
    mobdropdown:Refresh(mobs)
end)

game:GetService("Workspace").NPC.ChildRemoved:Connect(function() 
    for _,v2 in pairs(mobs) do table.remove(mobs, _) end 
    
    for _,v in pairs(game:GetService("Workspace").NPC:GetChildren()) do 
        insert = true 
        for _,v2 in pairs(mobs) do if v2 == v.Name then insert = false end end 
        if insert then table.insert(mobs, v.Name) end 
    end
    mobdropdown:Refresh(mobs)
end)
