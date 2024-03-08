function TP(targetCFrame)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = targetCFrame
end

function MonA()
    free = free or "Bandit"
    
    if free == "Bandit" then
        MONName = "Bandit [LV.5]"
    elseif free == "Bandit Leader" then
        MONName = "Bandit Leader [LV.15]"
    elseif free == "Clown Pirate" then
        MONName = "Clown Pirate [LV.50]"
    elseif free == "Marine" then
        MONName = "Marine [LV.300]"
    elseif free == "Monkey" then
        MONName = "Monkey [LV.750]"
    elseif free == "Monkey King" then
        MONName = "Monkey King [LV.1000]"
    elseif free == "Bomb Man" then
        MONName = "Bomb Man [LV.1500]"
    elseif free == "Sand Man" then
        MONName = "Sand Man [LV.2000]"
    elseif free == "Snow Bandit" then
        MONName = "Snow Bandit [LV.1750]"
    elseif free == "Snow Bandit Leader" then
        MONName = "Snow Bandit Leader [LV.2350]"
    end
end

function BossA()
    Bo = Bo or "Bandit"
    
    if Bo == "ไม่เลือก" then
        BossName = "ไม่เลือก [LV.0]"
    elseif Bo == "Natsu" then
        BossName = "Natsu [LV.5]"
    elseif Bo == "Choso" then
        BossName = "Choso [LV.10]"
    elseif Bo == "Ichigo" then
        BossName = "Ichigo [LV.15]"
    elseif Bo == "Killua" then
        BossName = "Killua [LV.20]"
    elseif Bo == "Gojo [Unleashed]" then
        BossName = "Gojo [Unleashed] [LV.25]"
    elseif Bo == "Sukuna [Half Power]" then
        BossName = "Sukuna [Half Power] [LV.30]"
    elseif Bo == "Gojo" then
        BossName = "Gojo [LV.35]"
    elseif Bo == "Sukuna" then
        BossName = "Sukuna [LV.40]"
    elseif Bo == "Shank" then
        BossName = "Shank [LV.45]"
    elseif Bo == "Kashimo" then
        BossName = "Kashimo [LV.50]"
    elseif Bo == "Artoria" then
        BossName = "Artoria [LV.55]"
    elseif Bo == "Bomb Man" then
        BossName = "Bomb Man [LV.60]"
    elseif Bo == "Sand Man" then
        BossName = "Sand Man [LV.65]"
    elseif Bo == "Monkey King" then
        BossName = "Monkey King [LV.70]"
    elseif Bo == "Bandit Leader" then
        BossName = "Bandit Leader [LV.75]"
    end
end


function QuestA()
    if free == "Bandit" then
        CFrameQuest = CFrame.new(-953.566528, 34.5999947, -552.164612, -0.0109250434, -3.3378329e-09, -0.999940336, 1.94075778e-09, 1, -3.35923622e-09, 0.999940336, -1.97734162e-09, -0.0109250434)
        QuestZ = "Bandit Quest"
    elseif free == "Bandit Leader" then
        CFrameQuest = CFrame.new(-1097.55042, 34.6000023, -492.550354, -0.0683717504, 2.67226739e-08, 0.997659922, 5.38579563e-08, 1, -2.30943531e-08, -0.997659922, 5.21529238e-08, -0.0683717504)
        QuestZ = "Bandit Leader Quest"
    elseif free == "Clown Pirate" then
        CFrameQuest = CFrame.new(-71.5784531, 36.4347496, 50.7921715, 0.00707866857, 2.668971e-08, 0.999974966, -5.85915032e-08, 1, -2.62756199e-08, -0.999974966, -5.84040372e-08, 0.00707866857)
        QuestZ = "Clown Pirate Quest"
    elseif free == "Marine" then
        CFrameQuest = CFrame.new(848.661377, 35.5073013, 1264.83777, -0.998497367, 5.36386899e-08, 0.0548002385, 5.90094018e-08, 1, 9.63871685e-08, -0.0548002385, 9.94760612e-08, -0.998497367)
        QuestZ = "Marine Quest" 
    elseif free == "Monkey" then
        CFrameQuest = CFrame.new(771.192871, 42.3243141, -1220.74805, -0.996942639, 2.59707669e-08, 0.0781369284, 2.55865924e-08, 1, -5.91784355e-09, -0.0781369284, -3.90049282e-09, -0.996942639)
        QuestZ = "Monkey Quest"  
    elseif free == "Monkey King" then
        CFrameQuest = CFrame.new(727.094971, 42.2545357, -1380.22131, -0.0418852083, 2.64795439e-08, 0.999122441, -2.36735005e-08, 1, -2.74952416e-08, -0.999122441, -2.48043701e-08, -0.0418852083)
        QuestZ = "Monkey King Quest"  
    elseif free == "Snow Bandit" then
        CFrameQuest = CFrame.new(1507.57898, 102.05999, -290.12558, -0.998586833, -8.202373e-09, -0.0531440228, -1.01186872e-08, 1, 3.57898209e-08, 0.0531440228, 3.62769903e-08, -0.998586833)
        QuestZ = "Snow Bandit Quest"  
    elseif free == "Bomb Man" or free == "Sand Man" or free == "Snow Bandit Leader" then
        CFrameQuest = nil
        QuestZ = nil
    end
end

function CheckLevel()
    local MyLevel = tonumber(game.Players.LocalPlayer.PlayerGui.MainUI.Interface.PlayerStatus.Frame.Level.TextLabel.Text:match('%d+'))
    
    if MyLevel and (MyLevel == 1 or (MyLevel >= 2 and MyLevel <= 99)) then
        free = "Bandit"
        QuestZ = "Bandit Quest"
    elseif MyLevel and (MyLevel >= 100 and MyLevel <= 149) then
      free = "Bandit Leader"
        QuestZ = "Bandit Leader Quest"
    elseif MyLevel and (MyLevel >= 150 and MyLevel <= 6999) then
        Bo = "Shank"
        QuestZ = "nil"
    end
end

function AA()
    game:GetService('VirtualUser'):CaptureController()
    game:GetService('VirtualUser'):Button1Down(Vector2.new(1280, 672))
end

function A()
    game:GetService('VirtualUser'):CaptureController()
    game:GetService('VirtualUser'):Button1Down(Vector2.new(1280, 672))
end

_G.Farn = true

spawn(function()
    while true do
        wait()
        pcall(function()
            CheckLevel()
            MonA()
            BossA()
            for _, v in pairs(game:GetService("Workspace").Lives:GetChildren()) do
                if v:FindFirstChild("Humanoid") and (v.Humanoid.DisplayName == MONName or v.Humanoid.DisplayName == BossName) and v.Humanoid.Health > 0 then
                    print("Found", v.Name, MONName or BossName)  -- Debugging output

                    v.HumanoidRootPart.Size = Vector3.new(10,10,10)
                    v.HumanoidRootPart.Transparency = 0.9
                    v.Humanoid.WalkSpeed = 0
                    v.Humanoid.JumpPower = 0

                    repeat
                        task.wait()
                        AA()
                        TP(v.HumanoidRootPart.CFrame * CFrame.new(0,5,0) * CFrame.Angles(math.rad(-90),0,0))
                    until not _G.Farn or v.Humanoid.Health <= 0
                end
            end
        end)
    end
end)


spawn(function()
    while true do
        wait()
        pcall(function()
            CheckLevel()
            QuestA()
            if not game.Players.LocalPlayer.PlayerGui:FindFirstChild("QuestUI") then
                repeat
                    task.wait()
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
                until not _G.Farn or game.Players.LocalPlayer.PlayerGui:FindFirstChild("QuestUI")
            end
        end)
    end
end)

for _, v in ipairs(workspace.Lives:GetChildren()) do
    if not game:GetService("Players"):GetPlayerFromCharacter(v) then
        local cleanedName = string.gsub(v.Name, "%d+$", "")
        v.Name = tostring(cleanedName)
    end
end

workspace.Lives.ChildAdded:Connect(function(model)
    task.wait()
    if not game:GetService("Players"):GetPlayerFromCharacter(model) then
        local cleanedName = string.gsub(model.Name, "%d+$", "")
        model.Name = cleanedName
    end
end)

spawn(function()
    while _G.Farn do
        wait()
        pcall(function()
            for _, v in pairs(game:GetService("Workspace"):GetDescendants()) do
                if v.Name == "ProximityPrompt" then
                    fireproximityprompt(v, 30)
                end
            end
        end)
    end
end)

-------------------------------Katana-------------------------------

_G.Katana = true

spawn(function()
while wait() do
pcall(function()
if _G.Katana then
local beli = tonumber(game.Players.LocalPlayer.PlayerGui.MainUI.Interface.PlayerStatus.Frame.Beli.TextLabel.Text) 
local Katana = game.Players.LocalPlayer.PlayerGui.MainUI.Interface.Inventory.WeaponFrame:FindFirstChild("Katana") then
if beli == 2500 and not Katana then
    _G.Farn = false 

    for i, v in pairs(game:GetService("Workspace").Shop.Katana:GetChildren()) do
        if v.ClassName == "ProximityPrompt" then
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
            wait()
            fireproximityprompt(v, 30)
        end
    end

 else
    _G.Farn = true 

                                end
                        end
                end)
        end
end)

-------------------------------Yoru-------------------------------

_G.Yoru = true

spanw(function()
while wait() do
pacall(function()
if _G.Yoru then
local beli = tonumber(game.Players.LocalPlayer.PlayerGui.MainUI.Interface.PlayerStatus.Frame.Beli.TextLabel.Text)
local Katana = game.Players.LocalPlayer.PlayerGui.MainUI.Interface.Inventory.WeaponFrame:FindFirstChild("Yoru") then
if bell == 5000000 and not Yoru then
_G.Farn = false
    for i, v in pairs(game:GetService("Workspace").Shop.Yoru:GetChildren()) do
        if v.ClassName == "ProximityPrompt" then
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
            wait()
            fireproximityprompt(v, 30)
        end
    end

 else
    _G.Farn = true 

                                end
                        end
                end)
        end
end)


_G.M = true

spawn(function()
while wait(.1) do
    pcall(function()
if _G.M then
local args = {
    [1] = "Melee",
    [2] = 1
}

game:GetService("ReplicatedStorage").Remotes.UpStats:FireServer(unpack(args))

                end
        end)
   end
end)

_G.Eq = true

spawn(function()
    while true do
        wait()
        if _G.Eq then
            pcall(function()
                for _, v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                    if v.Name == "Combat" then
                        game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
                    end
                end
            end)
        end
    end
end)

