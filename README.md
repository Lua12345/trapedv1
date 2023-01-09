local Rayfield = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Rayfield/main/source'))()

local Window = Rayfield:CreateWindow({
	Name = "#Traped | v1",
	LoadingTitle = "Traped | v1",
	LoadingSubtitle = "By Lua and Indra | creds to rayfield",
	ConfigurationSaving = {
		Enabled = true,
		FolderName = nil, -- Create a custom folder for your hub/game
		FileName = "Traped"
	},
        Discord = {
        	Enabled = false,
        	Invite = "ehr29QwzAs", -- The Discord invite code, do not include discord.gg/
        	RememberJoins = true -- Set this to false to make them join the discord every time they load it up
        },
	KeySystem = true, -- Set this to true to use our key system
	KeySettings = {
		Title = "#Traped | v1",
		Subtitle = "Key System",
		Note = "Join the discord gg/ehr29QwzAs",
		FileName = "Traped key",
		SaveKey = false,
		GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
		Key = "hi"
	}
})

local Tab = Window:CreateTab("Da Hood | Streamable", 4483362458) -- Title, Image

local Section = Tab:CreateSection("DISCLAMER: We didnt make all these scripts!")

local Button = Tab:CreateButton({
	Name = "Best Streamable",
	Callback = function()
		-- 0.138
-- 0.11243
loadstring(game:HttpGet("https://raw.githubusercontent.com/topillesrevenge/Streamable-Silent/main/Main"))()
DaHoodSettings.Prediction = 0.123
Aiming.TargetPart = {"Head", "LeftHand", "RightHand", "LeftLowerArm", "RightLowerArm", "LeftUpperArm", "RightUpperArm", "LeftFoot", "LeftLowerLeg", "UpperTorso", "HumanoidRootPart", "LeftUpperLeg", "RightLowerLeg", "RightFoot", "LowerTorso"}
Aiming.FOV = 25
Aiming.FOVSides = 25
Aiming.HitChance = 100
Aiming.ShowFOV = false
	end,
})

local Button = Tab:CreateButton({
	Name = "Eaten's Streamable",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/T0xicJacob/eatensdad/main/eaten-streamable", true))()
--eaten-streamable
	end,
})

local Button = Tab:CreateButton({
	Name = "Streamable 1 | T OFF/ON",
	Callback = function()
        getgenv().RecurringPoint = "UpperTorso"
        getgenv().Hitbox = "UpperTorso"
        getgenv().Keybind = "t"
        getgenv().AimbotStrengthAmount = 0.0335
        getgenv().PredictionAmount = 10
        getgenv().Radius = 25
        getgenv().UsePrediction = true
        getgenv().AimbotStrength = true
        getgenv().FirstPerson = true
        getgenv().ThirdPerson = true
        getgenv().TeamCheck = false
        getgenv().Enabled = true
        
        
        -- // main script use with silent aim / / -- 
        
        loadstring(game:HttpGet("https://raw.githubusercontent.com/tenaaki/GenericAimbot/main/v1.0.0"))()
	end,
})

local Button = Tab:CreateButton({
	Name = "Streamable 2 | Q OFF/ON",
	Callback = function()
		local hotkey = "Q" -- toggle key
local mouse = game.Players.LocalPlayer:GetMouse()



mouse.KeyDown:Connect(function(key)
if key == hotkey then
if getgenv().ValiantAimHacks.SilentAimEnabled == true then
 getgenv().ValiantAimHacks.SilentAimEnabled = false
else
getgenv().ValiantAimHacks.SilentAimEnabled = true
end
end
end)


-- // Services
local Players = game:GetService("Players")

-- // Vars
local LocalPlayer = Players.LocalPlayer
local accomidationfactor = 0.12567724521

-- // Silent Aim Module
local SilentAim = loadstring(game:HttpGet("https://pastebin.com/raw/2f0mGbMP"))()
SilentAim.TeamCheck = false
-- // Metatable vars
local mt = getrawmetatable(game)
local backupindex = mt.__index
setreadonly(mt, false)

-- // Check if player is down
SilentAim.checkSilentAim = function()
    local checkA = (SilentAim.SilentAimEnabled == true and SilentAim.Selected ~= LocalPlayer)
    local playerCharacter = SilentAim.Selected.Character
    local daHood = (playerCharacter.BodyEffects["K.O"].Value == false or playerCharacter:FindFirstChild("GRABBING_CONSTRAINT") ~= nil)

    return (checkA and daHood)
end

-- // Hook
mt.__index = newcclosure(function(t, k)
    if (t:IsA("Mouse") and (k == "Hit")) then
        print(t, k)
        local CPlayer = SilentAim.Selected
        if (SilentAim.checkSilentAim()) then
            if (CPlayer.Character:FindFirstChild("HumanoidRootPart")) then
                return {p=(CPlayer.Character.HumanoidRootPart.CFrame.p+(CPlayer.Character.HumanoidRootPart.Velocity*accomidationfactor))}
            end
        end
    end
    return backupindex(t, k)
end)

-- // Revert
setreadonly(mt, true)
getgenv().ValiantAimHacks.FOV = 9.2
	end,
})

local Button = Tab:CreateButton({
	Name = "Streamable 3 | E OFF/ON",
	Callback = function()
		
_G.PRED = 0.0345

local Aiming = loadstring(game:HttpGet("https://raw.githubusercontent.com/Stefanuk12/Aiming/main/Examples/AimLock.lua"))()
local AimingChecks = Aiming.Checks
local AimingSelected = Aiming.Selected
local AimLockSettings = Aiming.AimLock

Aiming.Settings.FOVSettings.Scale = 30 -- fov
Aiming.ShowCredits = false
Aiming.HitChance = 70 -- Hitchance
Aiming.Settings.FOVSettings.Enabled = false
Aiming.Settings.TracerSettings.Enabled = false
Aiming.UpdateFOV()
Aiming.TargetParts = {"Head","UpperTorso","LowerTorso","RightUpperLeg","LeftUpperLeg","LeftLowerLeg","RightLowerLeg","RightFoot","LeftFoot"}
Aiming.UpdateTracer()
Aiming.AimLock.Enabled = false

-- // Services
local Workspace = game:GetService("Workspace")

-- // Vars
local CurrentCamera = Workspace.CurrentCamera

local DaHoodSettings = {
    Prediction = 0.165,

    SilentAim = true,

    AimLock = AimLockSettings,
    BeizerLock = {
        Smoothness = 0.05,
        CurvePoints = {
            Vector2.new(0.83, 0),
            Vector2.new(0.17, 1)
        }
    }
}
getgenv().DaHoodSettings = DaHoodSettings

-- //
local function ApplyPredictionFormula(SelectedPart)
    return SelectedPart.CFrame + (SelectedPart.Velocity * DaHoodSettings.Prediction)
end

-- // Hook
local __index
__index = hookmetamethod(game, "__index", function(t, k)
    -- // Check if it trying to get our mouse's hit or target and see if we can use it
    if (t:IsA("Mouse") and (k == "Hit" or k == "Target") and AimingChecks.IsAvailable() and DaHoodSettings.SilentAim) then
        -- // Vars
        local SelectedPart = AimingSelected.Part
        local Hit = ApplyPredictionFormula(SelectedPart)

        -- // Return modded val
        return (k == "Hit" and Hit or SelectedPart)
    end

    -- // Return
    return __index(t, k)
end)

-- // Aimlock
function AimLockSettings.AimLockPosition(CameraMode)
    -- // Vars
    local Position
    local BeizerData = {}

    -- // Hit to account prediction
    local Hit = ApplyPredictionFormula(AimingSelected.Part)
    local HitPosition = Hit.Position

    -- //
    if (CameraMode) then
        Position = HitPosition
    else
        -- // Convert 3d -> 2d
        local Vector, _ = CurrentCamera:WorldToViewportPoint(HitPosition)
        local Vector2D = Vector2.new(Vector.X, Vector.Y)

        -- // Vars
        local BeizerLock = DaHoodSettings.BeizerLock

        -- //
        Position = Vector2D
        BeizerData = {
            Smoothness = BeizerLock.Smoothness,
            CurvePoints = BeizerLock.CurvePoints
        }
    end

    -- // Return
    return Position, BeizerData
end

local player = game.Players.LocalPlayer
local mouse = player:GetMouse()

mouse.KeyDown:Connect(function(key)

    if key == "v" then
        


        if DaHoodSettings.SilentAim == false then
        
        DaHoodSettings.SilentAim = true
        
        else
            
        DaHoodSettings.SilentAim = false

        end

    end


end)

local ping 
local Value 
local pingValue 
local PingNumber 

game:GetService("RunService").RenderStepped:Connect(function()
    
     ping = game:GetService("Stats").Network.ServerStatsItem["Data Ping"]:GetValueString()
     Value = tostring(ping)
     pingValue = Value:split(" ")
     PingNumber = pingValue[1]
    
     DaHoodSettings.Prediction = PingNumber / 1000 + _G.PRED
end)
	end,
})

local Button = Tab:CreateButton({
	Name = "Streamable 4 | B OFF/ON",
	Callback = function()
        _G.KEY = "b"
        _G.PART = "Head", "LeftHand", "RightHand", "LeftLowerArm", "RightLowerArm", "LeftUpperArm", "RightUpperArm", "LeftFoot", "LeftLowerLeg", "UpperTorso", "HumanoidRootPart", "LeftUpperLeg", "RightLowerLeg", "RightFoot", "LowerTorso"
        _G.PRED = 0.032
        loadstring(game:HttpGet("https://raw.githubusercontent.com/GuizzyisbackV2LOL/GuizzyLuaThusk4t5345345/main/LuaObf"))()
        
        
        
        
        --Reslover
        
        --Remove reslover if u dont like
        
        
        -- I add the whatever
        
        ---------------------
        
        
        local RunService = game:GetService("RunService")
        
        RunService.Heartbeat:Connect(function()
            pcall(function()
                for i,v in pairs(game.Players:GetChildren()) do
                    if v.Name ~= game.Players.LocalPlayer.Name then
                        local hrp = v.Character.HumanoidRootPart
                        hrp.Velocity = Vector3.new(hrp.Velocity.X, 0, hrp.Velocity.Z)    
                        hrp.AssemblyLinearVelocity = Vector3.new(hrp.Velocity.X, 0, hrp.Velocity.Z)   
                    end
                end
            end)
        end)
	end,
})

local Button = Tab:CreateButton({
	Name = "Streamable 5",
	Callback = function()
		loadstring(game:HttpGet("https://pastebin.com/raw/SbtCNZg7"))()
DaHoodSettings.Prediction = 0.131
Aiming.TargetPart = {"Head", "UpperTorso", "LowerTorso", "RightFoot", "LeftFoot"}
Aiming.FOV = 12
Aiming.FOVSides = 12
Aiming.HitChance = 100
	end,
})

local Button = Tab:CreateButton({
	Name = "Streamable 6",
	Callback = function()
		-- 0.138
-- 0.11243
loadstring(game:HttpGet("https://raw.githubusercontent.com/topillesrevenge/Streamable-Silent/main/Main"))()
DaHoodSettings.Prediction = 0.121
Aiming.TargetPart = {"Head", "LeftHand", "RightHand", "LeftLowerArm", "RightLowerArm", "LeftUpperArm", "RightUpperArm", "LeftFoot", "LeftLowerLeg", "UpperTorso", "HumanoidRootPart", "LeftUpperLeg", "RightLowerLeg", "RightFoot", "LowerTorso"}
Aiming.FOV = 25
Aiming.FOVSides = 25
Aiming.HitChance = 400
Aiming.ShowFOV = false
	end,
})

local Button = Tab:CreateButton({
	Name = "Streamable 7",
	Callback = function()
		-- // CHANGE STREAMABLE SETTINGS HERE
_G.PRED = 0.025
local Aiming = loadstring(game:HttpGet("https://raw.githubusercontent.com/Ezucii/new/main/sourceeeeeeeeeeeeee.lua"))()
Aiming.TeamCheck(false)
Aiming.ShowFOV = false
Aiming.FOV = 8
-- // SERVICES
local Workspace = game:GetService("Workspace")
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")

-- // Vars
local LocalPlayer = Players.LocalPlayer
local Mouse = LocalPlayer:GetMouse()
local CurrentCamera = Workspace.CurrentCamera

local DaHoodSettings = {
    SilentAim = true,
    AimLock = false,
    Prediction = 0.025,
    AimLockKeybind = Enum.KeyCode.E
}
getgenv().DaHoodSettings = DaHoodSettings


function Aiming.Check()
    -- // Check A
    if not (Aiming.Enabled == true and Aiming.Selected ~= LocalPlayer and Aiming.SelectedPart ~= nil) then
        return false
    end

    -- // Check if downed
    local Character = Aiming.Character(Aiming.Selected)
    local KOd = Character:WaitForChild("BodyEffects")["K.O"].Value
    local Grabbed = Character:FindFirstChild("GRABBING_CONSTRAINT") ~= nil

    -- // Check B
    if (KOd or Grabbed) then
        return false
    end

    -- //
    return true
end

local __index
__index = hookmetamethod(game, "__index", function(t, k)
    -- // Check if it trying to get our mouse's hit or target and see if we can use it
    if (t:IsA("Mouse") and (k == "Hit" or k == "Target") and Aiming.Check()) then
        -- // Vars
        local SelectedPart = Aiming.SelectedPart

        -- // Hit/Target
        if (DaHoodSettings.SilentAim and (k == "Hit" or k == "Target")) then
            -- // Hit to account prediction
            local Hit = SelectedPart.CFrame + (SelectedPart.Velocity * DaHoodSettings.Prediction)

            -- // Return modded val
            return (k == "Hit" and Hit or SelectedPart)
        end
    end

   
    return __index(t, k)
end)

local player = game.Players.LocalPlayer
local mouse = player:GetMouse()

mouse.KeyDown:Connect(function(key)
    if key == "v" then
        if Aiming.Enabled == false then
        Aiming.Enabled = true
        else
        Aiming.Enabled = false
        end
    end
end)


RunService.RenderStepped:Connect(function()

    local ping = game:GetService("Stats").Network.ServerStatsItem["Data Ping"]:GetValueString()
    local Value = tostring(ping)
    local pingValue = Value:split(" ")
    local PingNumber = pingValue[1]
    
    DaHoodSettings.Prediction = PingNumber / 1000 + _G.PRED
    
                    if Aiming.Character.Humanoid.Jump == true and AimlockTarget.Character.Humanoid.FloorMaterial == Enum.Material.Air then
                    Aiming.TargetPart = "RightFoot"
                else
                    Aiming.Character:WaitForChild("Humanoid").StateChanged:Connect(function(new)
                    
                    if new == Enum.HumanoidStateType.Freefall then
                    Aiming.TargetPart = "RightFoot"
                    else
                    
                    Aiming.TargetPart = Aiming.SelectedPart
                    
                    end
                    
                    end)
                    
                end

end)
	end,
})
