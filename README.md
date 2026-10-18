# Enzo-hub-- Logo "Enzo Hub" — LocalScript em StarterPlayer > StarterPlayerScripts
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local PlayerGui = LocalPlayer:WaitForChild("PlayerGui")

local gui = Instance.new("ScreenGui")
gui.Name = "EnzoHubLogo"
gui.ResetOnSpawn = false
gui.IgnoreGuiInset = true
gui.Parent = PlayerGui

-- Container circular
local logo = Instance.new("Frame")
logo.Size = UDim2.fromOffset(120, 120)
logo.Position = UDim2.new(0, 20, 0, 20)
logo.BackgroundColor3 = Color3.fromRGB(20, 20, 35)
logo.BorderSizePixel = 0
logo.Parent = gui

local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(1, 0)
corner.Parent = logo

-- Gradiente interno
local grad = Instance.new("UIGradient")
grad.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(0, 200, 255)),
    ColorSequenceKeypoint.new(0.5, Color3.fromRGB(140, 0, 255)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(255, 0, 120)),
})
grad.Rotation = 45
grad.Parent = logo

-- Anel de brilho externo
local ring = Instance.new("UIStroke")
ring.Thickness = 3
ring.Color = Color3.fromRGB(0, 220, 255)
ring.Transparency = 0.2
ring.Parent = logo

-- Sombra/glow (Frame maior atrás, semi-transparente)
local glow = Instance.new("Frame")
glow.Size = UDim2.fromOffset(140, 140)
glow.Position = UDim2.new(0.5, 0, 0.5, 0)
glow.AnchorPoint = Vector2.new(0.5, 0.5)
glow.BackgroundColor3 = Color3.fromRGB(0, 200, 255)
glow.BackgroundTransparency = 0.75
glow.BorderSizePixel = 0
glow.ZIndex = -1
glow.Parent = logo

local glowCorner = Instance.new("UICorner")
glowCorner.CornerRadius = UDim.new(1, 0)
glowCorner.Parent = glow

-- Texto "EH" estilizado
local txt = Instance.new("TextLabel")
txt.Size = UDim2.fromScale(1, 1)
txt.BackgroundTransparency = 1
txt.Text = "EH"
txt.TextColor3 = Color3.new(1, 1, 1)
txt.Font = Enum.Font.GothamBlack
txt.TextScaled = true
txt.Parent = logo

-- Padding pro texto não encostar na borda
local pad = Instance.new("UIPadding")
pad.PaddingTop = UDim.new(0.25, 0)
pad.PaddingBottom = UDim.new(0.25, 0)
pad.PaddingLeft = UDim.new(0.25, 0)
pad.PaddingRight = UDim.new(0.25, 0)
pad.Parent = txt

-- Subtítulo "ENZO HUB"
local sub = Instance.new("TextLabel")
sub.Size = UDim2.new(1, 0, 0, 18)
sub.Position = UDim2.new(0, 0, 1, 6)
sub.BackgroundTransparency = 1
sub.Text = "ENZO HUB"
sub.TextColor3 = Color3.fromRGB(0, 220, 255)
sub.Font = Enum.Font.GothamBold
sub.TextScaled = true
sub.Parent = logo
