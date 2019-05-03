a = 10

if a == 10 then
  print("Made by bartiirob")
end

local Player = game.Players.LocalPlayer
local Mouse = Player.GetMouse()
local RemoteEvent = game.Workspace.Fired
local UIS = game:GetService("UserInputService")

local Debounce = false

UIS.InputBegan:Connect(Function(input)
    if Input.KeyCode == Enum.KeyCode.R then
        if Debounce == true then return end
        RemoveEvent:FireServer(Debounce)
    end
end)




game.Workspace.Fired.OnServerEvent:Connect(function(Player, Debounce)
    Debounce = true
    local Character = Player.Character or Player.CharacterAdded:wait()
    local Fireball = Instance.new("Part")
    Fireball.Name = "Fireball"
    Fireball.Shape = Enum.PartType.Ball
    Fireball.Size = Vector3.new(2,2,2)
    Fireball.Material = Enum.Material.Neon
    Fireball.BrickColor = BrickCollor.new("Deep orange")
    Fireball.Cancollide = false
    Fireball.Parent = Character
    Fireball.CFrame = Character.HumanoidRootPart.CFrame*CFrame.new(0,1,-6)
    local BV = Instance.new("BodyVelocity")
    BV.MaxForce = Vector3.new(math.huge,math.huge)
    BV.Velocity = Character.HumanoidRootPart.CFrame.lookVector*100
    BV.Parent = Fireball
    Fireball:Destroy()
        local Humanoid = Hit.Parent.FindFirstChild("Humanoid")
        
        if Humanoid == nil then return end
        
        if AlreadyTouched == false then
            AlreadyTouched  = true
            if Humanoid.Parent ==  Character then
                Humanoid.Health = Humanoid.Health - 0
           else
                Humanoid.Health = Humanoid.Health = Humanoid.MaxHealth/4
    Fireball.Touched:Connect(function(Hit)
    wait(2)
    Debounce = false
end)
