local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("dekpok Hup", "DarkTheme")
local Tab = Window:NewTab("Main")
local Section = Tab:NewSection("Auto farm kaido")

Section:NewToggle("attack and auto quest", "light Only", function(e)
opened = e
end)

spawn(function()
while wait() do
if opened then
	pcall(function()
local plr = game.Players.LocalPlayer
   plr.Character.Light.X.Fire:FireServer()
end)
end
end
end)



spawn(function()
while wait() do
if opened then
pcall(function()
	fireclickdetector(game:GetService("Workspace")["KAIDO ISLANDDDDDDDD"]["KAIDOUU QUESTTT"].ClickPart.ClickDetector)
game:GetService("Players").LocalPlayer.PlayerGui.QuestTake.Accept1.RemoteEvent:FireServer()
end)
end
end
end)


 




local Weaponlist = {}
local Weapon = nil

for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    table.insert(Weaponlist,v.Name)
end

Section:NewDropdown("select weapon", "light Only", Weaponlist, function(currentOption)
    Weapon = currentOption
end)

Section:NewToggle("Auto Equip and tp", "light Only", function(a)
AutoEquiped = a
end)

spawn(function()
while wait() do
if AutoEquiped then
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))
game:GetService("VirtualInputManager"):SendKeyEvent(true,Enum.KeyCode.P,false,game)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-281.998077, 87751.5078, 832.938599, -0.057226032, -3.93335604e-08, -0.99836123, -4.62326888e-08, 1, -3.67480695e-08, 0.99836123, 4.405398e-08, -0.057226032) 
end)
end
end
end)

Section:NewKeybind("Keybind", "Keybind", Enum.KeyCode.RightControl, function()
	Library:ToggleUI()
end)

