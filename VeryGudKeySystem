--// Roblox Key System

--// Exact encoded key
local function decodeKey(hex)
    return (hex:gsub("%x%x", function(byte)
        return string.char(tonumber(byte, 16))
    end))
end

local VALID_KEY = decodeKey(
    "4B45595F3537663438343563343237323837306365306461653336333466376437636431"
)

local KEY_FILE = "JustSbs_Key.txt"

local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")

local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

--// Check for previously saved key
local savedKey = nil

if readfile and isfile and isfile(KEY_FILE) then
    savedKey = readfile(KEY_FILE)
end

--// Remove old UI
local oldGui = playerGui:FindFirstChild("KeySystem")

if oldGui then
    oldGui:Destroy()
end

--// ScreenGui
local gui = Instance.new("ScreenGui")
gui.Name = "KeySystem"
gui.ResetOnSpawn = false
gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
gui.Parent = playerGui

--// Main frame
local main = Instance.new("Frame")
main.Size = UDim2.new(0, 400, 0, 240)
main.Position = UDim2.new(0.5, -200, 0.5, -120)
main.BackgroundColor3 = Color3.fromRGB(20, 20, 25)
main.BorderSizePixel = 0
main.Parent = gui

local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 12)
corner.Parent = main

--// Title
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, -60, 0, 45)
title.Position = UDim2.new(0, 20, 0, 10)
title.BackgroundTransparency = 1
title.Text = "🔐 Key System"
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.TextSize = 24
title.Font = Enum.Font.GothamBold
title.TextXAlignment = Enum.TextXAlignment.Left
title.Parent = main

--// Close button
local close = Instance.new("TextButton")
close.Size = UDim2.new(0, 32, 0, 32)
close.Position = UDim2.new(1, -42, 0, 12)
close.BackgroundColor3 = Color3.fromRGB(35, 35, 42)
close.BorderSizePixel = 0
close.Text = "×"
close.TextColor3 = Color3.fromRGB(255, 100, 100)
close.TextSize = 22
close.Font = Enum.Font.GothamBold
close.Parent = main

local closeCorner = Instance.new("UICorner")
closeCorner.CornerRadius = UDim.new(0, 8)
closeCorner.Parent = close

close.MouseButton1Click:Connect(function()
    gui:Destroy()
end)

--// Description
local description = Instance.new("TextLabel")
description.Size = UDim2.new(1, -40, 0, 35)
description.Position = UDim2.new(0, 20, 0, 55)
description.BackgroundTransparency = 1
description.Text = "Enter your key below to continue."
description.TextColor3 = Color3.fromRGB(170, 170, 180)
description.TextSize = 14
description.Font = Enum.Font.Gotham
description.TextXAlignment = Enum.TextXAlignment.Left
description.Parent = main

--// Key textbox
local keyBox = Instance.new("TextBox")
keyBox.Size = UDim2.new(1, -40, 0, 45)
keyBox.Position = UDim2.new(0, 20, 0, 100)
keyBox.BackgroundColor3 = Color3.fromRGB(30, 30, 38)
keyBox.BorderSizePixel = 0
keyBox.PlaceholderText = "Enter key..."
keyBox.PlaceholderColor3 = Color3.fromRGB(100, 100, 110)
keyBox.Text = ""
keyBox.TextColor3 = Color3.fromRGB(255, 255, 255)
keyBox.TextSize = 15
keyBox.Font = Enum.Font.Gotham
keyBox.ClearTextOnFocus = false
keyBox.Parent = main

local boxCorner = Instance.new("UICorner")
boxCorner.CornerRadius = UDim.new(0, 8)
boxCorner.Parent = keyBox

local padding = Instance.new("UIPadding")
padding.PaddingLeft = UDim.new(0, 12)
padding.PaddingRight = UDim.new(0, 12)
padding.Parent = keyBox

--// Button container
local buttonFrame = Instance.new("Frame")
buttonFrame.Size = UDim2.new(1, -40, 0, 42)
buttonFrame.Position = UDim2.new(0, 20, 0, 155)
buttonFrame.BackgroundTransparency = 1
buttonFrame.Parent = main

--// Redeem button
local redeem = Instance.new("TextButton")
redeem.Size = UDim2.new(0.58, -5, 1, 0)
redeem.Position = UDim2.new(0, 0, 0, 0)
redeem.BackgroundColor3 = Color3.fromRGB(70, 120, 255)
redeem.BorderSizePixel = 0
redeem.Text = "Redeem Key"
redeem.TextColor3 = Color3.fromRGB(255, 255, 255)
redeem.TextSize = 15
redeem.Font = Enum.Font.GothamBold
redeem.Parent = buttonFrame

local redeemCorner = Instance.new("UICorner")
redeemCorner.CornerRadius = UDim.new(0, 8)
redeemCorner.Parent = redeem

--// Get Key button
local getKey = Instance.new("TextButton")
getKey.Size = UDim2.new(0.42, -5, 1, 0)
getKey.Position = UDim2.new(0.58, 5, 0, 0)
getKey.BackgroundColor3 = Color3.fromRGB(40, 40, 50)
getKey.BorderSizePixel = 0
getKey.Text = "Get Key"
getKey.TextColor3 = Color3.fromRGB(255, 255, 255)
getKey.TextSize = 14
getKey.Font = Enum.Font.GothamBold
getKey.TextWrapped = true
getKey.Parent = buttonFrame

local getKeyCorner = Instance.new("UICorner")
getKeyCorner.CornerRadius = UDim.new(0, 8)
getKeyCorner.Parent = getKey

--// Status
local status = Instance.new("TextLabel")
status.Size = UDim2.new(1, -40, 0, 25)
status.Position = UDim2.new(0, 20, 1, -32)
status.BackgroundTransparency = 1
status.Text = ""
status.TextSize = 13
status.Font = Enum.Font.Gotham
status.TextXAlignment = Enum.TextXAlignment.Left
status.Parent = main

--// Get Key
getKey.MouseButton1Click:Connect(function()

    if setclipboard then
        setclipboard("@justsbsxd")
    elseif toclipboard then
        toclipboard("@justsbsxd")
    end

    getKey.Text = "DM @justsbsxd on Discord"
    getKey.TextSize = 11

    status.Text = "✓ Discord username copied!"
    status.TextColor3 = Color3.fromRGB(100, 255, 140)
end)

--// Saved key handling
if savedKey == VALID_KEY then

    keyBox.Text = "Key already saved"
    keyBox.TextEditable = false

    redeem.Visible = false
    getKey.Visible = false

    status.Text = "Loading script..."
    status.TextColor3 = Color3.fromRGB(100, 255, 140)

    task.wait(2)

    gui:Destroy()

    loadstring(game:HttpGet(
        "https://raw.githubusercontent.com/JustSbs/VeryGudScript/refs/heads/main/VeryGudScript.lua"
    ))()

    return
end

--// Redeem function
local function redeemKey()

    local entered = keyBox.Text

    if entered == "" then

        status.Text = "Please enter a key."
        status.TextColor3 = Color3.fromRGB(255, 180, 80)

        return
    end

    if entered == VALID_KEY then

        --// Save key in Workspace
        local workspaceKey = workspace:FindFirstChild("JustSbs_Key")

        if not workspaceKey then
            workspaceKey = Instance.new("StringValue")
            workspaceKey.Name = "JustSbs_Key"
            workspaceKey.Parent = workspace
        end

        workspaceKey.Value = entered

        --// Save between executions
        if writefile then
            writefile(KEY_FILE, entered)
        end

        status.Text = "✓ Key successfully redeemed!"
        status.TextColor3 = Color3.fromRGB(100, 255, 140)

        task.wait(0.8)

        gui:Destroy()

        --// Execute main script
        loadstring(game:HttpGet(
            "https://raw.githubusercontent.com/JustSbs/VeryGudScript/refs/heads/main/VeryGudScript.lua"
        ))()

    else

        status.Text = "✕ Invalid key."
        status.TextColor3 = Color3.fromRGB(255, 90, 90)

    end
end

--// Redeem button
redeem.MouseButton1Click:Connect(redeemKey)

--// Enter to redeem
keyBox.FocusLost:Connect(function(enterPressed)

    if enterPressed then
        redeemKey()
    end

end)

--// Draggable GUI
local dragging = false
local dragStart
local startPos

main.InputBegan:Connect(function(input)

    if input.UserInputType == Enum.UserInputType.MouseButton1 then

        dragging = true
        dragStart = input.Position
        startPos = main.Position

        input.Changed:Connect(function()

            if input.UserInputState == Enum.UserInputState.End then
                dragging = false
            end

        end)

    end

end)

UserInputService.InputChanged:Connect(function(input)

    if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then

        local delta = input.Position - dragStart

        main.Position = UDim2.new(
            startPos.X.Scale,
            startPos.X.Offset + delta.X,
            startPos.Y.Scale,
            startPos.Y.Offset + delta.Y
        )

    end

end)
