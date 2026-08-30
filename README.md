--[[
    NTK HUB (TSB fram kill)
    Main Script - Selection Menu
    Author: NTK HUB
]]

-- Services
local CoreGui = game:GetService("CoreGui")
local TweenService = game:GetService("TweenService")
local UserInputService = game:GetService("UserInputService")
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

-- Remove existing GUI if already present
local existing = CoreGui:FindFirstChild("NTKHubMain")
if existing then
    existing:Destroy()
end

-- Create ScreenGui
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "NTKHubMain"
ScreenGui.ResetOnSpawn = false
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.Parent = CoreGui

-- ===== Main Frame =====
local MainFrame = Instance.new("Frame")
MainFrame.Name = "MainFrame"
MainFrame.Size = UDim2.new(0, 420, 0, 300)
MainFrame.Position = UDim2.new(0.5, -210, 0.5, -150)
MainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 30)
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.Parent = ScreenGui

-- Rounded corners
local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 12)
corner.Parent = MainFrame

-- Stroke
local stroke = Instance.new("UIStroke")
stroke.Color = Color3.fromRGB(120, 80, 200)
stroke.Thickness = 2
stroke.Parent = MainFrame

-- Gradient background
local gradient = Instance.new("UIGradient")
gradient.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(25, 20, 45)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(15, 15, 25))
})
gradient.Rotation = 90
gradient.Parent = MainFrame

-- ===== Title =====
local TitleLabel = Instance.new("TextLabel")
TitleLabel.Name = "Title"
TitleLabel.Size = UDim2.new(1, 0, 0, 55)
TitleLabel.Position = UDim2.new(0, 0, 0, 0)
TitleLabel.BackgroundTransparency = 1
TitleLabel.Text = "NTK HUB"
TitleLabel.TextColor3 = Color3.fromRGB(180, 140, 255)
TitleLabel.Font = Enum.Font.GothamBold
TitleLabel.TextSize = 28
TitleLabel.Parent = MainFrame

local SubtitleLabel = Instance.new("TextLabel")
SubtitleLabel.Name = "Subtitle"
SubtitleLabel.Size = UDim2.new(1, 0, 0, 20)
SubtitleLabel.Position = UDim2.new(0, 0, 0, 45)
SubtitleLabel.BackgroundTransparency = 1
SubtitleLabel.Text = "(TSB fram kill)"
SubtitleLabel.TextColor3 = Color3.fromRGB(140, 140, 160)
SubtitleLabel.Font = Enum.Font.Gotham
SubtitleLabel.TextSize = 14
SubtitleLabel.Parent = MainFrame

-- Divider line
local Divider = Instance.new("Frame")
Divider.Size = UDim2.new(0.9, 0, 0, 1)
Divider.Position = UDim2.new(0.05, 0, 0, 72)
Divider.BackgroundColor3 = Color3.fromRGB(120, 80, 200)
Divider.BackgroundTransparency = 0.5
Divider.BorderSizePixel = 0
Divider.Parent = MainFrame

-- ===== V1 Button =====
local V1Button = Instance.new("TextButton")
V1Button.Name = "V1Button"
V1Button.Size = UDim2.new(0.85, 0, 0, 60)
V1Button.Position = UDim2.new(0.075, 0, 0, 95)
V1Button.BackgroundColor3 = Color3.fromRGB(40, 35, 70)
V1Button.BorderSizePixel = 0
V1Button.Text = ""
V1Button.Parent = MainFrame

local v1Corner = Instance.new("UICorner")
v1Corner.CornerRadius = UDim.new(0, 10)
v1Corner.Parent = V1Button

local v1Stroke = Instance.new("UIStroke")
v1Stroke.Color = Color3.fromRGB(100, 70, 180)
v1Stroke.Thickness = 1.5
v1Stroke.Parent = V1Button

local v1Title = Instance.new("TextLabel")
v1Title.Size = UDim2.new(1, -20, 0, 25)
v1Title.Position = UDim2.new(0, 15, 0, 8)
v1Title.BackgroundTransparency = 1
v1Title.Text = "V1 - NTK Hub"
v1Title.TextColor3 = Color3.fromRGB(255, 255, 255)
v1Title.Font = Enum.Font.GothamBold
v1Title.TextSize = 18
v1Title.TextXAlignment = Enum.TextXAlignment.Left
v1Title.Parent = V1Button

local v1Desc = Instance.new("TextLabel")
v1Desc.Size = UDim2.new(1, -20, 0, 18)
v1Desc.Position = UDim2.new(0, 15, 0, 35)
v1Desc.BackgroundTransparency = 1
v1Desc.Text = "fram kill (github script)"
v1Desc.TextColor3 = Color3.fromRGB(160, 160, 180)
v1Desc.Font = Enum.Font.Gotham
v1Desc.TextSize = 12
v1Desc.TextXAlignment = Enum.TextXAlignment.Left
v1Desc.Parent = V1Button

-- ===== V2 Button =====
local V2Button = Instance.new("TextButton")
V2Button.Name = "V2Button"
V2Button.Size = UDim2.new(0.85, 0, 0, 60)
V2Button.Position = UDim2.new(0.075, 0, 0, 170)
V2Button.BackgroundColor3 = Color3.fromRGB(40, 35, 70)
V2Button.BorderSizePixel = 0
V2Button.Text = ""
V2Button.Parent = MainFrame

local v2Corner = Instance.new("UICorner")
v2Corner.CornerRadius = UDim.new(0, 10)
v2Corner.Parent = V2Button

local v2Stroke = Instance.new("UIStroke")
v2Stroke.Color = Color3.fromRGB(100, 70, 180)
v2Stroke.Thickness = 1.5
v2Stroke.Parent = V2Button

local v2Title = Instance.new("TextLabel")
v2Title.Size = UDim2.new(1, -20, 0, 25)
v2Title.Position = UDim2.new(0, 15, 0, 8)
v2Title.BackgroundTransparency = 1
v2Title.Text = "V2 -ProjectYielding"
v2Title.TextColor3 = Color3.fromRGB(255, 255, 255)
v2Title.Font = Enum.Font.GothamBold
v2Title.TextSize = 18
v2Title.TextXAlignment = Enum.TextXAlignment.Left
v2Title.Parent = V2Button

local v2Desc = Instance.new("TextLabel")
v2Desc.Size = UDim2.new(1, -20, 0, 18)
v2Desc.Position = UDim2.new(0, 15, 0, 35)
v2Desc.BackgroundTransparency = 1
v2Desc.Text = "fram kill (gitlab script)"
v2Desc.TextColor3 = Color3.fromRGB(160, 160, 180)
v2Desc.Font = Enum.Font.Gotham
v2Desc.TextSize = 12
v2Desc.TextXAlignment = Enum.TextXAlignment.Left
v2Desc.Parent = V2Button

-- ===== Close Button =====
local CloseButton = Instance.new("TextButton")
CloseButton.Name = "CloseButton"
CloseButton.Size = UDim2.new(0, 30, 0, 30)
CloseButton.Position = UDim2.new(1, -38, 0, 12)
CloseButton.BackgroundColor3 = Color3.fromRGB(200, 50, 50)
CloseButton.BorderSizePixel = 0
CloseButton.Text = "X"
CloseButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseButton.Font = Enum.Font.GothamBold
CloseButton.TextSize = 16
CloseButton.Parent = MainFrame

local closeCorner = Instance.new("UICorner")
closeCorner.CornerRadius = UDim.new(0, 8)
closeCorner.Parent = CloseButton

-- ===== Footer =====
local Footer = Instance.new("TextLabel")
Footer.Size = UDim2.new(1, 0, 0, 18)
Footer.Position = UDim2.new(0, 0, 1, -22)
Footer.BackgroundTransparency = 1
Footer.Text = "NTK HUB"
Footer.TextColor3 = Color3.fromRGB(90, 90, 110)
Footer.Font = Enum.Font.Gotham
Footer.TextSize = 11
Footer.Parent = MainFrame

-- ===== Hover Effects =====
local function addHoverEffect(button, defaultColor)
    button.MouseEnter:Connect(function()
        TweenService:Create(button, TweenInfo.new(0.15), {
            BackgroundColor3 = Color3.fromRGB(70, 55, 120)
        }):Play()
    end)
    button.MouseLeave:Connect(function()
        TweenService:Create(button, TweenInfo.new(0.15), {
            BackgroundColor3 = defaultColor
        }):Play()
    end)
end

addHoverEffect(V1Button, Color3.fromRGB(40, 35, 70))
addHoverEffect(V2Button, Color3.fromRGB(40, 35, 70))

CloseButton.MouseEnter:Connect(function()
    TweenService:Create(CloseButton, TweenInfo.new(0.15), {
        BackgroundColor3 = Color3.fromRGB(230, 70, 70)
    }):Play()
end)
CloseButton.MouseLeave:Connect(function()
    TweenService:Create(CloseButton, TweenInfo.new(0.15), {
        BackgroundColor3 = Color3.fromRGB(200, 50, 50)
    }):Play()
end)

-- ===== Dragging =====
local dragging = false
local dragInput
local dragStart
local startPos

MainFrame.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
        dragging = true
        dragStart = input.Position
        startPos = MainFrame.Position
        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                dragging = false
            end
        end)
    end
end)

MainFrame.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
        dragInput = input
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if input == dragInput and dragging then
        local delta = input.Position - dragStart
        MainFrame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
    end
end)

-- ===== Script Loader Functions =====

-- Fade out main frame
local function fadeOutAndDestroy(callback)
    local tween = TweenService:Create(MainFrame, TweenInfo.new(0.3), {
        BackgroundTransparency = 1
    })
    
    -- Fade all children too
    for _, child in ipairs(MainFrame:GetDescendants()) do
        if child:IsA("TextLabel") or child:IsA("TextButton") then
            TweenService:Create(child, TweenInfo.new(0.3), {
                TextTransparency = 1,
                BackgroundTransparency = child:IsA("TextButton") and 1 or child.BackgroundTransparency
            }):Play()
        elseif child:IsA("UIStroke") then
            TweenService:Create(child, TweenInfo.new(0.3), {
                Transparency = 1
            }):Play()
        end
    end
    
    tween:Play()
    tween.Completed:Connect(function()
        ScreenGui:Destroy()
        if callback then
            callback()
        end
    end)
end

-- Load V1 Script
local function loadV1()
    fadeOutAndDestroy(function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/kietkidlo-hub/script-fram-kill-tsb/refs/heads/main/README.md"))()
    end)
end

-- Load V2 Script
local function loadV2()
    fadeOutAndDestroy(function()
        loadstring(game:HttpGet("https://gitlab.com/zkay404-group/ProjectYielding/-/raw/main/ZKPublicFarm"))()
    end)
end

-- ===== Button Connections =====
V1Button.MouseButton1Click:Connect(loadV1)
V2Button.MouseButton1Click:Connect(loadV2)
CloseButton.MouseButton1Click:Connect(function()
    fadeOutAndDestroy()
end)

-- ===== Open Animation =====
MainFrame.Size = UDim2.new(0, 420, 0, 0)
MainFrame.Position = UDim2.new(0.5, -210, 0.5, 0)
TweenService:Create(MainFrame, TweenInfo.new(0.4, Enum.EasingStyle.Back, Enum.EasingDirection.Out), {
    Size = UDim2.new(0, 420, 0, 300),
    Position = UDim2.new(0.5, -210, 0.5, -150)
}):Play()

print("[NTK HUB] Main script loaded - Select V1 or V2")
