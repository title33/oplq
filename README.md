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
    elseif free == "Bomb Man" or free == "Sand Man" or free == "Snow Bandit Leader" then
        CFrameQuest = nil
        QuestZ = nil
    end
end

function CheckLevel()
    local MyLevel = tonumber(game.Players.LocalPlayer.PlayerGui.MainUI.Interface.PlayerStatus.Frame.Level.TextLabel.Text:match('%d+'))
    
    if MyLevel and (MyLevel == 1 or (MyLevel >= 2 and MyLevel <= 14)) then
        free = "Bandit"
        QuestZ = "Bandit Quest"
    elseif MyLevel and (MyLevel >= 15 and MyLevel <= 49) then
        free = "Bandit Leader"
        QuestZ = "Bandit Leader Quest"
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
            for _,v in pairs(game:GetService("Workspace").Lives:GetChildren()) do
                if v.Humanoid.DisplayName == MONName and v.Humanoid.Health > 0 then
                    v.HumanoidRootPart.Size = Vector3.new(10,10,10)
                    v.HumanoidRootPart.Transparency = 0.9
                    v.Humanoid.WalkSpeed = 0
                    v.Humanoid.JumpPower = 0
                    repeat task.wait()
                        AA()
                        TP(v.HumanoidRootPart.CFrame*CFrame.new(0,5,0)*CFrame.Angles(math.rad(-90),0,0))
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
                repeat task.wait()
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
                until not _G.Farn or game.Players.LocalPlayer.PlayerGui:FindFirstChild("QuestUI")
            end
        end)
    end
end)

for i, v in ipairs(workspace.Lives:GetChildren()) do
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
            for i, v in pairs(game:GetService("Workspace"):GetDescendants()) do
                if v.Name == "ProximityPrompt" then
                    fireproximityprompt(v, 30)
                end
            end
        end)
    end
end)

