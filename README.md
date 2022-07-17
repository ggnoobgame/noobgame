   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-281.998077, 87751.5078, 832.938599, -0.057226032, -3.93335604e-08, -0.99836123, -4.62326888e-08, 1, -3.67480695e-08, 0.99836123, 4.405398e-08, -0.057226032) 

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("dekpok Hup", "Synapse")
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
end)
end
end
end)

Section:NewKeybind("Keybind", "Keybind", Enum.KeyCode.RightControl, function()
	Library:ToggleUI()
end)

local Tab = Window:NewTab("Teleport")
local Section = Tab:NewSection("To")


Section:NewButton("STARTER lv1+", " ", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(444.875977, 59.3016624, -559.586609, 0.0462093353, -0, -0.998931766, 0, 1, -0, 0.998931766, 0, 0.0462093353)
end)

Section:NewButton("SNOW lv50+", " ", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1156.89038, 38.2675972, 421.304321, -0.512068033, -5.57608253e-08, 0.858944893, -9.92223192e-08, 1, 5.76549963e-09, -0.858944893, -8.22741768e-08, -0.512068033)
end)

Section:NewButton("SAND lv100+", " ", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-577.620056, 23.3571854, 1500.27002, -0.997186422, 0, 0.0749610513, 0, 1, 0, -0.0749610513, 0, -0.997186422)
end)

Section:NewButton("SKY lv250+", " ", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-4660.2334, 4294.85742, 323.136353, -0.999957323, 0, -0.00923635624, 0, 1, 0, 0.00923635624, 0, -0.999957323)
end)

Section:NewButton("END TOWN lv550+", " ", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2223.87915, 37.1282997, 1965.81482, 0.99383378, 0.000260314206, -0.110879816, -0.0108770542, 0.995402932, -0.0951559097, 0.110345326, 0.0957752168, 0.989267886)
end)

Section:NewButton("MMM lv900+", " ", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2555.85815, 49.9524994, -44.6238594, 0.999000192, -0.0211218279, -0.0394021459, 0.0148454513, 0.988072336, -0.153273061, 0.0421695746, 0.152534857, 0.987398028)
end)

Section:NewButton("DARK lv1350+", " ", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3319.47021, 66.5848236, 3964.00171, 0.744877338, -0, -0.667201459, 0, 1, -0, 0.667201459, 0, 0.744877338)
end)

Section:NewButton("DARK ROOM", " ", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3635.40259, 75.9166107, 3718.97437, -0.781180739, -6.8756334e-10, 0.62430495, -3.39178321e-08, 1, -4.13394048e-08, -0.62430495, -5.3468618e-08, -0.781180739)
end)

Section:NewButton("GOD ROOM", " ", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3641.05542, 147.76944, 3840.04199, 0.710120559, -8.50669224e-08, -0.704080105, 1.07318023e-07, 1, -1.25812258e-08, 0.704080105, -6.66262991e-08, 0.710120559)
end)

Section:NewButton("BLUE", " ", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(........)
end)

local Tab = Window:NewTab("Teleport")
local Section = Tab:NewSection("To")

Section:NewToggle("random fruit or GOD BOX", " ", function(d)
randomed = d
end)

spawn(function()
while wait() do
if randomed then
	pcall(function()
local plr = game.Players.LocalPlayer
   plr.Character.Light.X.Fire:FireServer()
end)
end
end
end)
