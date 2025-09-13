local player = game.Players.LocalPlayer
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "PlayerTeleportGUI"
screenGui.Parent = player.PlayerGui


local COLORS = {
    BACKGROUND = Color3.new(0.15, 0.15, 0.15),
    SECONDARY = Color3.new(0.2, 0.2, 0.2),
    ACCENT = Color3.new(0.3, 0.7, 1),
    SUCCESS = Color3.new(0.2, 0.8, 0.4),
    DANGER = Color3.new(0.9, 0.3, 0.3),
    TEXT = Color3.new(1, 1, 1),
    TEXT_DARK = Color3.new(0.1, 0.1, 0.1)
}


local frame = Instance.new("Frame")
frame.Name = "MainFrame"
frame.Size = UDim2.new(0, 320, 0, 200)
frame.Position = UDim2.new(0.5, -160, 0.5, -100)
frame.BackgroundColor3 = COLORS.BACKGROUND
frame.BorderSizePixel = 0
frame.Parent = screenGui


local frameCorner = Instance.new("UICorner")
frameCorner.CornerRadius = UDim.new(0, 12)
frameCorner.Parent = frame


local frameGradient = Instance.new("UIGradient")
frameGradient.Color = ColorSequence.new{
    ColorSequenceKeypoint.new(0, Color3.new(0.2, 0.2, 0.25)),
    ColorSequenceKeypoint.new(1, Color3.new(0.15, 0.15, 0.15))
}
frameGradient.Rotation = 45
frameGradient.Parent = frame


local frameStroke = Instance.new("UIStroke")
frameStroke.Color = Color3.new(0.4, 0.4, 0.4)
frameStroke.Thickness = 1
frameStroke.Parent = frame


local titleLabel = Instance.new("TextLabel")
titleLabel.Name = "TitleLabel"
titleLabel.Size = UDim2.new(1, -60, 0, 45)
titleLabel.Position = UDim2.new(0, 0, 0, 0)
titleLabel.Text = "TP MENU (เมนูเทเลพอร์ต)"
titleLabel.TextColor3 = COLORS.TEXT
titleLabel.BackgroundColor3 = COLORS.SECONDARY
titleLabel.BorderSizePixel = 0
titleLabel.TextScaled = true
titleLabel.Font = Enum.Font.GothamBold
titleLabel.Parent = frame


local titleCorner = Instance.new("UICorner")
titleCorner.CornerRadius = UDim.new(0, 8)
titleCorner.Parent = titleLabel


local titleGradient = Instance.new("UIGradient")
titleGradient.Color = ColorSequence.new{
    ColorSequenceKeypoint.new(0, COLORS.ACCENT),
    ColorSequenceKeypoint.new(1, Color3.new(0.2, 0.5, 0.8))
}
titleGradient.Rotation = 90
titleGradient.Parent = titleLabel


local closeButton = Instance.new("TextButton")
closeButton.Name = "CloseButton"
closeButton.Size = UDim2.new(0, 40, 0, 40)
closeButton.Position = UDim2.new(1, -45, 0, 2.5)
closeButton.Text = "✕ ปิด"
closeButton.TextColor3 = COLORS.TEXT
closeButton.BackgroundColor3 = COLORS.DANGER
closeButton.BorderSizePixel = 0
closeButton.TextScaled = true
closeButton.Font = Enum.Font.GothamBold
closeButton.Parent = frame

local closeCorner = Instance.new("UICorner")
closeCorner.CornerRadius = UDim.new(0, 8)
closeCorner.Parent = closeButton


local hideButton = Instance.new("TextButton")
hideButton.Name = "HideButton"
hideButton.Size = UDim2.new(0, 50, 0, 50)
hideButton.Position = UDim2.new(0, 10, 0, 10)
hideButton.Text = "👁 ซ่อน/แสดง"
hideButton.TextColor3 = COLORS.TEXT
hideButton.BackgroundColor3 = COLORS.SECONDARY
hideButton.BorderSizePixel = 0
hideButton.TextScaled = true
hideButton.Font = Enum.Font.Gotham
hideButton.Parent = screenGui

local hideCorner = Instance.new("UICorner")
hideCorner.CornerRadius = UDim.new(1, 0)
hideCorner.Parent = hideButton

local hideStroke = Instance.new("UIStroke")
hideStroke.Color = COLORS.ACCENT
hideStroke.Thickness = 2
hideStroke.Parent = hideButton


local dropdownButton = Instance.new("TextButton")
dropdownButton.Name = "DropdownButton"
dropdownButton.Size = UDim2.new(1, -20, 0, 35)
dropdownButton.Position = UDim2.new(0, 10, 0, 55)
dropdownButton.Text = "📋 เลือกผู้เล่น (Select Player)"
dropdownButton.TextColor3 = COLORS.TEXT_DARK
dropdownButton.BackgroundColor3 = Color3.new(0.9, 0.9, 0.9)
dropdownButton.BorderSizePixel = 0
dropdownButton.TextScaled = true
dropdownButton.Font = Enum.Font.Gotham
dropdownButton.Parent = frame

local dropdownCorner = Instance.new("UICorner")
dropdownCorner.CornerRadius = UDim.new(0, 6)
dropdownCorner.Parent = dropdownButton


local followButton = Instance.new("TextButton")
followButton.Name = "FollowButton"
followButton.Size = UDim2.new(0, 140, 0, 40)
followButton.Text = "🔗 ติดตาม (Follow)"
followButton.TextColor3 = COLORS.TEXT
followButton.BackgroundColor3 = COLORS.SUCCESS
followButton.BorderSizePixel = 0
followButton.TextScaled = true
followButton.Font = Enum.Font.GothamSemibold
followButton.Parent = buttonContainer


local teleportButton = Instance.new("TextButton")
teleportButton.Name = "TeleportButton"
teleportButton.Size = UDim2.new(0, 140, 0, 40)
teleportButton.Text = "⚡ เทเลพอร์ต (Teleport)"
teleportButton.TextColor3 = COLORS.TEXT
teleportButton.BackgroundColor3 = COLORS.ACCENT
teleportButton.BorderSizePixel = 0
teleportButton.TextScaled = true
teleportButton.Font = Enum.Font.GothamSemibold
teleportButton.Parent = buttonContainer


local confirmQuestion = Instance.new("TextLabel")
confirmQuestion.Name = "ConfirmQuestion"
confirmQuestion.Size = UDim2.new(1, -20, 0, 40)
confirmQuestion.Position = UDim2.new(0, 10, 0, 50)
confirmQuestion.Text = "ปิดสคริปต์? (Close script?)"
confirmQuestion.TextColor3 = COLORS.TEXT
confirmQuestion.BackgroundTransparency = 1
confirmQuestion.TextScaled = true
confirmQuestion.Font = Enum.Font.Gotham
confirmQuestion.Parent = confirmDialog


yesButton.Text = "✔ ใช่ (Yes)"
noButton.Text = "✕ ไม่ (No)"
