local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("GUNG HUB", "Synapse")
local Tab = Window:NewTab("Main")
local Section = Tab:NewSection("White screen")
Section:NewToggle("White screen", "Click to use White screen", function(state)
game:GetService("RunService"):Set3dRenderingEnabled(state)
end)
local Section = Tab:NewSection("Fastattack")
Section:NewToggle("Fastattack", "Click to use Fastattack", function(state)
local Fast = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
local CameraShaker = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
_G.Fastattack = state -- true\false
game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
        if _G.Fastattack then
        local Lop = Fast[2]
            Lop.activeController.timeToNextAttack = (-math.huge^math.huge*math.huge)
            Lop.activeController.attacking = false
            Lop.activeController.timeToNextBlock = 0
            Lop.activeController.humanoid.AutoRotate = 80
            Lop.activeController.increment = 3
            Lop.activeController.blocking = false
            Lop.activeController.hitboxMagnitude = 80
end
end)
end)
end)
local Section = Tab:NewSection("Ui setting")
Section:NewKeybind("off-on Ui", "F1", Enum.KeyCode.F1, function()
	Library:ToggleUI()
end)
