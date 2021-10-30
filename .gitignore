--Leak By HxrTJL     
function loadcheck()
   if isfile("SaveSettingJPEX.json") then
       else
           writefile("SaveSettingJPEX.json",game:GetService("HttpService"):JSONEncode(_G.Save))
       return
   end
end
_G.Save = {
   ["AutoFarm"] = false,
   ["AutoQuest"] = true,
   ["FastAttk"] = true,
   ["AutoNew"] = false,
   ["AutoNew2"] = false,
   ["AutoCavandit"] = false,
   ["AutoSeber"] = false,
   ["AutoFac"] = false,
   ["AutoSuperhuman"] = false,
   ["AutoElectric"] = false,
   ["AutoDeathStep"] = false,
   ["AutoHakiv2"] = false,
   ["AutoYama"] = false,
   ["AutoPlayerHunter"] = false,
   ["AutoBuyLegen"] = false,
   ["AutoBuyLegenHop"] = false,
   ["AutoEnhan"] = false,
   ["SelctToolFarm"] = "",
   ["AutoCollectFirst"] = false,
   ["AutoAccessories"] = false,
   ["SelctAccessories"] = "",
   ["AutoDevilFruitMastery"] = false,
   ["AutoGunMastery"] = false,
   ["Health"] = "",
   ["SelctToolHun"] = "",
   ["AutoQuestbar"] = false,
   ["SelctToolbar"] = "",
   ["AutoNear"] = false,
   ["DistanceNear"] = "",
   ["SelctToolNear"] = "",
   ["AutoRengoku"] = false,
   ["SelctToolRen"] = "",
   ["AutoSharkman"] = false,
   ["SelctToolShark"] = "",
   ["AutoObservation"] = false,
   ["AutoFramEctoplasm"] = false,
   ["AutoKill"] = false,
   ["SkillZ"] = true,
   ["SkillX"] = true,
   ["SkillC"] = true,
   ["SkillV"] = true,
   ["SelectBeliValue"] = "",
   ["lockBeli"] = false,
   ["Melee"] = false,
   ["Defense"] = false,
   ["Sword"] = false,
   ["Gun"] = false,
   ["demonfruit"] = false,
   ["ESPPlayer"] = false,
   ["ESPChest"] = false,
   ["ESPDevil"] = false,
   ["ESPFlower"] = false,
   ["AutoRaidNotKillMob"] = false,
   ["SelctToolRaid"] = "",
   ["KillAura"] = false,
   ["AutoNextIland"] = false,
   ["Awakener"] = false,
   ["SelectShip"] = "",
   ["AutoBuyShip"] = false,
   ["AutoRaid"] = false,
   ["FastAttkMisc"] = false,
   ["SelectLockLvl"] = "",
   ["locklvl"] = false,
   ["DashnNocool"] = false,
   ["InfinitsEnergy"] = false,
   ["AuctoClick"] = false,
   ["AutoCollectFruit"] = false,
   ["FlySpeed"] = "",
   ["FlyStart"] = false,
   ["Noclip"] = false,
   ["InfRace"] = false,
   ["DevilValue"] = "",
   ["BuyDevil"] = false,
   ["AutoRandomDevil"] = false,
   ["ShowHitbox"] = true,
   ["AUTOHAKI"] = false,
   ["AutoObservationHakib"] = false,
   ["AntiAfk"] = true,
   ["Magnet"] = true,
}
function LoadSetting()
   if isfile("SaveSettingJPEX.json") then
           vb = game:GetService("HttpService"):JSONDecode(readfile("SaveSettingJPEX.json"))
           _G.Save = vb
       else
           loadcheck()
   end
end

function SaveSetting()
   if isfile("SaveSettingJPEX.json") then
           writefile("SaveSettingJPEX.json",game:GetService("HttpService"):JSONEncode(_G.Save))
       else
           loadcheck()
   end
end


loadcheck()
LoadSetting()

local placeId = game.PlaceId
if placeId == 4520749081 then
  OldWorld = true
elseif placeId == 6381829480 then
  newworld = true
elseif placeId == 5931540094 then
  Raid = true
end

if OldWorld or newworld or Raid then
  local Flux = {RainbowColorValue = 0, HueSelectionPosition = 0}
  local PresetColor = Color3.fromRGB(66, 134, 255)
  local UserInputService = game:GetService("UserInputService")
  local TweenService = game:GetService("TweenService")
  local RunService = game:GetService("RunService")
  local LocalPlayer = game:GetService("Players").LocalPlayer
  local Mouse = LocalPlayer:GetMouse()
  local CloseBind = Enum.KeyCode.RightControl
  
  local FluxLib = Instance.new("ScreenGui")
  FluxLib.Name = "FluxLib"
  FluxLib.Parent = game.CoreGui
  FluxLib.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
  
  coroutine.wrap(
     function()
        while wait() do
           Flux.RainbowColorValue = Flux.RainbowColorValue + 1 / 255
           Flux.HueSelectionPosition = Flux.HueSelectionPosition + 1
  
           if Flux.RainbowColorValue >= 1 then
              Flux.RainbowColorValue = 0
           end
  
           if Flux.HueSelectionPosition == 80 then
              Flux.HueSelectionPosition = 0
           end
        end
     end
  )()
  
  local function MakeDraggable(topbarobject, object)
     local Dragging = nil
     local DragInput = nil
     local DragStart = nil
     local StartPosition = nil
  
     local function Update(input)
        local Delta = input.Position - DragStart
        local pos =
              UDim2.new(
              StartPosition.X.Scale,
              StartPosition.X.Offset + Delta.X,
              StartPosition.Y.Scale,
              StartPosition.Y.Offset + Delta.Y
        )
        local Tween = TweenService:Create(object, TweenInfo.new(0.2), {Position = pos})
        Tween:Play()
     end
  
     topbarobject.InputBegan:Connect(
        function(input)
              if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                 Dragging = true
                 DragStart = input.Position
                 StartPosition = object.Position
  
                 input.Changed:Connect(
                    function()
                          if input.UserInputState == Enum.UserInputState.End then
                             Dragging = false
                          end
                    end
                 )
              end
        end
     )
  
     topbarobject.InputChanged:Connect(
        function(input)
              if
                 input.UserInputType == Enum.UserInputType.MouseMovement or
                    input.UserInputType == Enum.UserInputType.Touch
              then
                 DragInput = input
              end
        end
     )
  
     UserInputService.InputChanged:Connect(
        function(input)
              if input == DragInput and Dragging then
                 Update(input)
              end
        end
     )
  end
  
  
  
  function Flux:Window(text, bottom,mainclr,toclose)
     CloseBind = toclose or Enum.KeyCode.RightControl
     PresetColor = mainclr or Color3.fromRGB(255, 35, 45)
     local fs = false
     local MainFrame = Instance.new("Frame")
     local MainCorner = Instance.new("UICorner")
     local LeftFrame = Instance.new("Frame")
     local LeftCorner = Instance.new("UICorner")
     local GlowTabHolder = Instance.new("ImageLabel")
     local Title = Instance.new("TextLabel")
     local BottomText = Instance.new("TextLabel")
     local TabHold = Instance.new("Frame")
     local TabLayout = Instance.new("UIListLayout")
     local Drag = Instance.new("Frame")
     local ContainerFolder = Instance.new("Folder")
  
     MainFrame.Name = "MainFrame"
     MainFrame.Parent = FluxLib
     MainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
     MainFrame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
     MainFrame.ClipsDescendants = true
     MainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
     MainFrame.Size = UDim2.new(0, 0, 0, 0)
  
     MainCorner.CornerRadius = UDim.new(0, 5)
     MainCorner.Name = "MainCorner"
     MainCorner.Parent = MainFrame
  
     LeftFrame.Name = "LeftFrame"
     LeftFrame.Parent = MainFrame
     LeftFrame.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
     LeftFrame.Size = UDim2.new(0, 205, 0, 484)
  
     LeftCorner.CornerRadius = UDim.new(0, 5)
     LeftCorner.Name = "LeftCorner"
     LeftCorner.Parent = LeftFrame
  
     GlowTabHolder.Name = "GlowTabHolder"
     GlowTabHolder.Parent = LeftFrame
     GlowTabHolder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     GlowTabHolder.BackgroundTransparency = 1.000
     GlowTabHolder.BorderSizePixel = 0
     GlowTabHolder.Position = UDim2.new(0, -15, 0, -15)
     GlowTabHolder.Size = UDim2.new(1, 30, 1, 30)
     GlowTabHolder.ZIndex = 0
     GlowTabHolder.Image = "rbxassetid://4996891970"
     GlowTabHolder.ImageColor3 = Color3.fromRGB(15, 15, 15)
     GlowTabHolder.ScaleType = Enum.ScaleType.Slice
     GlowTabHolder.SliceCenter = Rect.new(20, 20, 280, 280)
  
     Title.Name = "Title"
     Title.Parent = LeftFrame
     Title.BackgroundColor3 = Color3.fromRGB(255, 0, 11)
     Title.BackgroundTransparency = 1.000
     Title.Position = UDim2.new(0.097560972, 0, 0.0475206636, 0)
     Title.Size = UDim2.new(0, 111, 0, 34)
     Title.Font = Enum.Font.GothamBold
     Title.Text = text
     Title.TextColor3 = Color3.fromRGB(209, 34, 34  )
     Title.TextSize = 25.000
     Title.TextXAlignment = Enum.TextXAlignment.Left
  
     BottomText.Name = "BottomText"
     BottomText.Parent = LeftFrame
     BottomText.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     BottomText.BackgroundTransparency = 1.000
     BottomText.Position = UDim2.new(0.097560972, 0, 0.0889999792, 0)
     BottomText.Size = UDim2.new(0, 113, 0, 28)
     BottomText.Font = Enum.Font.Gotham
     BottomText.Text = bottom
     BottomText.TextColor3 = Color3.fromRGB(255, 255, 255)
     BottomText.TextSize = 14.000
     BottomText.TextTransparency = 0.300
     BottomText.TextXAlignment = Enum.TextXAlignment.Left
  
     TabHold.Name = "TabHold"
     TabHold.Parent = LeftFrame
     TabHold.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     TabHold.BackgroundTransparency = 1.000
     TabHold.Position = UDim2.new(0, 0, 0.167355374, 0)
     TabHold.Size = UDim2.new(0, 205, 0, 403)
  
     TabLayout.Name = "TabLayout"
     TabLayout.Parent = TabHold
     TabLayout.SortOrder = Enum.SortOrder.LayoutOrder
     TabLayout.Padding = UDim.new(0, 3)
  
     Drag.Name = "Drag"
     Drag.Parent = MainFrame
     Drag.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     Drag.BackgroundTransparency = 1.000
     Drag.Position = UDim2.new(0.290368259, 0, 0, 0)
     Drag.Size = UDim2.new(0, 501, 0, 23)
  
     ContainerFolder.Name = "ContainerFolder"
     ContainerFolder.Parent = MainFrame
     
     MakeDraggable(Drag,MainFrame)
     MakeDraggable(LeftFrame,MainFrame)
     MainFrame:TweenSize(UDim2.new(0, 706, 0, 484), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
     
     local uitoggled = false
     UserInputService.InputBegan:Connect(
        function(io, p)
           if io.KeyCode == CloseBind then
              if uitoggled == false then
                 MainFrame:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 uitoggled = true
                 wait(.5)
                 FluxLib.Enabled = false
              else
                 MainFrame:TweenSize(UDim2.new(0, 706, 0, 484), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 FluxLib.Enabled = true
                 uitoggled = false
              end
           end
        end
     )
     
     function Flux:Notification(desc,buttontitle)
        for i, v in next, MainFrame:GetChildren() do
           if v.Name == "NotificationBase" then
              v:Destroy()
           end
        end
        local NotificationBase = Instance.new("TextButton")
        local NotificationBaseCorner = Instance.new("UICorner")
        local NotificationFrame = Instance.new("Frame")
        local NotificationFrameCorner = Instance.new("UICorner")
        local NotificationFrameGlow = Instance.new("ImageLabel")
        local NotificationTitle = Instance.new("TextLabel")
        local CloseBtn = Instance.new("TextButton")
        local CloseBtnCorner = Instance.new("UICorner")
        local NotificationDesc = Instance.new("TextLabel")
  
        NotificationBase.Name = "NotificationBase"
        NotificationBase.Parent = MainFrame
        NotificationBase.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        NotificationBase.BackgroundTransparency = 1
        NotificationBase.Size = UDim2.new(0, 706, 0, 484)
        NotificationBase.AutoButtonColor = false
        NotificationBase.Font = Enum.Font.SourceSans
        NotificationBase.Text = ""
        NotificationBase.TextColor3 = Color3.fromRGB(0, 0, 0)
        NotificationBase.TextSize = 14.000
        NotificationBase.Visible = true
  
        NotificationBaseCorner.CornerRadius = UDim.new(0, 5)
        NotificationBaseCorner.Name = "NotificationBaseCorner"
        NotificationBaseCorner.Parent = NotificationBase
  
        NotificationFrame.Name = "NotificationFrame"
        NotificationFrame.Parent = NotificationBase
        NotificationFrame.AnchorPoint = Vector2.new(0.5, 0.5)
        NotificationFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        NotificationFrame.ClipsDescendants = true
        NotificationFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
        NotificationFrame.Size = UDim2.new(0, 0, 0, 0)
  
        NotificationFrameCorner.CornerRadius = UDim.new(0, 5)
        NotificationFrameCorner.Name = "NotificationFrameCorner"
        NotificationFrameCorner.Parent = NotificationFrame
  
        NotificationFrameGlow.Name = "NotificationFrameGlow"
        NotificationFrameGlow.Parent = NotificationFrame
        NotificationFrameGlow.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        NotificationFrameGlow.BackgroundTransparency = 1.000
        NotificationFrameGlow.BorderSizePixel = 0
        NotificationFrameGlow.Position = UDim2.new(0, -15, 0, -15)
        NotificationFrameGlow.Size = UDim2.new(1, 30, 1, 30)
        NotificationFrameGlow.ZIndex = 0
        NotificationFrameGlow.Image = "rbxassetid://4996891970"
        NotificationFrameGlow.ImageColor3 = Color3.fromRGB(15, 15, 15)
        NotificationFrameGlow.ScaleType = Enum.ScaleType.Slice
        NotificationFrameGlow.SliceCenter = Rect.new(20, 20, 280, 280)
  
        NotificationTitle.Name = "NotificationTitle"
        NotificationTitle.Parent = NotificationFrame
        NotificationTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        NotificationTitle.BackgroundTransparency = 1.000
        NotificationTitle.Position = UDim2.new(0.0400609747, 0, 0.0761325806, 0)
        NotificationTitle.Size = UDim2.new(0, 111, 0, 34)
        NotificationTitle.Font = Enum.Font.GothamBold
        NotificationTitle.Text = Title.Text .. " | NOTIFICATION"
        NotificationTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
        NotificationTitle.TextSize = 24.000
        NotificationTitle.TextXAlignment = Enum.TextXAlignment.Left
        NotificationTitle.TextTransparency = 1
  
        CloseBtn.Name = "CloseBtn"
        CloseBtn.Parent = NotificationFrame
        CloseBtn.BackgroundColor3 = Color3.fromRGB(21, 21, 21)
        CloseBtn.ClipsDescendants = true
        CloseBtn.Position = UDim2.new(0.0403124988, 0, 0.720855951, 0)
        CloseBtn.Size = UDim2.new(0, 366, 0, 43)
        CloseBtn.AutoButtonColor = false
        CloseBtn.Font = Enum.Font.Gotham
        CloseBtn.Text = buttontitle
        CloseBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
        CloseBtn.TextSize = 15.000
        CloseBtn.TextTransparency = 1
        CloseBtn.BackgroundTransparency = 1
  
        CloseBtnCorner.CornerRadius = UDim.new(0, 4)
        CloseBtnCorner.Name = "CloseBtnCorner"
        CloseBtnCorner.Parent = CloseBtn
  
        NotificationDesc.Name = "NotificationDesc"
        NotificationDesc.Parent = NotificationFrame
        NotificationDesc.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        NotificationDesc.BackgroundTransparency = 1.000
        NotificationDesc.Position = UDim2.new(0.112499997, 0, 0.266355127, 0)
        NotificationDesc.Size = UDim2.new(0, 309, 0, 82)
        NotificationDesc.Font = Enum.Font.Gotham
        NotificationDesc.Text = desc
        NotificationDesc.TextColor3 = Color3.fromRGB(255, 255, 255)
        NotificationDesc.TextSize = 15.000
        NotificationDesc.TextWrapped = true
        NotificationDesc.TextTransparency = 1
        
        CloseBtn.MouseEnter:Connect(function()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 0}
           ):Play()
        end)
  
        CloseBtn.MouseLeave:Connect(function()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 0.3}
           ):Play()
        end)
        
        CloseBtn.MouseButton1Click:Connect(function()
           
           TweenService:Create(
              NotificationDesc,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 1}
           ):Play()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 1}
           ):Play()
           TweenService:Create(
              NotificationTitle,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 1}
           ):Play()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {BackgroundTransparency = 1}
           ):Play()
           
           wait(.4)
           CloseBtn.Visible = false
           NotificationFrame:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
  
           wait(.2)
           
           TweenService:Create(
              NotificationBase,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {BackgroundTransparency = 1}
           ):Play()
           
           wait(.2)
           
           NotificationBase.Visible = false
        end)
  
        
        TweenService:Create(
           NotificationBase,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {BackgroundTransparency = 0.550}
        ):Play()
        
        wait(.1)
        
        NotificationFrame:TweenSize(UDim2.new(0, 400, 0, 214), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
        
        wait(.4)
        TweenService:Create(
           NotificationDesc,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {TextTransparency = .3}
        ):Play()
        TweenService:Create(
           CloseBtn,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {TextTransparency = .3}
        ):Play()
        TweenService:Create(
           NotificationTitle,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {TextTransparency = 0}
        ):Play()
        TweenService:Create(
           CloseBtn,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {BackgroundTransparency = 0}
        ):Play()
     end
     local Tabs = {}
     function Tabs:Tab(text,ico)
        local Tab = Instance.new("TextButton")
        local TabIcon = Instance.new("ImageLabel")
        local TabTitle = Instance.new("TextLabel")
        

        Tab.Name = "Tab"
        Tab.Parent = TabHold
        Tab.BackgroundColor3 = PresetColor
        Tab.BorderSizePixel = 0
        Tab.Size = UDim2.new(0, 205, 0, 40)
        Tab.AutoButtonColor = false
        Tab.Font = Enum.Font.SourceSans
        Tab.Text = ""
        Tab.TextColor3 = Color3.fromRGB(0, 0, 0)
        Tab.TextSize = 14.000
        Tab.BackgroundTransparency = 1
  
        TabIcon.Name = "TabIcon"
        TabIcon.Parent = Tab
        TabIcon.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        TabIcon.BackgroundTransparency = 1.000
        TabIcon.Position = UDim2.new(0.0634146333, 0, 0.25, 0)
        TabIcon.Size = UDim2.new(0, 20, 0, 20)
        TabIcon.Image = ico
        TabIcon.ImageTransparency = .3
  
        TabTitle.Name = "TabTitle"
        TabTitle.Parent = Tab
        TabTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        TabTitle.BackgroundTransparency = 1.000
        TabTitle.Position = UDim2.new(0.1902439, 0, 0.25, 0)
        TabTitle.Size = UDim2.new(0, 113, 0, 19)
        TabTitle.Font = Enum.Font.Gotham
        TabTitle.Text = text
        TabTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
        TabTitle.TextSize = 15.000
        TabTitle.TextXAlignment = Enum.TextXAlignment.Left
        TabTitle.TextTransparency = .3
        
        local Container = Instance.new("ScrollingFrame")
        local ContainerLayout = Instance.new("UIListLayout")
  
  
        Container.Name = "Container"
        Container.Parent = ContainerFolder
        Container.Active = true
        Container.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        Container.BackgroundTransparency = 1.000
        Container.BorderSizePixel = 0
        Container.Position = UDim2.new(0.321529746, 0, 0.0475206599, 0)
        Container.Size = UDim2.new(0, 470, 0, 438)
        Container.CanvasSize = UDim2.new(0, 0, 0, 0)
        Container.ScrollBarThickness = 5
        Container.Visible = false
        Container.ScrollBarImageColor3 = Color3.fromRGB(71, 76, 84)
  
        ContainerLayout.Name = "ContainerLayout"
        ContainerLayout.Parent = Container
        ContainerLayout.SortOrder = Enum.SortOrder.LayoutOrder
        ContainerLayout.Padding = UDim.new(0, 15)
        if fs == false then
           fs = true
           TabTitle.TextTransparency = 0
           TabIcon.ImageTransparency = 0
           Tab.BackgroundTransparency = 0
           Container.Visible = true
        end
        
        Tab.MouseButton1Click:Connect(function()
           for i, v in next, ContainerFolder:GetChildren() do
              if v.Name == "Container" then
                 v.Visible = false
              end
              Container.Visible = true
           end
           for i, v in next, TabHold:GetChildren() do
              if v.Name == "Tab" then
                 TweenService:Create(
                    v,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    v.TabIcon,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    v.TabTitle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    Tab,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    TabIcon,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    TabTitle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
              end
           end
        end)
        local ContainerContent = {}
        function ContainerContent:Button(text, desc, callback)
           if desc == "" then
              desc = "There is no description for this button."
           end
           local BtnDescToggled = false
           local Button = Instance.new("TextButton")
           local ButtonCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
  
           Button.Name = "Button"
           Button.Parent = Container
           Button.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Button.ClipsDescendants = true
           Button.Position = UDim2.new(0.370312512, 0, 0.552631557, 0)
           Button.Size = UDim2.new(0, 457, 0, 43)
           Button.AutoButtonColor = false
           Button.Font = Enum.Font.SourceSans
           Button.Text = ""
           Button.TextColor3 = Color3.fromRGB(0, 0, 0)
           Button.TextSize = 14.000
  
           ButtonCorner.CornerRadius = UDim.new(0, 4)
           ButtonCorner.Name = "ButtonCorner"
           ButtonCorner.Parent = Button
  
           Title.Name = "Title"
           Title.Parent = Button
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(255,255,255)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.200942323, 0, 0.785714269, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 1
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Button
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           ArrowIco.ImageTransparency = .3
           
           Button.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
           
           Button.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
           
           Button.MouseButton1Click:Connect(function()
              pcall(callback)
           end)
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if BtnDescToggled == false then
                 Button:TweenSize(UDim2.new(0, 457, 0, 74), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Button:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              BtnDescToggled = not BtnDescToggled
           end)
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Toggle(text, desc,default, callback)
           local ToggleDescToggled = false
           local Toggled = false
           if desc == "" then
              desc = "There is no description for this toggle."
           end
           local Toggle = Instance.new("TextButton")
           local ToggleCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local ToggleFrame = Instance.new("Frame")
           local ToggleFrameCorner = Instance.new("UICorner")
           local ToggleCircle = Instance.new("Frame")
           local ToggleCircleCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
  
           Toggle.Name = "Toggle"
           Toggle.Parent = Container
           Toggle.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Toggle.ClipsDescendants = true
           Toggle.Position = UDim2.new(0.110937506, 0, 0.67653507, 0)
           Toggle.Size = UDim2.new(0, 457, 0, 43)
           Toggle.AutoButtonColor = false
           Toggle.Font = Enum.Font.SourceSans
           Toggle.Text = ""
           Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
           Toggle.TextSize = 14.000
  
           ToggleCorner.CornerRadius = UDim.new(0, 4)
           ToggleCorner.Name = "ToggleCorner"
           ToggleCorner.Parent = Toggle
  
           Title.Name = "Title"
           Title.Parent = Toggle
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           ToggleFrame.Name = "ToggleFrame"
           ToggleFrame.Parent = Circle
           ToggleFrame.BackgroundColor3 = Color3.fromRGB(226, 227, 227)
           ToggleFrame.Position = UDim2.new(33.0856934, 0, 0, 0)
           ToggleFrame.Size = UDim2.new(0, 27, 0, 11)
  
           ToggleFrameCorner.Name = "ToggleFrameCorner"
           ToggleFrameCorner.Parent = ToggleFrame
  
           ToggleCircle.Name = "ToggleCircle"
           ToggleCircle.Parent = ToggleFrame
           ToggleCircle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ToggleCircle.Position = UDim2.new(0, 0, -0.272727281, 0)
           ToggleCircle.Selectable = true
           ToggleCircle.Size = UDim2.new(0, 17, 0, 17)
  
           ToggleCircleCorner.CornerRadius = UDim.new(2, 8)
           ToggleCircleCorner.Name = "ToggleCircleCorner"
           ToggleCircleCorner.Parent = ToggleCircle
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.200942323, 0, 0.785714269, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 1
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Toggle
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(86, 86, 86)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           ArrowIco.ImageTransparency = .3
           
            Toggle.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           Toggle.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
  
           Toggle.MouseButton1Click:Connect(function()
              if Toggled == false then
                 ToggleCircle:TweenPosition(UDim2.new(0.37, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                 TweenService:Create(
                    ToggleCircle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 =PresetColor}
                 ):Play()
              else
                 ToggleCircle:TweenPosition(UDim2.new(0, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                 TweenService:Create(
                    ToggleCircle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
              end
              Toggled = not Toggled
              pcall(callback, Toggled)
           end)
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if ToggleDescToggled == false then
                 Toggle:TweenSize(UDim2.new(0, 457, 0, 74), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Toggle:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              ToggleDescToggled = not ToggleDescToggled
           end)
           if default == true then
              ToggleCircle:TweenPosition(UDim2.new(0.37, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
              TweenService:Create(
                 ToggleCircle,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {BackgroundColor3 =PresetColor}
              ):Play()
              Toggled = not Toggled
              pcall(callback, Toggled)
           end
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        
        function ContainerContent:Slider(text,desc,min,max,start,callback)
           local SliderFunc = {}
           local SliderDescToggled = false
                          local dragging = false
           if desc == "" then
              desc = "There is no description for this slider."
           end
           local Slider = Instance.new("TextButton")
           local SliderCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local SlideFrame = Instance.new("Frame")
           local CurrentValueFrame = Instance.new("Frame")
           local SlideCircle = Instance.new("ImageButton")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
           local Value = Instance.new("TextLabel")
  
           Slider.Name = "Slider"
           Slider.Parent = Container
           Slider.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Slider.ClipsDescendants = true
           Slider.Position = UDim2.new(0.189062506, 0, 0.648612201, 0)
           Slider.Size = UDim2.new(0, 457, 0, 60)
           Slider.AutoButtonColor = false
           Slider.Font = Enum.Font.SourceSans
           Slider.Text = ""
           Slider.TextColor3 = Color3.fromRGB(0, 0, 0)
           Slider.TextSize = 14.000
  
           SliderCorner.CornerRadius = UDim.new(0, 4)
           SliderCorner.Name = "SliderCorner"
           SliderCorner.Parent = Slider
  
           Title.Name = "Title"
           Title.Parent = Slider
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.201000005, 0, 1.38600004, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 0.300
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           SlideFrame.Name = "SlideFrame"
           SlideFrame.Parent = Title
           SlideFrame.BackgroundColor3 = Color3.fromRGB(235, 234, 235)
           SlideFrame.BorderSizePixel = 0
           SlideFrame.Position = UDim2.new(-0.197140202, 0, 0.986091495, 0)
           SlideFrame.Size = UDim2.new(0, 426, 0, 3)
  
           CurrentValueFrame.Name = "CurrentValueFrame"
           CurrentValueFrame.Parent = SlideFrame
           CurrentValueFrame.BackgroundColor3 = PresetColor
           CurrentValueFrame.BorderSizePixel = 0
           CurrentValueFrame.Size = UDim2.new((start or 0) / max, 0, 0, 3)
  
           SlideCircle.Name = "SlideCircle"
           SlideCircle.Parent = SlideFrame
           SlideCircle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           SlideCircle.BackgroundTransparency = 1.000
           SlideCircle.Position = UDim2.new((start or 0)/max, -6,-1.30499995, 0)
           SlideCircle.Size = UDim2.new(0, 11, 0, 11)
           SlideCircle.Image = "rbxassetid://3570695787"
           SlideCircle.ImageColor3 = PresetColor
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Slider
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(86, 86, 86)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           ArrowIco.ImageTransparency = .3
  
           Value.Name = "Value"
           Value.Parent = Title
           Value.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Value.BackgroundTransparency = 1.000
           Value.Position = UDim2.new(2.27693367, 0, 0, 0)
           Value.Size = UDim2.new(0, 113, 0, 41)
           Value.Font = Enum.Font.Gotham
           Value.Text = tostring(start and math.floor((start / max) * (max - min) + min) or 0)
           Value.TextColor3 = Color3.fromRGB(255, 255, 255)
           Value.TextSize = 15.000
           Value.TextTransparency = 0.300
           Value.TextXAlignment = Enum.TextXAlignment.Right
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if SliderDescToggled == false then
                 Slider:TweenSize(UDim2.new(0, 457, 0, 101), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    Value,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 =PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Slider:TweenSize(UDim2.new(0, 457, 0, 60), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Value,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              SliderDescToggled = not SliderDescToggled
           end)
           
              local function move(input)
                 local pos =
                    UDim2.new(
                       math.clamp((input.Position.X - SlideFrame.AbsolutePosition.X) / SlideFrame.AbsoluteSize.X, 0, 1),
                       -6,
                    -1.30499995,
                       0
                    )
                 local pos1 =
                    UDim2.new(
                       math.clamp((input.Position.X - SlideFrame.AbsolutePosition.X) / SlideFrame.AbsoluteSize.X, 0, 1),
                       0,
                       0,
                       3
                    )
                 CurrentValueFrame:TweenSize(pos1, "Out", "Sine", 0.1, true)
                 SlideCircle:TweenPosition(pos, "Out", "Sine", 0.1, true)
                 local value = math.floor(((pos.X.Scale * max) / max) * (max - min) + min)
                 Value.Text = tostring(value)
                 pcall(callback, value)
              end
              SlideCircle.InputBegan:Connect(
                 function(input)
                    if input.UserInputType == Enum.UserInputType.MouseButton1 then
                       dragging = true
                    end
                 end
              )
              SlideCircle.InputEnded:Connect(
                 function(input)
                    if input.UserInputType == Enum.UserInputType.MouseButton1 then
                       dragging = false
                    end
                 end
              )
              game:GetService("UserInputService").InputChanged:Connect(
              function(input)
                 if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then
                    move(input)
                 end
              end
              )
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
           function SliderFunc:Change(tochange)
              CurrentValueFrame.Size = UDim2.new((tochange or 0) / max, 0, 0, 3)
              SlideCircle.Position = UDim2.new((tochange or 0)/max, -6,-1.30499995, 0)
              Value.Text = tostring(tochange and math.floor((tochange / max) * (max - min) + min) or 0)
              pcall(callback,tochange)
           end
           return SliderFunc
        end
        function ContainerContent:Dropdown(text,list,callback)
           local DropFunc = {}
           local Selected = text
           local FrameSize = 43
           local ItemCount = 0
           local DropToggled = false
           local Dropdown = Instance.new("TextButton")
           local DropdownCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local ArrowIco = Instance.new("ImageLabel")
           local DropItemHolder = Instance.new("ScrollingFrame")
           local DropLayout = Instance.new("UIListLayout")
  
           Dropdown.Name = "Dropdown"
           Dropdown.Parent = Container
           Dropdown.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Dropdown.ClipsDescendants = true
           Dropdown.Position = UDim2.new(0.110937499, 0, 0.67653507, 0)
           Dropdown.Size = UDim2.new(0, 457, 0, 43)
           Dropdown.AutoButtonColor = false
           Dropdown.Font = Enum.Font.SourceSans
           Dropdown.Text = ""
           Dropdown.TextColor3 = Color3.fromRGB(0, 0, 0)
           Dropdown.TextSize = 14.000
  
           DropdownCorner.CornerRadius = UDim.new(0, 4)
           DropdownCorner.Name = "DropdownCorner"
           DropdownCorner.Parent = Dropdown
  
           Title.Name = "Title"
           Title.Parent = Dropdown
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = Title
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(3.45979357, 0, 0.508096159, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6035047377"
           ArrowIco.ImageTransparency = .3
  
           DropItemHolder.Name = "DropItemHolder"
           DropItemHolder.Parent = Title
           DropItemHolder.Active = true
           DropItemHolder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           DropItemHolder.BackgroundTransparency = 1.000
           DropItemHolder.BorderSizePixel = 0
           DropItemHolder.Position = UDim2.new(-0.203539819, 0, 1.02380955, 0)
           DropItemHolder.Size = UDim2.new(0, 436, 0, 82)
           DropItemHolder.CanvasSize = UDim2.new(0, 0, 0, 0)
           DropItemHolder.ScrollBarThickness = 5
           DropItemHolder.ScrollBarImageColor3 = Color3.fromRGB(35, 35, 35)
  
           DropLayout.Name = "DropLayout"
           DropLayout.Parent = DropItemHolder
           DropLayout.SortOrder = Enum.SortOrder.LayoutOrder
           DropLayout.Padding = UDim.new(0, 2)
           
           Dropdown.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           Dropdown.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
  
           
           Dropdown.MouseButton1Click:Connect(function()
              if DropToggled == false then
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, FrameSize), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           DropToggled = not DropToggled
           end)
           
           for i,v in next, list do
              ItemCount = ItemCount + 1
              
              if ItemCount == 1 then
                 FrameSize = 78
              elseif ItemCount == 2 then
                 FrameSize = 107
              elseif ItemCount >= 3 then
                 FrameSize = 133
              end
              local Item = Instance.new("TextButton")
              local ItemCorner = Instance.new("UICorner")
              
           Item.Name = "Item"
           Item.Parent = DropItemHolder
           Item.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Item.ClipsDescendants = true
           Item.Size = UDim2.new(0, 427, 0, 25)
           Item.AutoButtonColor = false
           Item.Font = Enum.Font.Gotham
           Item.Text = v
           Item.TextColor3 = Color3.fromRGB(255, 255, 255)
           Item.TextSize = 15.000
           Item.TextTransparency = 0.300
  
           ItemCorner.CornerRadius = UDim.new(0, 4)
           ItemCorner.Name = "ItemCorner"
              ItemCorner.Parent = Item
              DropItemHolder.CanvasSize = UDim2.new(0, 0, 0, DropLayout.AbsoluteContentSize.Y)
              
              Item.MouseEnter:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
              end)
  
              Item.MouseLeave:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
              end)
              
              Item.MouseButton1Click:Connect(function()
                 pcall(callback, v)
                 Title.Text = text
                 Selected = v
                 DropToggled = not DropToggled
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
                 
              end)
           end
           function DropFunc:Add(addtext)
              ItemCount = ItemCount + 1
  
              if ItemCount == 1 then
                 FrameSize = 78
              elseif ItemCount == 2 then
                 FrameSize = 107
              elseif ItemCount >= 3 then
                 FrameSize = 133
              end
              local Item = Instance.new("TextButton")
              local ItemCorner = Instance.new("UICorner")
  
              Item.Name = "Item"
              Item.Parent = DropItemHolder
              Item.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
              Item.ClipsDescendants = true
              Item.Size = UDim2.new(0, 427, 0, 25)
              Item.AutoButtonColor = false
              Item.Font = Enum.Font.Gotham
              Item.Text = addtext
              Item.TextColor3 = Color3.fromRGB(255, 255, 255)
              Item.TextSize = 15.000
              Item.TextTransparency = 0.300
  
              ItemCorner.CornerRadius = UDim.new(0, 4)
              ItemCorner.Name = "ItemCorner"
              ItemCorner.Parent = Item
              DropItemHolder.CanvasSize = UDim2.new(0, 0, 0, DropLayout.AbsoluteContentSize.Y)
  
              Item.MouseEnter:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
              end)
  
              Item.MouseLeave:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
              end)
  
              Item.MouseButton1Click:Connect(function()
                 pcall(callback, addtext)
                 Title.Text = text
                 Selected = addtext
                 DropToggled = not DropToggled
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end)
              if DropToggled == true then
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           end
           function DropFunc:Clear()
              Title.Text = text
              FrameSize = 0
              ItemCount = 0
              for i, v in next, DropItemHolder:GetChildren() do
                 if v.Name == "Item" then
                    v:Destroy()
                 end
              end
              if DropToggled == true then
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           end
           return DropFunc
        end
        function ContainerContent:Colorpicker(text,preset,callback)
           local ColorPickerToggled = false
           local OldToggleColor = Color3.fromRGB(0, 0, 0)
           local OldColor = Color3.fromRGB(0, 0, 0)
           local OldColorSelectionPosition = nil
           local OldHueSelectionPosition = nil
           local ColorH, ColorS, ColorV = 1, 1, 1
           local RainbowColorPicker = false
           local ColorPickerInput = nil
           local ColorInput = nil
           local HueInput = nil
           
           local Colorpicker = Instance.new("Frame")
           local ColorpickerCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Hue = Instance.new("ImageLabel")
           local HueCorner = Instance.new("UICorner")
           local HueGradient = Instance.new("UIGradient")
           local HueSelection = Instance.new("ImageLabel")
           local Color = Instance.new("ImageLabel")
           local ColorCorner = Instance.new("UICorner")
           local ColorSelection = Instance.new("ImageLabel")
           local Toggle = Instance.new("TextLabel")
           local ToggleFrame = Instance.new("Frame")
           local ToggleFrameCorner = Instance.new("UICorner")
           local ToggleCircle = Instance.new("Frame")
           local ToggleCircleCorner = Instance.new("UICorner")
           local Confirm = Instance.new("TextButton")
           local ConfirmCorner = Instance.new("UICorner")
           local ConfirmTitle = Instance.new("TextLabel")
           local BoxColor = Instance.new("Frame")
           local BoxColorCorner = Instance.new("UICorner")
           local ColorpickerBtn = Instance.new("TextButton")
           local ToggleBtn = Instance.new("TextButton")
  
  
           Colorpicker.Name = "Colorpicker"
           Colorpicker.Parent = Container
           Colorpicker.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
           Colorpicker.ClipsDescendants = true
           Colorpicker.Position = UDim2.new(0.110937499, 0, 0.67653507, 0)
           Colorpicker.Size = UDim2.new(0, 457, 0, 43)
  
           ColorpickerCorner.CornerRadius = UDim.new(0, 4)
           ColorpickerCorner.Name = "ColorpickerCorner"
           ColorpickerCorner.Parent = Colorpicker
  
           Title.Name = "Title"
           Title.Parent = Colorpicker
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = "UI Color Setting"
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
           
  
           ColorpickerBtn.Name = "ColorpickerBtn"
           ColorpickerBtn.Parent = Title
           ColorpickerBtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ColorpickerBtn.BackgroundTransparency = 1.000
           ColorpickerBtn.Position = UDim2.new(-0.336283177, 0, 0, 0)
           ColorpickerBtn.Size = UDim2.new(0, 457, 0, 42)
           ColorpickerBtn.Font = Enum.Font.SourceSans
           ColorpickerBtn.Text = ""
           ColorpickerBtn.TextColor3 = Color3.fromRGB(0, 0, 0)
           ColorpickerBtn.TextSize = 14.000
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Hue.Name = "Hue"
           Hue.Parent = Title
           Hue.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Hue.Position = UDim2.new(0, 229, 0, 46)
           Hue.Size = UDim2.new(0, 25, 0, 80)
  
           HueCorner.CornerRadius = UDim.new(0, 3)
           HueCorner.Name = "HueCorner"
           HueCorner.Parent = Hue
  
           HueGradient.Color = ColorSequence.new {
              ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 0, 4)),
              ColorSequenceKeypoint.new(0.20, Color3.fromRGB(234, 255, 0)),
              ColorSequenceKeypoint.new(0.40, Color3.fromRGB(21, 255, 0)),
              ColorSequenceKeypoint.new(0.60, Color3.fromRGB(0, 255, 255)),
              ColorSequenceKeypoint.new(0.80, Color3.fromRGB(0, 17, 255)),
              ColorSequenceKeypoint.new(0.90, Color3.fromRGB(255, 0, 251)),
              ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 0, 4))
           }			
           HueGradient.Rotation = 270
           HueGradient.Name = "HueGradient"
           HueGradient.Parent = Hue
  
           HueSelection.Name = "HueSelection"
           HueSelection.Parent = Hue
           HueSelection.AnchorPoint = Vector2.new(0.5, 0.5)
           HueSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           HueSelection.BackgroundTransparency = 1.000
           HueSelection.Position = UDim2.new(0.48, 0, 1 - select(1, Color3.toHSV(preset)))
           HueSelection.Size = UDim2.new(0, 18, 0, 18)
           HueSelection.Image = "http://www.roblox.com/asset/?id=4805639000"
           HueSelection.Visible = false
  
           Color.Name = "Color"
           Color.Parent = Title
           Color.BackgroundColor3 = Color3.fromRGB(255, 0, 4)
           Color.Position = UDim2.new(0, -23, 0, 46)
           Color.Size = UDim2.new(0, 246, 0, 80)
           Color.ZIndex = 10
           Color.Image = "rbxassetid://4155801252"
  
           ColorCorner.CornerRadius = UDim.new(0, 3)
           ColorCorner.Name = "ColorCorner"
           ColorCorner.Parent = Color
  
           ColorSelection.Name = "ColorSelection"
           ColorSelection.Parent = Color
           ColorSelection.AnchorPoint = Vector2.new(0.5, 0.5)
           ColorSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ColorSelection.BackgroundTransparency = 1.000
           ColorSelection.Position = UDim2.new(preset and select(3, Color3.toHSV(preset)))
           ColorSelection.Size = UDim2.new(0, 18, 0, 18)
           ColorSelection.Image = "http://www.roblox.com/asset/?id=4805639000"
           ColorSelection.ScaleType = Enum.ScaleType.Fit
           ColorSelection.Visible = false
  
           Toggle.Name = "Toggle"
           Toggle.Parent = Title
           Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Toggle.BackgroundTransparency = 1.000
           Toggle.Position = UDim2.new(2.37430048, 0, 1.07157099, 0)
           Toggle.Size = UDim2.new(0, 137, 0, 38)
           Toggle.Font = Enum.Font.Gotham
           Toggle.Text = "Rainbow"
           Toggle.TextColor3 = Color3.fromRGB(255, 255, 255)
           Toggle.TextSize = 15.000
           Toggle.TextTransparency = 0.300
           Toggle.TextXAlignment = Enum.TextXAlignment.Left
  
           ToggleFrame.Name = "ToggleFrame"
           ToggleFrame.Parent = Toggle
           ToggleFrame.BackgroundColor3 = Color3.fromRGB(226, 227, 227)
           ToggleFrame.Position = UDim2.new(0.778387249, 0, 0.357142866, 0)
           ToggleFrame.Size = UDim2.new(0, 27, 0, 11)
  
           ToggleFrameCorner.Name = "ToggleFrameCorner"
           ToggleFrameCorner.Parent = ToggleFrame
  
           ToggleCircle.Name = "ToggleCircle"
           ToggleCircle.Parent = ToggleFrame
           ToggleCircle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ToggleCircle.Position = UDim2.new(0, 0, -0.273000002, 0)
           ToggleCircle.Selectable = true
           ToggleCircle.Size = UDim2.new(0, 17, 0, 17)
  
           ToggleCircleCorner.CornerRadius = UDim.new(2, 8)
           ToggleCircleCorner.Name = "ToggleCircleCorner"
           ToggleCircleCorner.Parent = ToggleCircle
  
           Confirm.Name = "Confirm"
           Confirm.Parent = Title
           Confirm.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
           Confirm.ClipsDescendants = true
           Confirm.Position = UDim2.new(2.3791616, 0, 1.97633278, 0)
           Confirm.Size = UDim2.new(0, 144, 0, 42)
           Confirm.AutoButtonColor = false
           Confirm.Font = Enum.Font.SourceSans
           Confirm.Text = ""
           Confirm.TextColor3 = Color3.fromRGB(0, 0, 0)
           Confirm.TextSize = 14.000
  
           ConfirmCorner.CornerRadius = UDim.new(0, 4)
           ConfirmCorner.Name = "ConfirmCorner"
           ConfirmCorner.Parent = Confirm
  
           ConfirmTitle.Name = "ConfirmTitle"
           ConfirmTitle.Parent = Confirm
           ConfirmTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ConfirmTitle.BackgroundTransparency = 1.000
           ConfirmTitle.Size = UDim2.new(0, 116, 0, 40)
           ConfirmTitle.Font = Enum.Font.Gotham
           ConfirmTitle.Text = "Confirm"
           ConfirmTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
           ConfirmTitle.TextSize = 15.000
           ConfirmTitle.TextTransparency = 0.300
           ConfirmTitle.TextXAlignment = Enum.TextXAlignment.Left
  
           BoxColor.Name = "BoxColor"
           BoxColor.Parent = Title
           BoxColor.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           BoxColor.Position = UDim2.new(3.26915574, 0, 0.261904776, 0)
           BoxColor.Size = UDim2.new(0, 35, 0, 19)
  
           BoxColorCorner.CornerRadius = UDim.new(0, 4)
           BoxColorCorner.Name = "BoxColorCorner"
           BoxColorCorner.Parent = BoxColor
  
           ToggleBtn.Name = "ToggleBtn"
           ToggleBtn.Parent = Toggle
           ToggleBtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ToggleBtn.BackgroundTransparency = 1.000
           ToggleBtn.Size = UDim2.new(0, 137, 0, 38)
           ToggleBtn.Font = Enum.Font.SourceSans
           ToggleBtn.Text = ""
           ToggleBtn.TextColor3 = Color3.fromRGB(0, 0, 0)
           ToggleBtn.TextSize = 14.000
           
           ColorpickerBtn.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           ColorpickerBtn.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
            
           ColorpickerBtn.MouseButton1Click:Connect(function()
              if ColorPickerToggled == false then
                 ColorSelection.Visible = true
                 HueSelection.Visible = true
                 Colorpicker:TweenSize(UDim2.new(0, 457, 0, 138), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 ColorSelection.Visible = false
                 HueSelection.Visible = false
                 Colorpicker:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              ColorPickerToggled = not ColorPickerToggled
           end)
           
  
           local function UpdateColorPicker(nope)
              BoxColor.BackgroundColor3 = Color3.fromHSV(ColorH, ColorS, ColorV)
              Color.BackgroundColor3 = Color3.fromHSV(ColorH, 1, 1)
  
              pcall(callback, BoxColor.BackgroundColor3)
           end
  
           ColorH =
              1 -
              (math.clamp(HueSelection.AbsolutePosition.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) /
                 Hue.AbsoluteSize.Y)
           ColorS =
              (math.clamp(ColorSelection.AbsolutePosition.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) /
                 Color.AbsoluteSize.X)
           ColorV =
              1 -
              (math.clamp(ColorSelection.AbsolutePosition.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) /
                 Color.AbsoluteSize.Y)
  
           BoxColor.BackgroundColor3 = preset
           Color.BackgroundColor3 = preset
           pcall(callback, BoxColor.BackgroundColor3)
  
           Color.InputBegan:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if RainbowColorPicker then
                       return
                    end
  
                    if ColorInput then
                       ColorInput:Disconnect()
                    end
  
                    ColorInput =
                       RunService.RenderStepped:Connect(
                          function()
                          local ColorX =
                             (math.clamp(Mouse.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) /
                                Color.AbsoluteSize.X)
                          local ColorY =
                             (math.clamp(Mouse.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) /
                                Color.AbsoluteSize.Y)
  
                          ColorSelection.Position = UDim2.new(ColorX, 0, ColorY, 0)
                          ColorS = ColorX
                          ColorV = 1 - ColorY
  
                          UpdateColorPicker(true)
                       end
                       )
                 end
              end
           )
  
           Color.InputEnded:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if ColorInput then
                       ColorInput:Disconnect()
                    end
                 end
              end
           )
  
           Hue.InputBegan:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if RainbowColorPicker then
                       return
                    end
  
                    if HueInput then
                       HueInput:Disconnect()
                    end
  
                    HueInput =
                       RunService.RenderStepped:Connect(
                          function()
                          local HueY =
                             (math.clamp(Mouse.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) /
                                Hue.AbsoluteSize.Y)
  
                          HueSelection.Position = UDim2.new(0.48, 0, HueY, 0)
                          ColorH = 1 - HueY
  
                          UpdateColorPicker(true)
                       end
                       )
                 end
              end
           )
  
           Hue.InputEnded:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if HueInput then
                       HueInput:Disconnect()
                    end
                 end
              end
           )
  
           ToggleBtn.MouseButton1Down:Connect(
              function()
                 RainbowColorPicker = not RainbowColorPicker
  
                 if ColorInput then
                    ColorInput:Disconnect()
                 end
  
                 if HueInput then
                    HueInput:Disconnect()
                 end
  
                 if RainbowColorPicker then
                    ToggleCircle:TweenPosition(UDim2.new(0.37, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                    TweenService:Create(
                       ToggleCircle,
                       TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                       {BackgroundColor3 =PresetColor}
                    ):Play()
  
                    OldToggleColor = BoxColor.BackgroundColor3
                    OldColor = Color.BackgroundColor3
                    OldColorSelectionPosition = ColorSelection.Position
                    OldHueSelectionPosition = HueSelection.Position
  
                    while RainbowColorPicker do
                       BoxColor.BackgroundColor3 = Color3.fromHSV(Flux.RainbowColorValue, 1, 1)
                       Color.BackgroundColor3 = Color3.fromHSV(Flux.RainbowColorValue, 1, 1)
  
                       ColorSelection.Position = UDim2.new(1, 0, 0, 0)
                       HueSelection.Position = UDim2.new(0.48, 0, 0, Flux.HueSelectionPosition)
  
                       pcall(callback, BoxColor.BackgroundColor3)
                       wait()
                    end
                 elseif not RainbowColorPicker then
                    ToggleCircle:TweenPosition(UDim2.new(0, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                    TweenService:Create(
                       ToggleCircle,
                       TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                       {BackgroundColor3 = Color3.fromRGB(255,255,255)}
                    ):Play()
  
                    BoxColor.BackgroundColor3 = OldToggleColor
                    Color.BackgroundColor3 = OldColor
  
                    ColorSelection.Position = OldColorSelectionPosition
                    HueSelection.Position = OldHueSelectionPosition
  
                    pcall(callback, BoxColor.BackgroundColor3)
                 end
              end
           )
  
           Confirm.MouseButton1Click:Connect(
              function()
                 ColorPickerToggled = not ColorPickerToggled
                 Colorpicker:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           )
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Line()
           local Line = Instance.new("TextButton")
           local LineCorner = Instance.new("UICorner")
  
           Line.Name = "Line"
           Line.Parent = Container
           Line.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           Line.ClipsDescendants = true
           Line.Position = UDim2.new(0, 0, 0.70091325, 0)
           Line.Size = UDim2.new(0, 457, 0, 4)
           Line.AutoButtonColor = false
           Line.Font = Enum.Font.SourceSans
           Line.Text = ""
           Line.TextColor3 = Color3.fromRGB(0, 0, 0)
           Line.TextSize = 14.000
  
           LineCorner.CornerRadius = UDim.new(0, 4)
           LineCorner.Name = "LineCorner"
           LineCorner.Parent = Line
           
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Label(text)
           local labelfunc = {}
           local Label = Instance.new("TextButton")
           local LabelCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
  
           Label.Name = "Label"
           Label.Parent = Container
           Label.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Label.ClipsDescendants = true
           Label.Position = UDim2.new(0.370312512, 0, 0.552631557, 0)
           Label.Size = UDim2.new(0, 457, 0, 43)
           Label.AutoButtonColor = false
           Label.Font = Enum.Font.SourceSans
           Label.Text = ""
           Label.TextColor3 = Color3.fromRGB(0, 0, 0)
           Label.TextSize = 14.000
  
           LabelCorner.CornerRadius = UDim.new(0, 4)
           LabelCorner.Name = "LabelCorner"
           LabelCorner.Parent = Label
  
           Title.Name = "Title"
           Title.Parent = Label
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.038480062, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
           
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
           function labelfunc:Refresh(tochange)
              Title.Text = tochange
           end
           return labelfunc
        end
        function ContainerContent:Textbox(text,desc,disapper,callback)
           if desc == "" then
              desc = "There is no description for this textbox."
           end
           local TextboxDescToggled = false
           local Textbox = Instance.new("TextButton")
           local TextboxCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local TextboxFrame = Instance.new("Frame")
           local TextboxFrameCorner = Instance.new("UICorner")
           local TextBox = Instance.new("TextBox")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
  
           Textbox.Name = "Textbox"
           Textbox.Parent = Container
           Textbox.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           Textbox.ClipsDescendants = true
           Textbox.Position = UDim2.new(0.0459499061, 0, 0.734449744, 0)
           Textbox.Size = UDim2.new(0, 457, 0, 43)
           Textbox.AutoButtonColor = false
           Textbox.Font = Enum.Font.SourceSans
           Textbox.Text = ""
           Textbox.TextColor3 = Color3.fromRGB(0, 0, 0)
           Textbox.TextSize = 14.000
  
           TextboxCorner.CornerRadius = UDim.new(0, 4)
           TextboxCorner.Name = "TextboxCorner"
           TextboxCorner.Parent = Textbox
  
           Title.Name = "Title"
           Title.Parent = Textbox
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.200942323, 0, 0.985714269, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 1
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           TextboxFrame.Name = "TextboxFrame"
           TextboxFrame.Parent = Title
           TextboxFrame.BackgroundColor3 = Color3.fromRGB(50, 53, 59)
           TextboxFrame.Position = UDim2.new(1.82300889, 0, 0.202380955, 0)
           TextboxFrame.Size = UDim2.new(0, 161, 0, 26)
  
           TextboxFrameCorner.CornerRadius = UDim.new(0, 4)
           TextboxFrameCorner.Name = "TextboxFrameCorner"
           TextboxFrameCorner.Parent = TextboxFrame
  
           TextBox.Parent = TextboxFrame
           TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           TextBox.BackgroundTransparency = 1.000
           TextBox.Size = UDim2.new(0, 161, 0, 26)
           TextBox.Font = Enum.Font.Gotham
           TextBox.Text = ""
           TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
           TextBox.TextSize = 15.000
           TextBox.TextTransparency = 0.300
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Textbox
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(86, 86, 86)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           
           TextBox.FocusLost:Connect(
              function(ep)
                 if ep then
                    if #TextBox.Text > 0 then
                       pcall(callback, TextBox.Text)
                       if disapper then
                          TextBox.Text = ""
                       end
                    end
                 end
              end
           )
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if TextboxDescToggled == false then
                 Textbox:TweenSize(UDim2.new(0, 457, 0, 81), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Textbox:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              TextboxDescToggled = not TextboxDescToggled
           end)
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Bind(text,presetbind,callback)
           local Key = presetbind.Name
           local Bind = Instance.new("TextButton")
           local BindCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local BindLabel = Instance.new("TextLabel")
  
           Bind.Name = "Bind"
           Bind.Parent = Container
           Bind.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           Bind.ClipsDescendants = true
           Bind.Position = UDim2.new(0.40625, 0, 0.828947306, 0)
           Bind.Size = UDim2.new(0, 457, 0, 43)
           Bind.AutoButtonColor = false
           Bind.Font = Enum.Font.SourceSans
           Bind.Text = ""
           Bind.TextColor3 = Color3.fromRGB(0, 0, 0)
           Bind.TextSize = 14.000
  
           BindCorner.CornerRadius = UDim.new(0, 4)
           BindCorner.Name = "BindCorner"
           BindCorner.Parent = Bind
  
           Title.Name = "Title"
           Title.Parent = Bind
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           BindLabel.Name = "BindLabel"
           BindLabel.Parent = Title
           BindLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           BindLabel.BackgroundTransparency = 1.000
           BindLabel.Position = UDim2.new(2.56011987, 0, 0, 0)
           BindLabel.Size = UDim2.new(0, 113, 0, 42)
           BindLabel.Font = Enum.Font.Gotham
           BindLabel.Text = Key
           BindLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
           BindLabel.TextSize = 15.000
           BindLabel.TextTransparency = 0.300
           BindLabel.TextXAlignment = Enum.TextXAlignment.Right
           
           Bind.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           Bind.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
  
           Bind.MouseButton1Click:connect(
              function()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 BindLabel.Text = "..."
                 local inputwait = game:GetService("UserInputService").InputBegan:wait()
                 if inputwait.KeyCode.Name ~= "Unknown" then
                    BindLabel.Text = inputwait .KeyCode.Name
                    Key = inputwait .KeyCode.Name
                 end
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
              end
           )
  
           game:GetService("UserInputService").InputBegan:connect(
           function(current, pressed)
              if not pressed then
                 if current.KeyCode.Name == Key then
                    pcall(callback)
                 end
              end
           end
           )
           
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        return ContainerContent
     end
     return Tabs
  end
  local win = Flux:Window("JPEXHUB", "King lecacy",getgenv().ColorUi,_G.OffOnUI)
 local AutoFarms = win:Tab("Auto Fram","http://www.roblox.com/asset/?id=7100202580")

   local mt = getrawmetatable(game)
   local newindex = mt.__newindex

   setreadonly(mt,false)

   mt.__newindex = function(a,b,c)
       if b == 'CFrame' and a.Name == 'HumanoidRootPart' and string.find(getfenv(2).script:GetFullName(), 'Services.Client')  then
           return newindex(a,b, a.CFrame)
       end

       return newindex(a,b,c)
   end
       function CheckQuest()
         local MyLevel = game.Players.LocalPlayer.PlayerStats.lvl.Value
         if OldWorld then
             if MyLevel == 1 or MyLevel <= 9 then
                 CFrameQuest = CFrame.new(2277.1884765625, 48.143299102783, -1648.5339355469)
                 CFrameMon = CFrame.new(2388.6013183594, 148.19408416748, -1578.6862792969)
                 NameMon = "Soldier"
                 Ms = "Soldier [Lv. 1]"
             elseif MyLevel == 10 or MyLevel <= 19 then
                 CFrameQuest = CFrame.new(2496.5114746094, 48.135684967041, -1771.6900634766)
                 CFrameMon = CFrame.new(2388.6013183594, 148.19408416748, -1578.6862792969)
                 NameMon = "Clown Pirate"
                 Ms = "Clown Pirate [Lv. 10]"
             elseif MyLevel == 20 or MyLevel <= 29 then
                 CFrameQuest = CFrame.new(2231.0498046875, 48.153293609619, -1779.0476074219)
                 CFrameMon = CFrame.new(2293.3962402344, 148.193294525146, -1802.6019287109)
                 NameMon = "Smoky"
                 Ms = "Smoky [Lv. 20]"
             elseif MyLevel == 30 or MyLevel <= 74 then
                 CFrameQuest = CFrame.new(2011.1265869141, 48.143299102783, -1810.4008789063)
                 CFrameMon = CFrame.new(2091.3608398438, 148.193294525146, -1928.6489257813)
                 NameMon = "Tashi"
                 Ms = "Tashi [Lv. 30]"
             elseif MyLevel == 75 or MyLevel <= 144 then
                 CFrameQuest = CFrame.new(3751.44165, 69.0870895, -564.072815, 0.529884458, -0, -0.848069847, 0, 1, -0, 0.848069847, 0, 0.529884458)
                 CFrameMon = CFrame.new(3751.44165, 69.0870895, -564.072815, 0.529884458, -0, -0.848069847, 0, 1, -0, 0.848069847, 0, 0.529884458)
                 NameMon = "The Clown"
                 Ms = "The Clown [Lv. 75]"
             elseif MyLevel == 145 or MyLevel <= 179 then
                 CFrameQuest = CFrame.new(1743.97546, 69.5770111, 348.256134, 0.241506964, 0.889585376, 0.387701184, 0.966802657, -0.186209321, -0.17498143, -0.0834672004, 0.41708988, -0.905024409)
                 CFrameMon = CFrame.new(1743.97546, 69.5770111, 348.256134, 0.241506964, 0.889585376, 0.387701184, 0.966802657, -0.186209321, -0.17498143, -0.0834672004, 0.41708988, -0.905024409)
                 NameMon = "Axe-Hand"
                 Ms = "Axe-Hand [Lv. 145]"
             elseif MyLevel == 180 or MyLevel <= 229 then
                 CFrameQuest = CFrame.new(3231.89673, 10.889246, 1516.1969, 0.819155693, -0, -0.573571265, 0, 1, -0, 0.573571265, 0, 0.819155693)
                 CFrameMon = CFrame.new(3231.89673, 10.889246, 1516.1969, 0.819155693, -0, -0.573571265, 0, 1, -0, 0.573571265, 0, 0.819155693)
                 NameMon = "Fishman"
                 Ms = "Fishman [Lv. 180]"
             elseif MyLevel == 230 or MyLevel <= 249 then
                 CFrameQuest = CFrame.new(3651.37427, 10.8831606, 1511.43884, -0.801726937, 0, 0.597690463, 0, 1, 0, -0.597690463, 0, -0.801726937)
                 CFrameMon = CFrame.new(3651.37427, 10.8831606, 1511.43884, -0.801726937, 0, 0.597690463, 0, 1, 0, -0.597690463, 0, -0.801726937)
                 NameMon = "SharkMan"
                 Ms = "SharkMan [Lv. 230]"
             elseif MyLevel == 250 or MyLevel <= 299 then
                CFrameQuest = CFrame.new(-51.7463303, 49.7374306, -87.7024078)
                CFrameMon = CFrame.new(4408.55518, 110.4656439, 3199.33618)
                NameMon = "Trainer Chef"
                Ms = "Trainer Chef [Lv. 250]"
             elseif MyLevel == 300 or MyLevel <= 349 then
                CFrameQuest = CFrame.new(39.4004707, 99.5126801, -47.8512077)
                CFrameMon = CFrame.new(96.1493149, 112.94034, -143.488434)
                NameMon = "Dark Leg"
                Ms = "Dark Leg [Lv. 300]"
             elseif MyLevel == 350 or MyLevel <= 399 then
                CFrameQuest = CFrame.new(-44.2784309, 49.7609177, 115.918266)
                CFrameMon = CFrame.new(-103.605598, 112.94034, 233.536148)
                NameMon = "Weapon Man"
                Ms = "Weapon Man [Lv. 350]"
             elseif MyLevel == 400 or MyLevel <= 449 then
               CFrameQuest = CFrame.new(-2851.466796875, 18.111785888672, 1420.4886474609)
               CFrameMon = CFrame.new(-2818.3337402344, 118.12328338623, 1470.3162841797)
               NameMon = "Snow Soldier"
               Ms = "Snow Soldier [Lv. 400]"
             elseif MyLevel == 450 or MyLevel <= 524 then
               CFrameQuest = CFrame.new(-2838.9370117188, 18.091789245605, 1319.8012695313)
               CFrameMon = CFrame.new(-2860.3764648438, 118.121784210205, 1293.3358154297)
               NameMon = "King Snow"
               Ms = "King Snow [Lv. 450]"
             elseif MyLevel == 525 or MyLevel <= 624 then
               CFrameQuest = CFrame.new(1731.5385742188, 12.902250289917, 3644.4453125)
               CFrameMon = CFrame.new(1761.9046630859, 112.971120834351, 3610.41015625)
               NameMon = "Candle Man"
               Ms = "Candle Man [Lv. 525]"
             elseif MyLevel == 625 or MyLevel <= 724 then
               CFrameQuest = CFrame.new(1520.1804199219, 12.902250289917, 3431.5466308594)
               CFrameMon = CFrame.new(1538.6333007813, 112.902250289917, 3397.02734375)
               NameMon = "Bomb Man"
               Ms = "Bomb Man [Lv. 625]"
             elseif MyLevel == 725 or MyLevel <= 799 then
               CFrameQuest = CFrame.new(1511.4117431641, 43.04167175293, 3541.400390625)
               CFrameMon = CFrame.new(1478.7867431641, 102.56248474121, 3638.8305664063)
               NameMon = "King of Sand"
               Ms = "King of Sand [Lv. 725]"
             elseif MyLevel == 800 or MyLevel <= 849 then
               CFrameQuest = CFrame.new(-1251.8015136719, 200.67266845703, 4581.4990234375)
               CFrameMon = CFrame.new(-1294.9228515625, 422.30653381348, 4678.55859375)
               NameMon = "Sky Soldier"
               Ms = "Sky Soldier [Lv. 800]"
             elseif MyLevel == 850 or MyLevel <= 899 then
               CFrameQuest = CFrame.new(-818.76123046875, 386.42059326172, 4745.69921875)
               CFrameMon = CFrame.new(-790.27984619141, 486.47073364258, 4807.623046875)
               NameMon = "Ball Man"
               Ms = "Ball Man [Lv. 850]"
             elseif MyLevel == 900 or MyLevel <= 999 then
               CFrameQuest = CFrame.new(-861.33489990234, 386.42074584961, 4879.1186523438)
               CFrameMon = CFrame.new(-895.37359619141, 486.42074584961, 4946.294921875)
               NameMon = "Rumble Man"
               Ms = "Rumble Man [Lv. 900]"
             elseif MyLevel == 1000 or MyLevel <= 1099 then
               CFrameQuest = CFrame.new(8271.4833984375, 11.896879196167, 5437.4653320313)
               CFrameMon = CFrame.new(8333.201171875, 111.846879959106, 5465.994140625)
               NameMon = "Soldier"
               Ms = "Soldier [Lv. 1000]"
             elseif MyLevel == 1100 or MyLevel <= 1149 then
               CFrameQuest = CFrame.new(8176.1176757813, 11.846877098083, 5287.4770507813)
               CFrameMon = CFrame.new(8274.4404296875, 123.251501083374, 5267.7802734375)
               NameMon = "Leader"
               Ms = "Leader [Lv. 1100]"
             elseif MyLevel == 1150 or MyLevel <= 1249 then
               CFrameQuest = CFrame.new(8176.1176757813, 11.846877098083, 5287.4770507813)
               CFrameMon = CFrame.new(8274.4404296875, 123.251501083374, 5267.7802734375)
               NameMon = "Pasta"
               Ms = "Pasta [Lv. 1150]"
             elseif MyLevel == 1250 or MyLevel <= 1324 then
               CFrameQuest = CFrame.new(4210.1782226563, 13.030811309814, 6768.8955078125)
               CFrameMon = CFrame.new(4166.5815429688, 113.090654373169, 6898.6127929688)
               NameMon = "Wolf"
               Ms = "Wolf [Lv. 1250]"
             elseif MyLevel == 1325 or MyLevel <= 1399 then
               CFrameQuest = CFrame.new(4311.3798828125, 13.042789459229, 6978.6538085938)
               CFrameMon = CFrame.new(4379.4565429688, 113.090654373169, 6949.353515625)
               NameMon = "Giraffe"
               Ms = "Giraffe [Lv. 1325]"
             elseif MyLevel == 1400 or MyLevel <= 1499 then
               CFrameQuest = CFrame.new(4312.81640625, 13.059648513794, 7417.8813476563)
               CFrameMon = CFrame.new(4391.2377929688, 112.961982727051, 7569.0166015625)
               NameMon = "Leo"
               Ms = "Leo [Lv. 1400]"
             elseif MyLevel == 1500 or MyLevel <= 1599 then
               CFrameQuest = CFrame.new(-776.28472900391, 47.856597900391, 8478.431640625)
               CFrameMon = CFrame.new(-778.30328369141, 147.856491088867, 8537.9267578125)
               NameMon = "Zombie"
               Ms = "Zombie [Lv. 1500]"
             elseif MyLevel == 1600 or MyLevel <= 1749 then
               CFrameQuest = CFrame.new(-793.65240478516, 47.857288360596, 8329.0654296875)
               CFrameMon = CFrame.new(-793.65240478516, 197.857288360596, 8329.0654296875)
               NameMon = "Shadow Master"
               Ms = "Shadow Master [Lv. 1600]"
             elseif MyLevel == 1750 or MyLevel <= 1799 then
               CFrameQuest = CFrame.new(8601.7705078125, 49.582111358643, 1731.2292480469)
               CFrameMon = CFrame.new(8601.7705078125, 199.582111358643, 1731.2292480469)
               NameMon = "New World Pirate"
               Ms = "New World Pirate [Lv. 1750]"
             elseif MyLevel == 1800 or MyLevel <= 1924 then
               CFrameQuest = CFrame.new(8580.9599609375, 49.578090667725, 1347.4166259766)
               CFrameMon = CFrame.new(8580.9599609375, 199.578090667725, 1347.4166259766)
               NameMon = "Rear Admiral"
               Ms = "Rear Admiral [Lv. 1800]"
             elseif MyLevel == 1925 or MyLevel <= 1849 then
               CFrameQuest = CFrame.new(8242.3994140625, 49.60005569458, 1392.0007324219)
               CFrameMon = CFrame.new(8242.3994140625, 199.60005569458, 1392.0007324219)
               NameMon = "Quake Woman"
               Ms = "Quake Woman [Lv. 1925]"
             elseif MyLevel == 1850 or MyLevel <= 1999 then
               CFrameQuest = CFrame.new(8555.9892578125, 49.57417678833, 1460.2507324219)
               CFrameMon = CFrame.new(8555.9892578125, 199.57417678833, 1460.2507324219)
               NameMon = "True Karate Fishman"
               Ms = "True Karate Fishman [Lv. 1850]"
             elseif MyLevel == 2000 or MyLevel <= 2049 then
               CFrameQuest = CFrame.new(2970.7785644531, 40.2607421875, 13349.877929688)
               CFrameMon = CFrame.new(2970.7785644531, 190.2607421875, 13349.877929688)
               NameMon = "Fishman"
               Ms = "Fishman [Lv. 2000]"
             elseif MyLevel == 2050 or MyLevel <= 2099 then
               CFrameQuest = CFrame.new(2783.875, 40.24825668335, 13617.719726563)
               CFrameMon = CFrame.new(2783.875, 190.24825668335, 13617.719726563)
               NameMon = "Combat Fishman"
               Ms = "Combat Fishman [Lv. 2050]"
             elseif MyLevel == 2100 or MyLevel <= 2149 then
               CFrameQuest = CFrame.new(3297.2663574219, 40.275020599365, 13793.421875)
               CFrameMon = CFrame.new(3297.2663574219, 190.275020599365, 13793.421875)
               NameMon = "Sword Fishman"
               Ms = "Sword Fishman [Lv. 2100]"
             elseif MyLevel == 2150 or MyLevel <= 2199 then
               CFrameQuest = CFrame.new(3019.2189941406, 40.270706176758, 13883.921875)
               CFrameMon = CFrame.new(3019.2189941406, 190.270706176758, 13883.921875)
               NameMon = "Fishman Soldier"
               Ms = "Fishman Soldier [Lv. 2150]"
             elseif MyLevel >= 2200 then
               CFrameQuest = CFrame.new(2785.8464355469, 40.275859832764, 13820.041992188)
               CFrameMon = CFrame.new(2785.8464355469, 190.275859832764, 13820.041992188)
               NameMon = "Seasoned Fishman"
               Ms = "Seasoned Fishman [Lv. 2200]"
             end
         end
         if newworld then
             if MyLevel >= 2250 and MyLevel <= 2299 then
               Ms = "Beast Pirate [Lv. 2250]"
               CFrameQuest = CFrame.new(558.123962, 75.4188766, -2156.09204, -1, 0, 0, 0, 1, 0, 0, 0, -1)
               NameMon = "Beast Pirate"
               CFrameMon = CFrame.new(558.123962, 175.4188766, -2156.09204)
             elseif MyLevel >= 2300 and MyLevel <= 2349 then
               Ms = "Beast Pirate [Lv. 2300]"
               CFrameQuest = CFrame.new(416.176941, 75.386673, -5425.97754, -1.1920929e-07, 0, 1.00000012, 0, 1, 0, -1.00000012, 0, -1.1920929e-07)
               NameMon = "Beast Pirate"
               CFrameMon = CFrame.new(416.176941, 175.386673, -5425.97754)
             elseif MyLevel >= 2350 and MyLevel <= 2399 then
               Ms = "Snake Man [Lv. 2350]"
               CFrameQuest = CFrame.new(88.140152, 75.3936996, -5321.16357, -0.023422122, 0, -0.99972564, 0, 1, 0, 0.99972564, 0, -0.023422122)
               NameMon = "Snake Man"
               CFrameMon = CFrame.new(88.140152, 175.3936996, -5321.16357)
             elseif MyLevel >= 2400 and MyLevel <= 2449 then
               Ms = "Bandit Beast Pirate [Lv. 2400]"
               CFrameQuest = CFrame.new(-2120.31909, 74.9218903, -4906.35107, -1, 0, 0, 0, 1, 0, 0, 0, -1)
               NameMon = "Bandit Beast Pirate"
               CFrameMon = CFrame.new(-2120.31909, 174.9218903, -4906.35107)
             elseif MyLevel >= 2450 and MyLevel <= 2499 then
               Ms = "Powerful Beast Pirate [Lv. 2450]"
               CFrameQuest = CFrame.new(-2754.46362, 75.4548111, -5289.625, 0.57264179, 0, 0.819805682, 0, 1, 0, -0.819805682, 0, 0.57264179)
               NameMon = "Powerful Beast Pirate"
               CFrameMon = CFrame.new(-2754.46362, 175.4548111, -5289.625, 0.57264179)
             elseif MyLevel >= 2500 and MyLevel <= 2549 then
               Ms = "Violet Samurai [Lv. 2500]"
               CFrameQuest = CFrame.new(-3022.99292, 75.7534866, -4925.86426, 0.901796937, 0, 0.43216005, 0, 1, 0, -0.43216005, 0, 0.901796937)
               NameMon = "Violet Samurai"
               CFrameMon = CFrame.new(-3022.99292, 175.7534866, -4925.86426)
             elseif MyLevel >= 2550 and MyLevel <= 2599 then
               Ms = "Rabbit Man [Lv. 2550]"
               CFrameQuest = CFrame.new(-1037.83777, 75.6733093, -1947.10742, 1, 0, 0, 0, 1, 0, 0, 0, 1)
               NameMon = "Rabbit Man"
               CFrameMon = CFrame.new(-1037.83777, 175.6733093, -1947.10742)
             elseif MyLevel >= 2600 and MyLevel <= 2649 then
               Ms = "Bat Man [Lv. 2600]"
               CFrameQuest = CFrame.new(-2710.16284, 75.4078979, -1561.74146, 0, 0, 1, 0, 1, -0, -1, 0, 0)
               NameMon = "Bat Man"
               CFrameMon = CFrame.new(-2710.16284, 175.4078979, -1561.74146)
             elseif MyLevel >= 2650 and MyLevel <= 2699 then
               Ms = "Kitsune Samurai [Lv. 2650]"
               CFrameQuest = CFrame.new(-2917.12598, 75.457901, -1452.71692, 1, 0, 0, 0, 1, 0, 0, 0, 1)
               NameMon = "Kitsune Samurai"
               CFrameMon = CFrame.new(-2917.12598, 175.457901, -1452.71692)
             elseif MyLevel >= 2700 and MyLevel <= 2749 then
               Ms = "Elite Beast Pirate [Lv. 2700]"
               CFrameQuest = CFrame.new(-1042.13416, 75.4581985, 172.622971, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
               NameMon = "Elite Beast Pirate"
               CFrameMon = CFrame.new(-1042.13416, 175.4581985, 172.622971)
             elseif MyLevel >= 2750 and MyLevel <= 2799 then
               Ms = "Elite Beast Pirate [Lv. 2750]"
               CFrameQuest = CFrame.new(-1051.44336, 75.4359818, -113.772148, -1.1920929e-07, -0, -1.00000012, 0, 1, -0, 1.00000012, 0, -1.1920929e-07)
               NameMon = "Elite Beast Pirate"
               CFrameMon = CFrame.new(-1051.44336, 175.4359818, -113.772148)
             elseif MyLevel >= 2800 and MyLevel <= 2849 then
               Ms = "Bear Man [Lv. 2800]"
               CFrameQuest = CFrame.new(-387.776123, 75.4327545, 280.899261, 1, 0, 0, 0, 1, 0, 0, 0, 1)
               NameMon = "Bear Man"
               CFrameMon = CFrame.new(-387.776123, 175.4327545, 280.899261)
             elseif MyLevel >= 2850 and MyLevel <= 2899 then
               Ms = "Magician [Lv. 2850]"
               CFrameQuest = CFrame.new(-3519.60156, 75.506752, 1201.35449, 1, 0, 0, 0, 1, 0, 0, 0, 1)
               NameMon = "Magician"
               CFrameMon = CFrame.new(-3519.60156, 175.506752, 1201.35449)
             elseif MyLevel >= 2900 and MyLevel <= 2949 then
               Ms = "Pachy Woman [Lv. 2900]"
               CFrameQuest = CFrame.new(-4334.17969, 75.456749, 1914.44507, 0.480083644, -0, -0.877222717, 0, 1, -0, 0.877222717, 0, 0.480083644)
               NameMon = "Pachy Woman"
               CFrameMon = CFrame.new(-4334.17969, 175.456749, 1914.44507)
             elseif MyLevel >= 2950 and MyLevel <= 2999 then
               Ms = "Kappa [Lv. 2950]"
               CFrameQuest = CFrame.new(-1426.53455, 74.8297577, 4112.34961, 0.0880642533, -0, -0.996114731, 0, 1, -0, 0.996114731, 0, 0.0880642533)
               NameMon = "Kappa"
               CFrameMon = CFrame.new(-1426.53455, 174.8297577, 4112.34961)
             elseif MyLevel >= 3000 and MyLevel <= 3024 then
               Ms = "Mammoth Man [Lv. 3000]"
               CFrameQuest = CFrame.new(-4276.69336, 74.254776, 4561.5752, 0.996116102, 0, 0.0880491585, 0, 1, 0, -0.0880491585, 0, 0.996116102)
               NameMon = "Mammoth Man"
               CFrameMon = CFrame.new(-4276.69336, 174.254776, 4561.5752)
             elseif MyLevel >= 3025 and MyLevel <= 3074 then
               Ms = "Skull Pirate [Lv. 3050]"
               CFrameQuest = CFrame.new(-3816.54614, 51.3296509, 9891.29688, -1.1920929e-07, 0, -1.00000012, 0, 1, 0, 1.00000012, 0, -1.1920929e-07)
               NameMon = "Skull Pirate"
               CFrameMon = CFrame.new(-3816.54614, 151.3296509, 9891.29688)
             elseif MyLevel >= 3075 and MyLevel <= 3099 then
               Ms = "Elite Skeleton [Lv. 3100]"
               CFrameQuest = CFrame.new(-3032.25317, 51.5443535, 9854.83691, -1.1920929e-07, 0, 1.00000012, 0, 1, 0, -1.00000012, 0, -1.1920929e-07)
               NameMon = "Elite Skeleton"
               CFrameMon = CFrame.new(-3032.25317, 151.5443535, 9854.83691)
             elseif MyLevel >= 3100 and MyLevel <= 3124 then
               Ms = "Desert Thief [Lv.3125]"
               CFrameQuest = CFrame.new(8847.94238, 14.4670143, 1400.72119, -0.322491169, 0, 0.946572542, 0, 1, 0, -0.946572542, 0, -0.322491169)
               NameMon = "Desert Thief"
               CFrameMon = CFrame.new(8847.94238, 114.4670143, 1400.72119)
             elseif MyLevel >= 3125 and MyLevel <= 3149 then
               Ms = "Anubis [Lv.3150]"
               CFrameQuest = CFrame.new(9141.8457, 14.469614, 1055.01233, -0.894592047, 0, 0.446883589, 0, 1, 0, -0.446883589, 0, -0.894592047)
               NameMon = "Anubis"
               CFrameMon = CFrame.new(9141.8457, 114.469614, 1055.01233)
             elseif MyLevel >= 3150  and MyLevel <= 3174 then
               Ms = "Pharaoh [Lv.3175]"
               CFrameQuest = CFrame.new(9554.38672, 14.4762154, 1545.59363, 0.31220305, 0, 0.950015426, 0, 1, 0, -0.950015426, 0, 0.31220305)
               NameMon = "Pharaoh"
               CFrameMon = CFrame.new(9554.38672, 114.4762154, 1545.59363)
             elseif MyLevel > 3175 then
               Ms = "Flame User [Lv.3200]"
               CFrameQuest = CFrame.new(9857.44727, 14.7451639, 1684.2052, -0.0956259966, 0, 0.995417356, 0, 1, 0, -0.995417356, 0, -0.0956259966)
               NameMon = "Flame User"
               CFrameMon = CFrame.new(9857.44727, 114.7451639, 1684.2052)
             end
         end
     end
   CheckQuest()

   SelectToolWeapon = ""
   function EquipWeapon(ToolSe)
       if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
           local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
           wait()
           game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
       end
   end

   AutoFarms:Toggle("Auto Farm","",false,function(vu)
     if Typeing == "" and vu then
        Flux:Notification("Select Type First","OK")
     else
       _G.AF = vu
       if not game.Players.LocalPlayer.Character.RightLowerArm:FindFirstChild("BusoHaki") then
           game:GetService("Players").LocalPlayer.Character.Services.Client.Armament:FireServer()
       end
     end
   end)
   Typeing = ""
   AutoFarms:Slider("TypeFram","",1,3,3,function(sd)   
     Typeing = sd
 end)
   DistanceMob = 6
   AutoFarms:Slider("DistanceMob","",0,50,6,function(dis)
     DistanceMob = dis
 end)

   Wapon = {}
   for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
       if v:IsA("Tool") then
           table.insert(Wapon ,v.Name)
       end
   end
   for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
       if v:IsA("Tool") then
           table.insert(Wapon, v.Name)
       end
   end
   local SelectWeapona = AutoFarms:Dropdown("Select Weapon",Wapon,function(Value)
       SelectToolWeapon = Value
       SelectToolWeaponOld = Value
   end)
   AutoFarms:Button("Refresh Weapon","",function()
           SelectToolWeapon = ""
           SelectWeapona:Clear()
           Wapon = {}
           for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
              if v:IsA("Tool") then
                 SelectWeapona:Add(v.Name)
              end
           end
           for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
              if v:IsA("Tool") then
                 SelectWeapona:Add(v.Name)
              end
           end
        end)
AutoFarms:Label("AutoFarm-Boss")
function an()
for i, v in pairs(game:GetService("Workspace").Monster:GetDescendants()) do
  if v.Name == BoosSelecta then
     repeat wait()
        local LocalPlayer = game:GetService("Players").LocalPlayer
        local VirtualUser = game:GetService('VirtualUser')
       if v.Humanoid.Health > 0 then
           VirtualUser:CaptureController()
           VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
           if TypeingBoss == 2 then
               game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(90), 0, 0) - Vector3.new(0,0,DistanceBoss,0)
           elseif TypeingBoss == 3 then
               game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(-90), 0, 0) * CFrame.new(0,0,DistanceBoss)
           elseif TypeingBoss == 1 then
               game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,DistanceBoss)
           end
       else
         print("Un")
       end
     until not v.Parent or v.Humanoid.Health <= 0 or _G.AF == false
  end
end
end
TypeingBoss = ""
AutoFarms:Slider("TypeFramBoss","",1,3,3,function(smd)   
  TypeingBoss = smd
end)
AutoFarms:Toggle("AutoFarm-Boss","",false,function(Bossa)
  if TypeingBoss == "" and Bossa then
     Flux:Notification("Select Type First","OK")
  else
  BossFarm = Bossa
  end
end)
DistanceBoss = 6
AutoFarms:Slider("DistanceMob","",0,50,6,function(dis)
  DistanceBoss = dis
end)
spawn(function()
  while wait() do
     if BossFarm then
        an()
     end
  end
end)
spawn(function()
  game:GetService('RunService').Stepped:connect(function()
      if BossFarm == true then
          game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
      end
  end)
end)
Boss = {}
for i,v in pairs(game.Workspace.Monster.Boss:GetChildren()) do
   if v:IsA("Model") then
       table.insert(Boss ,v.Name)
   end
end
for i,v in pairs(game.Workspace.Monster.Boss:GetChildren()) do
   if v:IsA("Model") then
       table.insert(Boss, v.Name)
   end
end
local BoosSelect = AutoFarms:Dropdown("Select Boss",Boss,function(Value)
   BoosSelecta = Value
   SelectToolWeaponOld = Value
end)
AutoFarms:Button("Refresh Boss","",function()
  BoosSelecta = ""
       BoosSelect:Clear()
       Wapon = {}
       for i,v in pairs(game.Workspace.Monster.Boss:GetChildren()) do
          if v:IsA("Model") then
           BoosSelect:Add(v.Name)
          end
       end
       for i,v in pairs(game.Workspace.Monster.Boss:GetChildren()) do
          if v:IsA("Model") then
           BoosSelect:Add(v.Name)
          end
       end
    end)
   local LocalPlayer = game:GetService("Players").LocalPlayer
   local VirtualUser = game:GetService('VirtualUser')
   function autofarm()
       if game:GetService("Players").LocalPlayer.PlayerGui.Quest.QuestBoard.Visible == false then
           pcall(function()
               CheckQuest()
               game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
               game:GetService'VirtualUser':Button1Down(Vector2.new(0.9,0.9))
               game:GetService'VirtualUser':Button1Up(Vector2.new(0.9,0.9))
                   wait(.5)
               for i, v in pairs(game.Players.LocalPlayer.PlayerGui:GetDescendants()) do
                   if v.Name == "Dialogue" then
                       v.Accept.Size = UDim2.new(0, 10000, 0, 10000)
                       v.Accept.Position = UDim2.new(-2, 0, -5, 0)
                       v.Accept.BlackgroundTransparency = 1
                   end
               end
           end)
       elseif game:GetService("Players").LocalPlayer.PlayerGui.Quest.QuestBoard.Visible == true then
         if game:GetService("Workspace").Monster:GetDescendants(Ms) then
            pcall(
               function()
                     for i, v in pairs(game:GetService("Workspace").Monster:GetDescendants()) do
                        if v.Name == Ms then
                           repeat wait()
                             if v.Humanoid.Health > 0 then
                                 VirtualUser:CaptureController()
                                 VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
                                 if Typeing == 2 then
                                     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(90), 0, 0) - Vector3.new(0,DistanceMob,0)
                                 elseif Typeing == 3 then
                                     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(-90), 0, 0) * CFrame.new(0,0,DistanceMob)
                                 elseif Typeing == 1 then
                                     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,DistanceMob)
                                 end
                             else
                               CheckQuest()
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
                             end
                           until not v.Parent or v.Humanoid.Health <= 0 or _G.AF == false
                        end
                     end
               end
            )
         else
         end
        end
   end
   spawn(function()
       game:GetService('RunService').Stepped:connect(function()
           if _G.AF == true then
               game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
           end
       end)
   end)
   spawn(function()
       while wait() do
           if _G.AF then
               autofarm()
           end
       end
   end)
   spawn(function()
       while wait(.1) do
           if _G.AF then
               EquipWeapon(SelectToolWeapon)
           end
       end
   end)
   
   AutoFarms:Label("Auto Farm Setting")
      LockLevelValue = 3250
      OldLevel = game.Players.LocalPlayer.PlayerStats.lvl.Value
      AutoFarms:Slider("Select Level Lock","",1,LockLevelValue,LockLevelValue,function(value)
         LockLevelValue = value
      end)
      AutoFarms:Toggle("Lock Level","",false,function(value)
         LockLevel = value
      end)
      spawn(function()
         while wait(.1) do
            if LockLevel then
               if game.Players.localPlayer.Data.Level.Value >= LockLevelValue then
                  game.Players.localPlayer:Kick("\n Auto Fram Completed Level : "..game.Players.LocalPlayer.PlayerStats.lvl.Value.."\n Old Level : "..OldLevel)
               end
            end
         end
      end)
     spawn(function()
         while wait(.1) do
            if AuctoClick then
               Click()
            end
         end
      end)
   AutoFarms:Label("Auto Farm Setting")

   AutoFarms:Toggle("Auto Skill Z","",false,function(Z)
     SkillZ = Z
 end)

 AutoFarms:Toggle("Auto Skill X","",false,function(X)
     SkillX = X
 end)

 AutoFarms:Toggle("Auto Skill C","",false,function(C)
     SkillC = C
 end)

 AutoFarms:Toggle("Auto Skill V","",false,function(V)
     SkillV = V
 end)

 spawn(function()
     while wait(.1) do
         if SkillZ and _G.AF then
             game:GetService("VirtualInputManager"):SendKeyEvent(true,122,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
             wait(.3)
             game:GetService("VirtualInputManager"):SendKeyEvent(false,122,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
         end
     end
 end)

 spawn(function()
     while wait(.1) do
         if SkillX and _G.AF then
             game:GetService("VirtualInputManager"):SendKeyEvent(true,120,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
             wait(.3)
             game:GetService("VirtualInputManager"):SendKeyEvent(false,120,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
         end
     end
 end)

 spawn(function()
     while wait(.1) do
         if SkillC and _G.AF then
             game:GetService("VirtualInputManager"):SendKeyEvent(true,99	,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
             wait(.3)
             game:GetService("VirtualInputManager"):SendKeyEvent(false,99,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
         end
     end
 end)

 spawn(function()
     while wait(.1) do
         if SkillV and _G.AF then
             game:GetService("VirtualInputManager"):SendKeyEvent(true,118,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
             wait(.3)
             game:GetService("VirtualInputManager"):SendKeyEvent(false,118,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
         end
     end
 end)
   local Up = win:Tab("Auto Stats","http://www.roblox.com/asset/?id=7100881079")

Up1 = false
Up:Toggle("Melee","",false,function(a)
   Up1 = a
end)
Up2 = false
Up:Toggle("Defense","",false,function(h)
   Up2 = h
end)
Up3 = false
Up:Toggle("Sword","",false,function(d)
   Up3 = d
end)
Up4 = false
Up:Toggle("Demomfruit","",false,function(l)
   Up4 = l
end)
spawn(function()
   while wait(.1) do
       if Up1 then
local A_1 = "Melee"
local A_2 = 1
local Event = game:GetService("Players").LocalPlayer.PlayerGui.Stats.Button.StatsFrame.RemoteEvent
Event:FireServer(A_1, A_2)
       end
      if Up2 then
local A_1 = "Defense"
local A_2 = 1
local Event = game:GetService("Players").LocalPlayer.PlayerGui.Stats.Button.StatsFrame.RemoteEvent
Event:FireServer(A_1, A_2)
       end
       if Up3 then
local A_1 = "Sword"
local A_2 = 1
local Event = game:GetService("Players").LocalPlayer.PlayerGui.Stats.Button.StatsFrame.RemoteEvent
Event:FireServer(A_1, A_2)

       end
       if Up4 then
local A_1 = "Devil Fruit"
local A_2 = 1
local Event = game:GetService("Players").LocalPlayer.PlayerGui.Stats.Button.StatsFrame.RemoteEvent
Event:FireServer(A_1, A_2)

       end
   end
end)
function isnil(thing)
  return (thing == nil)
end
local function round(n)
  return math.floor(tonumber(n) + 0.5)
end
Number = math.random(1, 1000000)
function UpdatePlayerChams()
  for i,v in pairs(game:GetService'Players':GetChildren()) do
     pcall(function()
           if not isnil(v.Character) then
              if ESPPlayer then
                 if not isnil(v.Character.Head) and not v.Character.Head:FindFirstChild('NameEsp'..Number) then
                 local bill = Instance.new('BillboardGui',v.Character.Head)
                 bill.Name = 'NameEsp'..Number
                 bill.ExtentsOffset = Vector3.new(0, 1, 0)
                 bill.Size = UDim2.new(1,200,1,30)
                 bill.Adornee = v.Character.Head
                 bill.AlwaysOnTop = true
                 local name = Instance.new('TextLabel',bill)
                 name.Font = "GothamBold"
                 name.FontSize = "Size14"
                 name.TextWrapped = true
                 name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
                 name.Size = UDim2.new(1,0,1,0)
                 name.TextYAlignment = 'Top'
                 name.BackgroundTransparency = 1
                 name.TextStrokeTransparency = 0.5
                 if v.Team == game.Players.LocalPlayer.Team then
                       name.TextColor3 = Color3.fromRGB(255, 35, 45)
                 else
                       name.TextColor3 = Color3.fromRGB(255, 35, 45)
                 end
                 else
                       v.Character.Head['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
                 end
              else
                 if v.Character.Head:FindFirstChild('NameEsp'..Number) then
                 v.Character.Head:FindFirstChild('NameEsp'..Number):Destroy()
                 end
              end
           end
     end)
  end
end
function UpdateDevilChams()
  for i,v in pairs(game.Workspace:GetChildren()) do
     pcall(function()
           if DevilFruitESP then
              if string.find(v.Name, "Fruit") then
                 if not v.Handle:FindFirstChild('NameEsp'..Number) then
                       local bill = Instance.new('BillboardGui',v.Handle)
                       bill.Name = 'NameEsp'..Number
                       bill.ExtentsOffset = Vector3.new(0, 1, 0)
                       bill.Size = UDim2.new(1,200,1,30)
                       bill.Adornee = v.Handle
                       bill.AlwaysOnTop = true
                       local name = Instance.new('TextLabel',bill)
                       name.Font = "GothamBold"
                       name.FontSize = "Size14"
                       name.TextWrapped = true
                       name.Size = UDim2.new(1,0,1,0)
                       name.TextYAlignment = 'Top'
                       name.BackgroundTransparency = 1
                       name.TextStrokeTransparency = 0.5
                       name.TextColor3 = Color3.fromRGB(255, 35, 45)
                       name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
                 else
                       v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
                 end
              end
           else
              if v.Handle:FindFirstChild('NameEsp'..Number) then
                 v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
              end
           end
     end)
  end
end
function UpdateFlowerChams()
  for i,v in pairs(game.Workspace:GetChildren()) do
     pcall(function()
           if v.Name == "Flower2" or v.Name == "Flower1" then
              if FlowerESP then
                 if not v:FindFirstChild('NameEsp'..Number) then
                       local bill = Instance.new('BillboardGui',v)
                       bill.Name = 'NameEsp'..Number
                       bill.ExtentsOffset = Vector3.new(0, 1, 0)
                       bill.Size = UDim2.new(1,200,1,30)
                       bill.Adornee = v
                       bill.AlwaysOnTop = true
                       local name = Instance.new('TextLabel',bill)
                       name.Font = "GothamBold"
                       name.FontSize = "Size14"
                       name.TextWrapped = true
                       name.Size = UDim2.new(1,0,1,0)
                       name.TextYAlignment = 'Top'
                       name.BackgroundTransparency = 1
                       name.TextStrokeTransparency = 0.5
                       name.TextColor3 = Color3.fromRGB(255, 0, 0)
                       if v.Name == "Flower1" then
                          name.Text = ("Blue Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                          name.TextColor3 = ASDz
                       end
                       if v.Name == "Flower2" then
                          name.Text = ("Red Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                          name.TextColor3 = ASDz
                       end
                 else
                       v['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                 end
              else
                 if v:FindFirstChild('NameEsp'..Number) then
                 v:FindFirstChild('NameEsp'..Number):Destroy()
                 end
              end
           end
     end)
  end
end
local Ra = win:Tab("Raid-Esp","http://www.roblox.com/asset/?id=7100202580")
if OldWorld then
  Ra:Button("TeleportRaid","",function()
     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1,1,1)
  end)
elseif newworld then
  Ra:Button("TeleportRaid","",function()
     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1559.97485, 677.027893, -2822.86304, 0, 0, 1, 0, 1, -0, -1, 0, 0)
  end)
end
Ra:Toggle("ESP Player","",false,function(a)
  ESPPlayer = a
  while ESPPlayer do wait()
     UpdatePlayerChams()
  end
end)
Ra:Toggle("ESP Devil Fruit","",false,function(a)
  DevilFruitESP = a
  while DevilFruitESP do wait()
     UpdateDevilChams()
  end
end)
local Te = win:Tab("Teleport","http://www.roblox.com/asset/?id=7100840693")
 Te:Toggle("Click = TP","",false,function(vu)
    CTRL = vu
 end)
 local Plr = game:GetService("Players").LocalPlayer
 local Mouse = Plr:GetMouse()
 Mouse.Button1Down:connect(
    function()
       if not Mouse.Target then
          return
       end
       if CTRL then
          Plr.Character:MoveTo(Mouse.Hit.p)
       end
    end
 )
local Player = game.Players.LocalPlayer.Character.HumanoidRootPart
if OldWorld then
  Te:Button("Level Quest","",function()
     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
 end)
Te:Button("First Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2154.54956, 45.8827972, -1721.71594, 0.64414835, -0, -0.764900565, 0, 1, -0, 0.764900565, 0, 0.64414835)
end)
Te:Button("Stone Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(9672.47754, -1.31569958, -3748.64917, -0.484826207, 0, 0.874610603, 0, 1, 0, -0.874610603, 0, -0.484826207)
end)
Te:Button("War Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(8549.06934, 46.4148483, 1399.4314, -0.0896954536, 0, -0.995969236, 0, 1, 0, 0.995969236, 0, -0.0896954536)
end)
Te:Button("Lobby Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(4193.4541, 17.4079437, 6104.90039, 0.0661337376, -0, -0.997810781, 0, 1, -0, 0.997810781, 0, 0.0661337376)
end)
Te:Button("Shark Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(3904.56201, 7.42724943, 3170.61841, 0.819155693, -0, -0.573571265, 0, 1, -0, 0.573571265, 0, 0.819155693)
end)
Te:Button("Snow Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2850.79517, 14.6617012, 1339.95374, 0.173624337, -0, -0.984811902, 0, 1, -0, 0.984811902, 0, 0.173624337)
end)
Te:Button("Sky Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1074.1532, 228.37265, 4521.84717, -0.975334406, 0, -0.220732689, 0, 1, 0, 0.220732689, 0, -0.975334406)
end)
Te:Button("Buble Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(8189.104, 8.43679619, 5386.99658, 0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, 0.374604106)
end)
Te:Button("Desret Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1499.24585, 10.5296488, 3447.84814, 0.422592998, 0, 0.906319618, 0, 1, 0, -0.906319618, 0, 0.422592998)
end)
Te:Button("Marine Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1626.43896, 36.5390015, 1155.34204, -0.913549781, 0, 0.406727046, 0, 1, 0, -0.406727046, 0, -0.913549781)
end)
Te:Button("Fish Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2877.18701, 41.4635086, 13955.7988, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
end)
Te:Button("Chef Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-27.3069839, 96.2180405, 83.7015533, 0.469467044, 0, 0.882950008, 0, 1, 0, -0.882950008, 0, 0.469467044)
end)
Te:Button("Zombie Island","",function()
  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1036.49768, 46.0034332, 8549.59082, 2.98023224e-06, -0.522269726, -0.852780342, -1, -3.09944153e-06, -1.69873238e-06, -1.69873238e-06, 0.852780342, -0.522269726)
end) 
elseif newworld then
   Te:Button("Level Quest","",function()
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
   end)
   Te:Button("SeaBeast","",function()
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.SeaMonster.SeaBeast.HumanoidRootPart.CFrame

   end)
   Te:Button("First Spawn","",function()
     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1893.71594, 69.1028595, -2088.2251, 0, 0, 1, 0, 1, -0, -1, 0, 0)
       end) 
   Te:Button("Pick Color Dragon","",function()
     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1335.90088, 72.3622894, -2206.30078, 0, 0, 1, 0, 1, -0, -1, 0, 0)
    end) 
    Te:Button("SpawnFruit","",function()
     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2289.4353, 71.830513, -1821.31189, 0, 0, 1, 0, 1, -0, -1, 0, 0)
        end) 
        Te:Button("King Samurai","",function()
           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3727.19385, 514.627136, -1411.06958, 0, 0, -1, 0, 1, 0, 1, 0, 0)
            end) 
            Te:Button("Kaido","",function()
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3441.12305, 14.4575653, 10826.7402, 1, 0, 0, 0, 1, 0, 0, 0, 1)
                end) 
                Te:Button("Desert Island","",function()
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(8314.96973, 7.00850534, 957.432434, 0.934183955, -0, -0.356791854, 0, 1, -0, 0.356791854, 0, 0.934183955)
                    end) 
end
local Mi = win:Tab("Misc","http://www.roblox.com/asset/?id=7100794798")

Mi:Slider("WallkSpeed","",0,100,100,function(walk)
   game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = walk
end)
Mi:Slider("JumpPower","",16,500,500,function(Jump)
   game.Players.LocalPlayer.Character.Humanoid.JumpPower = Jump
end)
Mi:Toggle("Semi-GodMode","",false,function(Mode)
  GodMode = Mode 
end)
local Player   = game:GetService('Players').LocalPlayer

local function CheckRig()
   if Player.Character then
       local Humanoid = Player.Character:WaitForChild('Humanoid')
       if Humanoid.RigType == Enum.HumanoidRigType.R15 then
           return 'R15'
       else
           return 'R6'
       end
   end
end

local function InitiateInvis()
   local Character = Player.Character
   local StoredCF = Character.PrimaryPart.CFrame

   if CheckRig() == 'R6' then
       local Clone = Character.HumanoidRootPart:Clone()
       Character.HumanoidRootPart:Destroy()
       Clone.Parent = Character
   else
       local Clone = Character.LowerTorso.Root:Clone()
       Character.LowerTorso.Root:Destroy()
       Clone.Parent = Character.LowerTorso
   end

end
Mi:Dropdown("Water Walk",{"Water Walk","No Water Walk"},function(walk)
  if walk == "Water Walk" then
     for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do
        if v.Name == "Ocean" then
       
       box = Instance.new('Part',workspace)
       box.Transparency = 1
       box.Anchored = true
       box.CanCollide = true
       box.Size = Vector3.new(100000,0,100000)
       box.CFrame = v.CFrame
       end
       end
     elseif walk == "No Water Walk" then
        game.Workspace.Part:Destroy()
  end   
end)

if OldWorld then
  Mi:Button("Invisible Your Self","",function()
       local cframeold = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(0,0,0)
       wait(1)
       InitiateInvis()
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cframeold
   end)
elseif newworld then
  Mi:Button("Invisible Your Self","",function()
       local cframeold = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(868.589355, 202.844162, -4921.85693, -1, 0, 0, 0, -1, 0, 0, 0, 1)
       wait(1)
       InitiateInvis()
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cframeold
   end)
   
end
spawn(function()
   while wait(.1) do
       if GodMode then
           pcall(function()
               game:GetService("Players").LocalPlayer.Character.KenHaki:Destroy()
               game:GetService("Players").LocalPlayer.Backpack.SwimScript.RemoteEvent:Destroy()
           end)
       end
   end
end)
Mi:Toggle("Noclip","",false,function(k)
   bvlop = k
end)
spawn(function()
   while wait() do
       if bvlop then
           game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
       end
   end
end)
if OldWorld then
Mi:Button("CoffinBoat Unlock","",function()
local A_1 = "CoffinBoat"
local A_2 = "ShipA"
local Event = game:GetService("ReplicatedStorage").Remotes.Events.Ship
Event:FireServer(A_1, A_2)
   wait(1)
Player.CFrame = CFrame.new(1870.33423, 2.44216585, -1461.14185, -0.627872348, 0, 0.778316259, 0, 1, 0, -0.778316259, 0, -0.627872348)
end)
end
if newworld then
   Mi:Button("CoffinBoat Unlock","",function()
local A_1 = "CoffinBoat"
local A_2 = "ShipA"
local Event = game:GetService("ReplicatedStorage").Remotes.Events.Ship
Event:FireServer(A_1, A_2)
   wait(1)
Player.CFrame = CFrame.new(2058.26807, -0.666899681, -2098.13208, -0.139119372, 0.00129486993, -0.990274787, -0.00105064479, 0.999998391, 0.00145518489, 0.990275085, 0.0012428714, -0.139117792)
   end)
end
Mi:Button("Collect Fruit","",function()
   for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
       if v.ClassName == "Tool" then
          v.Handle.CFrame = Player.CFrame    
       end
   end
end)
Mi:Button("Inf Geppo","",function()
   game.Players.LocalPlayer.Backpack.GeppoNew.cds.Value = 10000
end) 
Mi:Button("Geppo No CoolDown","",function()
  local a;

a = hookfunction(getrenv().wait, function(x)
   if tostring(getfenv(2).script) == "GeppoNew" then
       return game:GetService("RunService").RenderStepped:wait()
   end
   return a(x)
end)
end)          
Mi:Button("Dash No CoolDown","",function()
  local a;

a = hookfunction(getrenv().wait, function(x)
   if tostring(getfenv(2).script) == "Dash" then
       return game:GetService("RunService").RenderStepped:wait()
   end
   return a(x)
end)
end) 
Mi:Button("Server Hop","",function()
    local PlaceID = game.PlaceId
    local AllIDs = {}
    local foundAnything = ""
    local actualHour = os.date("!*t").hour
    local Deleted = false
    function TPReturner()
       local Site;
       if foundAnything == "" then
          Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
       else
          Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
       end
       local ID = ""
       if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
          foundAnything = Site.nextPageCursor
       end
       local num = 0;
       for i,v in pairs(Site.data) do
          local Possible = true
          ID = tostring(v.id)
          if tonumber(v.maxPlayers) > tonumber(v.playing) then
             for _,Existing in pairs(AllIDs) do
                if num ~= 0 then
                      if ID == tostring(Existing) then
                         Possible = false
                      end
                else
                      if tonumber(actualHour) ~= tonumber(Existing) then
                         local delFile = pcall(function()
                            -- delfile("NotSameServers.json")
                            AllIDs = {}
                            table.insert(AllIDs, actualHour)
                         end)
                      end
                end
                num = num + 1
             end
             if Possible == true then
                table.insert(AllIDs, ID)
                wait()
                pcall(function()
                      -- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
                      wait()
                      game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
                end)
                wait(4)
             end
          end
       end
    end
    function Teleport()
       while wait() do
          pcall(function()
             TPReturner()
             if foundAnything ~= "" then
                TPReturner()
             end
          end)
       end
    end
    Teleport()
 end)
 local a = win:Tab("DF-Sniper","http://www.roblox.com/asset/?id=7100923244")
 Fruit = ""
 a:Dropdown("SelectDF-Sinper",{"BombBomb","AlloAllo","BarrierBarrier","DarkDark","BuddhaBuddha","DragonDragon","GasGas","GumGum","HumanHuman","IceIce","LoveLove","LightLight","MagmaMagma","OpOp","FlameFlame","GiraffeGiraffe","GravityGravity","LeopardLeopard","PawPaw","PhoenixPhoenix","QuakeQuake","RumbleRumble","SandSand","ShadowShadow","SnowSnow","SpinSpin","SpinoSpino","StringString","VenomVenom","WolfWolf"},function(a)
  Fruit = a
 end)
 a:Toggle("Buy Sniper","",false,function(f)
     if Fruit == "" and f then
        Flux:Notification("Select Fruit First","OK")
     else
        Buy = f
     end
 end)
 spawn(function()
  while wait(.1) do
     if Buy then
        local args = {
           [1] = Fruit,
           [2] = true,
       }
       
       game:GetService("ReplicatedStorage").Remotes.Functions.dfbeli:InvokeServer(unpack(args))
     end
  end
 end)
local king = win:Tab("SeaKing","http://www.roblox.com/asset/?id=7100202580")
  king:Toggle("Auto-SeaKing","",false,function(t)
    _G.SeaKing = t
  end)
  
  spawn(function()
  while game:GetService("RunService").RenderStepped:wait() do
    if _G.SeaKing then
      pcall(function()
        equip()
          for i,v in pairs(game:GetService("Workspace").SeaMonster:GetDescendants()) do
          if game:GetService("Workspace").SeaMonster:FindFirstChild("SeaKing") then
          if v.Name == "SeaKing" then
          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(90), 0, 0) - Vector3.new(0,23,0)
          game:GetService'VirtualUser':CaptureController()
          local tool = _G.SelectWepon
          wait(.4)
          game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool) 
game:GetService'VirtualUser':Button1Down(Vector2.new(31, 123))
game:GetService'VirtualUser':CaptureController()
game:GetService'VirtualUser':Button1Down(Vector2.new(2347, 254))
          if v.Humanoid.Health <= 0 then
          if game:GetService("Workspace").Island:FindFirstChild("Legacy Island1") then
          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Island:FindFirstChild("Legacy Island1").ChestSpawner.CFrame
          elseif game:GetService("Workspace").Island:FindFirstChild("Legacy Island2") then
          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Island:FindFirstChild("Legacy Island2").ChestSpawner.CFrame
          elseif game:GetService("Workspace").Island:FindFirstChild("Legacy Island3") then
          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Island:FindFirstChild("Legacy Island3").ChestSpawner.CFrame
          elseif game:GetService("Workspace").Island:FindFirstChild("Legacy Island4") then
          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Island:FindFirstChild("Legacy Island4").ChestSpawner.CFrame
        end
        end
        end
        end
      end
  end)
  end
  end
  end)
  
  game:GetService("RunService").RenderStepped:Connect(function()
    if _G.SeaKing then
    game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
    end
  end)
  
  
  king:Toggle("ServerHop-SeaKing","",false,function(t)
    _G.SeverHopSea = t
  end)
  
  spawn(function()
    while wait() do
      if _G.SeverHopSea then
        if not game:GetService("Workspace").SeaMonster:FindFirstChild("SeaKing") then
          local PlaceID = game.PlaceId
              local AllIDs = {}
              local foundAnything = ""
              local actualHour = os.date("!*t").hour
              local Deleted = false
              function TPReturner()
                 local Site;
                 if foundAnything == "" then
                    Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
                 else
                    Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
                 end
                 local ID = ""
                 if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
                    foundAnything = Site.nextPageCursor
                 end
                 local num = 0;
                 for i,v in pairs(Site.data) do
                    local Possible = true
                    ID = tostring(v.id)
                    if tonumber(v.maxPlayers) > tonumber(v.playing) then
                       for _,Existing in pairs(AllIDs) do
                          if num ~= 0 then
                                if ID == tostring(Existing) then
                                   Possible = false
                                end
                          else
                                if tonumber(actualHour) ~= tonumber(Existing) then
                                   local delFile = pcall(function()
                                      -- delfile("NotSameServers.json")
                                      AllIDs = {}
                                      table.insert(AllIDs, actualHour)
                                   end)
                                end
                          end
                          num = num + 1
                       end
                       if Possible == true then
                          table.insert(AllIDs, ID)
                          wait()
                          pcall(function()
                                -- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
                                wait()
                                game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
                          end)
                          wait(4)
                       end
                    end
                 end
              end
              function Teleport()
                 while wait() do
                    pcall(function()
                       TPReturner()
                       if foundAnything ~= "" then
                          TPReturner()
                       end
                    end)
                 end
              end
              Teleport()
            end
          end
        end
        
        
  end)
  
end
if placeId == 2753915549 then
 oldword = true
elseif placeId == 4442272183 then
 NewWorld = true
 elseif placeId == 7449423635 then
   Third = true
end
if oldword or NewWorld or Third then
  local Flux = {RainbowColorValue = 0, HueSelectionPosition = 0}
  local PresetColor = Color3.fromRGB(66, 134, 255)
  local UserInputService = game:GetService("UserInputService")
  local TweenService = game:GetService("TweenService")
  local RunService = game:GetService("RunService")
  local LocalPlayer = game:GetService("Players").LocalPlayer
  local Mouse = LocalPlayer:GetMouse()
  local CloseBind = Enum.KeyCode.RightControl
  
  local FluxLib = Instance.new("ScreenGui")
  FluxLib.Name = "FluxLib"
  FluxLib.Parent = game.CoreGui
  FluxLib.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
  
  coroutine.wrap(
     function()
        while wait() do
           Flux.RainbowColorValue = Flux.RainbowColorValue + 1 / 255
           Flux.HueSelectionPosition = Flux.HueSelectionPosition + 1
  
           if Flux.RainbowColorValue >= 1 then
              Flux.RainbowColorValue = 0
           end
  
           if Flux.HueSelectionPosition == 80 then
              Flux.HueSelectionPosition = 0
           end
        end
     end
  )()
  
  local function MakeDraggable(topbarobject, object)
     local Dragging = nil
     local DragInput = nil
     local DragStart = nil
     local StartPosition = nil
  
     local function Update(input)
        local Delta = input.Position - DragStart
        local pos =
              UDim2.new(
              StartPosition.X.Scale,
              StartPosition.X.Offset + Delta.X,
              StartPosition.Y.Scale,
              StartPosition.Y.Offset + Delta.Y
        )
        local Tween = TweenService:Create(object, TweenInfo.new(0.2), {Position = pos})
        Tween:Play()
     end
  
     topbarobject.InputBegan:Connect(
        function(input)
              if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                 Dragging = true
                 DragStart = input.Position
                 StartPosition = object.Position
  
                 input.Changed:Connect(
                    function()
                          if input.UserInputState == Enum.UserInputState.End then
                             Dragging = false
                          end
                    end
                 )
              end
        end
     )
  
     topbarobject.InputChanged:Connect(
        function(input)
              if
                 input.UserInputType == Enum.UserInputType.MouseMovement or
                    input.UserInputType == Enum.UserInputType.Touch
              then
                 DragInput = input
              end
        end
     )
  
     UserInputService.InputChanged:Connect(
        function(input)
              if input == DragInput and Dragging then
                 Update(input)
              end
        end
     )
  end
  
  
  
  function Flux:Window(text, bottom,mainclr,toclose)
     CloseBind = toclose or Enum.KeyCode.RightControl
     PresetColor = mainclr or Color3.fromRGB(255, 35, 45)
     local fs = false
     local MainFrame = Instance.new("Frame")
     local MainCorner = Instance.new("UICorner")
     local LeftFrame = Instance.new("Frame")
     local LeftCorner = Instance.new("UICorner")
     local GlowTabHolder = Instance.new("ImageLabel")
     local Title = Instance.new("TextLabel")
     local BottomText = Instance.new("TextLabel")
     local TabHold = Instance.new("Frame")
     local TabLayout = Instance.new("UIListLayout")
     local Drag = Instance.new("Frame")
     local ContainerFolder = Instance.new("Folder")
  
     MainFrame.Name = "MainFrame"
     MainFrame.Parent = FluxLib
     MainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
     MainFrame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
     MainFrame.ClipsDescendants = true
     MainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
     MainFrame.Size = UDim2.new(0, 0, 0, 0)
  
     MainCorner.CornerRadius = UDim.new(0, 5)
     MainCorner.Name = "MainCorner"
     MainCorner.Parent = MainFrame
  
     LeftFrame.Name = "LeftFrame"
     LeftFrame.Parent = MainFrame
     LeftFrame.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
     LeftFrame.Size = UDim2.new(0, 205, 0, 484)
  
     LeftCorner.CornerRadius = UDim.new(0, 5)
     LeftCorner.Name = "LeftCorner"
     LeftCorner.Parent = LeftFrame
  
     GlowTabHolder.Name = "GlowTabHolder"
     GlowTabHolder.Parent = LeftFrame
     GlowTabHolder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     GlowTabHolder.BackgroundTransparency = 1.000
     GlowTabHolder.BorderSizePixel = 0
     GlowTabHolder.Position = UDim2.new(0, -15, 0, -15)
     GlowTabHolder.Size = UDim2.new(1, 30, 1, 30)
     GlowTabHolder.ZIndex = 0
     GlowTabHolder.Image = "rbxassetid://4996891970"
     GlowTabHolder.ImageColor3 = Color3.fromRGB(15, 15, 15)
     GlowTabHolder.ScaleType = Enum.ScaleType.Slice
     GlowTabHolder.SliceCenter = Rect.new(20, 20, 280, 280)
  
     Title.Name = "Title"
     Title.Parent = LeftFrame
     Title.BackgroundColor3 = Color3.fromRGB(255, 0, 11)
     Title.BackgroundTransparency = 1.000
     Title.Position = UDim2.new(0.097560972, 0, 0.0475206636, 0)
     Title.Size = UDim2.new(0, 111, 0, 34)
     Title.Font = Enum.Font.GothamBold
     Title.Text = text
     Title.TextColor3 = Color3.fromRGB(209, 34, 34  )
     Title.TextSize = 25.000
     Title.TextXAlignment = Enum.TextXAlignment.Left
  
     BottomText.Name = "BottomText"
     BottomText.Parent = LeftFrame
     BottomText.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     BottomText.BackgroundTransparency = 1.000
     BottomText.Position = UDim2.new(0.097560972, 0, 0.0889999792, 0)
     BottomText.Size = UDim2.new(0, 113, 0, 28)
     BottomText.Font = Enum.Font.Gotham
     BottomText.Text = bottom
     BottomText.TextColor3 = Color3.fromRGB(255, 255, 255)
     BottomText.TextSize = 14.000
     BottomText.TextTransparency = 0.300
     BottomText.TextXAlignment = Enum.TextXAlignment.Left
  
     TabHold.Name = "TabHold"
     TabHold.Parent = LeftFrame
     TabHold.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     TabHold.BackgroundTransparency = 1.000
     TabHold.Position = UDim2.new(0, 0, 0.167355374, 0)
     TabHold.Size = UDim2.new(0, 205, 0, 403)
  
     TabLayout.Name = "TabLayout"
     TabLayout.Parent = TabHold
     TabLayout.SortOrder = Enum.SortOrder.LayoutOrder
     TabLayout.Padding = UDim.new(0, 3)
  
     Drag.Name = "Drag"
     Drag.Parent = MainFrame
     Drag.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     Drag.BackgroundTransparency = 1.000
     Drag.Position = UDim2.new(0.290368259, 0, 0, 0)
     Drag.Size = UDim2.new(0, 501, 0, 23)
  
     ContainerFolder.Name = "ContainerFolder"
     ContainerFolder.Parent = MainFrame
     
     MakeDraggable(Drag,MainFrame)
     MakeDraggable(LeftFrame,MainFrame)
     MainFrame:TweenSize(UDim2.new(0, 706, 0, 484), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
     
     local uitoggled = false
     UserInputService.InputBegan:Connect(
        function(io, p)
           if io.KeyCode == CloseBind then
              if uitoggled == false then
                 MainFrame:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 uitoggled = true
                 wait(.5)
                 FluxLib.Enabled = false
              else
                 MainFrame:TweenSize(UDim2.new(0, 706, 0, 484), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 FluxLib.Enabled = true
                 uitoggled = false
              end
           end
        end
     )
     
     function Flux:Notification(desc,buttontitle)
        for i, v in next, MainFrame:GetChildren() do
           if v.Name == "NotificationBase" then
              v:Destroy()
           end
        end
        local NotificationBase = Instance.new("TextButton")
        local NotificationBaseCorner = Instance.new("UICorner")
        local NotificationFrame = Instance.new("Frame")
        local NotificationFrameCorner = Instance.new("UICorner")
        local NotificationFrameGlow = Instance.new("ImageLabel")
        local NotificationTitle = Instance.new("TextLabel")
        local CloseBtn = Instance.new("TextButton")
        local CloseBtnCorner = Instance.new("UICorner")
        local NotificationDesc = Instance.new("TextLabel")
  
        NotificationBase.Name = "NotificationBase"
        NotificationBase.Parent = MainFrame
        NotificationBase.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        NotificationBase.BackgroundTransparency = 1
        NotificationBase.Size = UDim2.new(0, 706, 0, 484)
        NotificationBase.AutoButtonColor = false
        NotificationBase.Font = Enum.Font.SourceSans
        NotificationBase.Text = ""
        NotificationBase.TextColor3 = Color3.fromRGB(0, 0, 0)
        NotificationBase.TextSize = 14.000
        NotificationBase.Visible = true
  
        NotificationBaseCorner.CornerRadius = UDim.new(0, 5)
        NotificationBaseCorner.Name = "NotificationBaseCorner"
        NotificationBaseCorner.Parent = NotificationBase
  
        NotificationFrame.Name = "NotificationFrame"
        NotificationFrame.Parent = NotificationBase
        NotificationFrame.AnchorPoint = Vector2.new(0.5, 0.5)
        NotificationFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        NotificationFrame.ClipsDescendants = true
        NotificationFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
        NotificationFrame.Size = UDim2.new(0, 0, 0, 0)
  
        NotificationFrameCorner.CornerRadius = UDim.new(0, 5)
        NotificationFrameCorner.Name = "NotificationFrameCorner"
        NotificationFrameCorner.Parent = NotificationFrame
  
        NotificationFrameGlow.Name = "NotificationFrameGlow"
        NotificationFrameGlow.Parent = NotificationFrame
        NotificationFrameGlow.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        NotificationFrameGlow.BackgroundTransparency = 1.000
        NotificationFrameGlow.BorderSizePixel = 0
        NotificationFrameGlow.Position = UDim2.new(0, -15, 0, -15)
        NotificationFrameGlow.Size = UDim2.new(1, 30, 1, 30)
        NotificationFrameGlow.ZIndex = 0
        NotificationFrameGlow.Image = "rbxassetid://4996891970"
        NotificationFrameGlow.ImageColor3 = Color3.fromRGB(15, 15, 15)
        NotificationFrameGlow.ScaleType = Enum.ScaleType.Slice
        NotificationFrameGlow.SliceCenter = Rect.new(20, 20, 280, 280)
  
        NotificationTitle.Name = "NotificationTitle"
        NotificationTitle.Parent = NotificationFrame
        NotificationTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        NotificationTitle.BackgroundTransparency = 1.000
        NotificationTitle.Position = UDim2.new(0.0400609747, 0, 0.0761325806, 0)
        NotificationTitle.Size = UDim2.new(0, 111, 0, 34)
        NotificationTitle.Font = Enum.Font.GothamBold
        NotificationTitle.Text = Title.Text .. " | NOTIFICATION"
        NotificationTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
        NotificationTitle.TextSize = 24.000
        NotificationTitle.TextXAlignment = Enum.TextXAlignment.Left
        NotificationTitle.TextTransparency = 1
  
        CloseBtn.Name = "CloseBtn"
        CloseBtn.Parent = NotificationFrame
        CloseBtn.BackgroundColor3 = Color3.fromRGB(21, 21, 21)
        CloseBtn.ClipsDescendants = true
        CloseBtn.Position = UDim2.new(0.0403124988, 0, 0.720855951, 0)
        CloseBtn.Size = UDim2.new(0, 366, 0, 43)
        CloseBtn.AutoButtonColor = false
        CloseBtn.Font = Enum.Font.Gotham
        CloseBtn.Text = buttontitle
        CloseBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
        CloseBtn.TextSize = 15.000
        CloseBtn.TextTransparency = 1
        CloseBtn.BackgroundTransparency = 1
  
        CloseBtnCorner.CornerRadius = UDim.new(0, 4)
        CloseBtnCorner.Name = "CloseBtnCorner"
        CloseBtnCorner.Parent = CloseBtn
  
        NotificationDesc.Name = "NotificationDesc"
        NotificationDesc.Parent = NotificationFrame
        NotificationDesc.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        NotificationDesc.BackgroundTransparency = 1.000
        NotificationDesc.Position = UDim2.new(0.112499997, 0, 0.266355127, 0)
        NotificationDesc.Size = UDim2.new(0, 309, 0, 82)
        NotificationDesc.Font = Enum.Font.Gotham
        NotificationDesc.Text = desc
        NotificationDesc.TextColor3 = Color3.fromRGB(255, 255, 255)
        NotificationDesc.TextSize = 15.000
        NotificationDesc.TextWrapped = true
        NotificationDesc.TextTransparency = 1
        
        CloseBtn.MouseEnter:Connect(function()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 0}
           ):Play()
        end)
  
        CloseBtn.MouseLeave:Connect(function()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 0.3}
           ):Play()
        end)
        
        CloseBtn.MouseButton1Click:Connect(function()
           
           TweenService:Create(
              NotificationDesc,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 1}
           ):Play()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 1}
           ):Play()
           TweenService:Create(
              NotificationTitle,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 1}
           ):Play()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {BackgroundTransparency = 1}
           ):Play()
           
           wait(.4)
           CloseBtn.Visible = false
           NotificationFrame:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
  
           wait(.2)
           
           TweenService:Create(
              NotificationBase,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {BackgroundTransparency = 1}
           ):Play()
           
           wait(.2)
           
           NotificationBase.Visible = false
        end)
  
        
        TweenService:Create(
           NotificationBase,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {BackgroundTransparency = 0.550}
        ):Play()
        
        wait(.1)
        
        NotificationFrame:TweenSize(UDim2.new(0, 400, 0, 214), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
        
        wait(.4)
        TweenService:Create(
           NotificationDesc,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {TextTransparency = .3}
        ):Play()
        TweenService:Create(
           CloseBtn,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {TextTransparency = .3}
        ):Play()
        TweenService:Create(
           NotificationTitle,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {TextTransparency = 0}
        ):Play()
        TweenService:Create(
           CloseBtn,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {BackgroundTransparency = 0}
        ):Play()
     end
     local Tabs = {}
     function Tabs:Tab(text,ico)
        local Tab = Instance.new("TextButton")
        local TabIcon = Instance.new("ImageLabel")
        local TabTitle = Instance.new("TextLabel")
        

        Tab.Name = "Tab"
        Tab.Parent = TabHold
        Tab.BackgroundColor3 = PresetColor
        Tab.BorderSizePixel = 0
        Tab.Size = UDim2.new(0, 205, 0, 40)
        Tab.AutoButtonColor = false
        Tab.Font = Enum.Font.SourceSans
        Tab.Text = ""
        Tab.TextColor3 = Color3.fromRGB(0, 0, 0)
        Tab.TextSize = 14.000
        Tab.BackgroundTransparency = 1
  
        TabIcon.Name = "TabIcon"
        TabIcon.Parent = Tab
        TabIcon.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        TabIcon.BackgroundTransparency = 1.000
        TabIcon.Position = UDim2.new(0.0634146333, 0, 0.25, 0)
        TabIcon.Size = UDim2.new(0, 20, 0, 20)
        TabIcon.Image = ico
        TabIcon.ImageTransparency = .3
  
        TabTitle.Name = "TabTitle"
        TabTitle.Parent = Tab
        TabTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        TabTitle.BackgroundTransparency = 1.000
        TabTitle.Position = UDim2.new(0.1902439, 0, 0.25, 0)
        TabTitle.Size = UDim2.new(0, 113, 0, 19)
        TabTitle.Font = Enum.Font.Gotham
        TabTitle.Text = text
        TabTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
        TabTitle.TextSize = 15.000
        TabTitle.TextXAlignment = Enum.TextXAlignment.Left
        TabTitle.TextTransparency = .3
        
        local Container = Instance.new("ScrollingFrame")
        local ContainerLayout = Instance.new("UIListLayout")
  
  
        Container.Name = "Container"
        Container.Parent = ContainerFolder
        Container.Active = true
        Container.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        Container.BackgroundTransparency = 1.000
        Container.BorderSizePixel = 0
        Container.Position = UDim2.new(0.321529746, 0, 0.0475206599, 0)
        Container.Size = UDim2.new(0, 470, 0, 438)
        Container.CanvasSize = UDim2.new(0, 0, 0, 0)
        Container.ScrollBarThickness = 5
        Container.Visible = false
        Container.ScrollBarImageColor3 = Color3.fromRGB(71, 76, 84)
  
        ContainerLayout.Name = "ContainerLayout"
        ContainerLayout.Parent = Container
        ContainerLayout.SortOrder = Enum.SortOrder.LayoutOrder
        ContainerLayout.Padding = UDim.new(0, 15)
        if fs == false then
           fs = true
           TabTitle.TextTransparency = 0
           TabIcon.ImageTransparency = 0
           Tab.BackgroundTransparency = 0
           Container.Visible = true
        end
        
        Tab.MouseButton1Click:Connect(function()
           for i, v in next, ContainerFolder:GetChildren() do
              if v.Name == "Container" then
                 v.Visible = false
              end
              Container.Visible = true
           end
           for i, v in next, TabHold:GetChildren() do
              if v.Name == "Tab" then
                 TweenService:Create(
                    v,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    v.TabIcon,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    v.TabTitle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    Tab,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    TabIcon,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    TabTitle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
              end
           end
        end)
        local ContainerContent = {}
        function ContainerContent:Button(text, desc, callback)
           if desc == "" then
              desc = "There is no description for this button."
           end
           local BtnDescToggled = false
           local Button = Instance.new("TextButton")
           local ButtonCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
  
           Button.Name = "Button"
           Button.Parent = Container
           Button.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Button.ClipsDescendants = true
           Button.Position = UDim2.new(0.370312512, 0, 0.552631557, 0)
           Button.Size = UDim2.new(0, 457, 0, 43)
           Button.AutoButtonColor = false
           Button.Font = Enum.Font.SourceSans
           Button.Text = ""
           Button.TextColor3 = Color3.fromRGB(0, 0, 0)
           Button.TextSize = 14.000
  
           ButtonCorner.CornerRadius = UDim.new(0, 4)
           ButtonCorner.Name = "ButtonCorner"
           ButtonCorner.Parent = Button
  
           Title.Name = "Title"
           Title.Parent = Button
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(255,255,255)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.200942323, 0, 0.785714269, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 1
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Button
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           ArrowIco.ImageTransparency = .3
           
           Button.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
           
           Button.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
           
           Button.MouseButton1Click:Connect(function()
              pcall(callback)
           end)
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if BtnDescToggled == false then
                 Button:TweenSize(UDim2.new(0, 457, 0, 74), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Button:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              BtnDescToggled = not BtnDescToggled
           end)
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Toggle(text, desc,default, callback)
           local ToggleDescToggled = false
           local Toggled = false
           if desc == "" then
              desc = "There is no description for this toggle."
           end
           local Toggle = Instance.new("TextButton")
           local ToggleCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local ToggleFrame = Instance.new("Frame")
           local ToggleFrameCorner = Instance.new("UICorner")
           local ToggleCircle = Instance.new("Frame")
           local ToggleCircleCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
  
           Toggle.Name = "Toggle"
           Toggle.Parent = Container
           Toggle.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Toggle.ClipsDescendants = true
           Toggle.Position = UDim2.new(0.110937506, 0, 0.67653507, 0)
           Toggle.Size = UDim2.new(0, 457, 0, 43)
           Toggle.AutoButtonColor = false
           Toggle.Font = Enum.Font.SourceSans
           Toggle.Text = ""
           Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
           Toggle.TextSize = 14.000
  
           ToggleCorner.CornerRadius = UDim.new(0, 4)
           ToggleCorner.Name = "ToggleCorner"
           ToggleCorner.Parent = Toggle
  
           Title.Name = "Title"
           Title.Parent = Toggle
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           ToggleFrame.Name = "ToggleFrame"
           ToggleFrame.Parent = Circle
           ToggleFrame.BackgroundColor3 = Color3.fromRGB(226, 227, 227)
           ToggleFrame.Position = UDim2.new(33.0856934, 0, 0, 0)
           ToggleFrame.Size = UDim2.new(0, 27, 0, 11)
  
           ToggleFrameCorner.Name = "ToggleFrameCorner"
           ToggleFrameCorner.Parent = ToggleFrame
  
           ToggleCircle.Name = "ToggleCircle"
           ToggleCircle.Parent = ToggleFrame
           ToggleCircle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ToggleCircle.Position = UDim2.new(0, 0, -0.272727281, 0)
           ToggleCircle.Selectable = true
           ToggleCircle.Size = UDim2.new(0, 17, 0, 17)
  
           ToggleCircleCorner.CornerRadius = UDim.new(2, 8)
           ToggleCircleCorner.Name = "ToggleCircleCorner"
           ToggleCircleCorner.Parent = ToggleCircle
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.200942323, 0, 0.785714269, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 1
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Toggle
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(86, 86, 86)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           ArrowIco.ImageTransparency = .3
           
            Toggle.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           Toggle.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
  
           Toggle.MouseButton1Click:Connect(function()
              if Toggled == false then
                 ToggleCircle:TweenPosition(UDim2.new(0.37, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                 TweenService:Create(
                    ToggleCircle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 =PresetColor}
                 ):Play()
              else
                 ToggleCircle:TweenPosition(UDim2.new(0, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                 TweenService:Create(
                    ToggleCircle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
              end
              Toggled = not Toggled
              pcall(callback, Toggled)
           end)
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if ToggleDescToggled == false then
                 Toggle:TweenSize(UDim2.new(0, 457, 0, 74), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Toggle:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              ToggleDescToggled = not ToggleDescToggled
           end)
           if default == true then
              ToggleCircle:TweenPosition(UDim2.new(0.37, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
              TweenService:Create(
                 ToggleCircle,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {BackgroundColor3 =PresetColor}
              ):Play()
              Toggled = not Toggled
              pcall(callback, Toggled)
           end
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        
        function ContainerContent:Slider(text,desc,min,max,start,callback)
           local SliderFunc = {}
           local SliderDescToggled = false
                          local dragging = false
           if desc == "" then
              desc = "There is no description for this slider."
           end
           local Slider = Instance.new("TextButton")
           local SliderCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local SlideFrame = Instance.new("Frame")
           local CurrentValueFrame = Instance.new("Frame")
           local SlideCircle = Instance.new("ImageButton")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
           local Value = Instance.new("TextLabel")
  
           Slider.Name = "Slider"
           Slider.Parent = Container
           Slider.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Slider.ClipsDescendants = true
           Slider.Position = UDim2.new(0.189062506, 0, 0.648612201, 0)
           Slider.Size = UDim2.new(0, 457, 0, 60)
           Slider.AutoButtonColor = false
           Slider.Font = Enum.Font.SourceSans
           Slider.Text = ""
           Slider.TextColor3 = Color3.fromRGB(0, 0, 0)
           Slider.TextSize = 14.000
  
           SliderCorner.CornerRadius = UDim.new(0, 4)
           SliderCorner.Name = "SliderCorner"
           SliderCorner.Parent = Slider
  
           Title.Name = "Title"
           Title.Parent = Slider
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.201000005, 0, 1.38600004, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 0.300
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           SlideFrame.Name = "SlideFrame"
           SlideFrame.Parent = Title
           SlideFrame.BackgroundColor3 = Color3.fromRGB(235, 234, 235)
           SlideFrame.BorderSizePixel = 0
           SlideFrame.Position = UDim2.new(-0.197140202, 0, 0.986091495, 0)
           SlideFrame.Size = UDim2.new(0, 426, 0, 3)
  
           CurrentValueFrame.Name = "CurrentValueFrame"
           CurrentValueFrame.Parent = SlideFrame
           CurrentValueFrame.BackgroundColor3 = PresetColor
           CurrentValueFrame.BorderSizePixel = 0
           CurrentValueFrame.Size = UDim2.new((start or 0) / max, 0, 0, 3)
  
           SlideCircle.Name = "SlideCircle"
           SlideCircle.Parent = SlideFrame
           SlideCircle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           SlideCircle.BackgroundTransparency = 1.000
           SlideCircle.Position = UDim2.new((start or 0)/max, -6,-1.30499995, 0)
           SlideCircle.Size = UDim2.new(0, 11, 0, 11)
           SlideCircle.Image = "rbxassetid://3570695787"
           SlideCircle.ImageColor3 = PresetColor
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Slider
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(86, 86, 86)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           ArrowIco.ImageTransparency = .3
  
           Value.Name = "Value"
           Value.Parent = Title
           Value.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Value.BackgroundTransparency = 1.000
           Value.Position = UDim2.new(2.27693367, 0, 0, 0)
           Value.Size = UDim2.new(0, 113, 0, 41)
           Value.Font = Enum.Font.Gotham
           Value.Text = tostring(start and math.floor((start / max) * (max - min) + min) or 0)
           Value.TextColor3 = Color3.fromRGB(255, 255, 255)
           Value.TextSize = 15.000
           Value.TextTransparency = 0.300
           Value.TextXAlignment = Enum.TextXAlignment.Right
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if SliderDescToggled == false then
                 Slider:TweenSize(UDim2.new(0, 457, 0, 101), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    Value,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 =PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Slider:TweenSize(UDim2.new(0, 457, 0, 60), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Value,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              SliderDescToggled = not SliderDescToggled
           end)
           
              local function move(input)
                 local pos =
                    UDim2.new(
                       math.clamp((input.Position.X - SlideFrame.AbsolutePosition.X) / SlideFrame.AbsoluteSize.X, 0, 1),
                       -6,
                    -1.30499995,
                       0
                    )
                 local pos1 =
                    UDim2.new(
                       math.clamp((input.Position.X - SlideFrame.AbsolutePosition.X) / SlideFrame.AbsoluteSize.X, 0, 1),
                       0,
                       0,
                       3
                    )
                 CurrentValueFrame:TweenSize(pos1, "Out", "Sine", 0.1, true)
                 SlideCircle:TweenPosition(pos, "Out", "Sine", 0.1, true)
                 local value = math.floor(((pos.X.Scale * max) / max) * (max - min) + min)
                 Value.Text = tostring(value)
                 pcall(callback, value)
              end
              SlideCircle.InputBegan:Connect(
                 function(input)
                    if input.UserInputType == Enum.UserInputType.MouseButton1 then
                       dragging = true
                    end
                 end
              )
              SlideCircle.InputEnded:Connect(
                 function(input)
                    if input.UserInputType == Enum.UserInputType.MouseButton1 then
                       dragging = false
                    end
                 end
              )
              game:GetService("UserInputService").InputChanged:Connect(
              function(input)
                 if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then
                    move(input)
                 end
              end
              )
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
           function SliderFunc:Change(tochange)
              CurrentValueFrame.Size = UDim2.new((tochange or 0) / max, 0, 0, 3)
              SlideCircle.Position = UDim2.new((tochange or 0)/max, -6,-1.30499995, 0)
              Value.Text = tostring(tochange and math.floor((tochange / max) * (max - min) + min) or 0)
              pcall(callback,tochange)
           end
           return SliderFunc
        end
        function ContainerContent:Dropdown(text,list,callback)
           local DropFunc = {}
           local Selected = text
           local FrameSize = 43
           local ItemCount = 0
           local DropToggled = false
           local Dropdown = Instance.new("TextButton")
           local DropdownCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local ArrowIco = Instance.new("ImageLabel")
           local DropItemHolder = Instance.new("ScrollingFrame")
           local DropLayout = Instance.new("UIListLayout")
  
           Dropdown.Name = "Dropdown"
           Dropdown.Parent = Container
           Dropdown.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Dropdown.ClipsDescendants = true
           Dropdown.Position = UDim2.new(0.110937499, 0, 0.67653507, 0)
           Dropdown.Size = UDim2.new(0, 457, 0, 43)
           Dropdown.AutoButtonColor = false
           Dropdown.Font = Enum.Font.SourceSans
           Dropdown.Text = ""
           Dropdown.TextColor3 = Color3.fromRGB(0, 0, 0)
           Dropdown.TextSize = 14.000
  
           DropdownCorner.CornerRadius = UDim.new(0, 4)
           DropdownCorner.Name = "DropdownCorner"
           DropdownCorner.Parent = Dropdown
  
           Title.Name = "Title"
           Title.Parent = Dropdown
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = Title
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(3.45979357, 0, 0.508096159, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6035047377"
           ArrowIco.ImageTransparency = .3
  
           DropItemHolder.Name = "DropItemHolder"
           DropItemHolder.Parent = Title
           DropItemHolder.Active = true
           DropItemHolder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           DropItemHolder.BackgroundTransparency = 1.000
           DropItemHolder.BorderSizePixel = 0
           DropItemHolder.Position = UDim2.new(-0.203539819, 0, 1.02380955, 0)
           DropItemHolder.Size = UDim2.new(0, 436, 0, 82)
           DropItemHolder.CanvasSize = UDim2.new(0, 0, 0, 0)
           DropItemHolder.ScrollBarThickness = 5
           DropItemHolder.ScrollBarImageColor3 = Color3.fromRGB(35, 35, 35)
  
           DropLayout.Name = "DropLayout"
           DropLayout.Parent = DropItemHolder
           DropLayout.SortOrder = Enum.SortOrder.LayoutOrder
           DropLayout.Padding = UDim.new(0, 2)
           
           Dropdown.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           Dropdown.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
  
           
           Dropdown.MouseButton1Click:Connect(function()
              if DropToggled == false then
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, FrameSize), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           DropToggled = not DropToggled
           end)
           
           for i,v in next, list do
              ItemCount = ItemCount + 1
              
              if ItemCount == 1 then
                 FrameSize = 78
              elseif ItemCount == 2 then
                 FrameSize = 107
              elseif ItemCount >= 3 then
                 FrameSize = 133
              end
              local Item = Instance.new("TextButton")
              local ItemCorner = Instance.new("UICorner")
              
           Item.Name = "Item"
           Item.Parent = DropItemHolder
           Item.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Item.ClipsDescendants = true
           Item.Size = UDim2.new(0, 427, 0, 25)
           Item.AutoButtonColor = false
           Item.Font = Enum.Font.Gotham
           Item.Text = v
           Item.TextColor3 = Color3.fromRGB(255, 255, 255)
           Item.TextSize = 15.000
           Item.TextTransparency = 0.300
  
           ItemCorner.CornerRadius = UDim.new(0, 4)
           ItemCorner.Name = "ItemCorner"
              ItemCorner.Parent = Item
              DropItemHolder.CanvasSize = UDim2.new(0, 0, 0, DropLayout.AbsoluteContentSize.Y)
              
              Item.MouseEnter:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
              end)
  
              Item.MouseLeave:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
              end)
              
              Item.MouseButton1Click:Connect(function()
                 pcall(callback, v)
                 Title.Text = text
                 Selected = v
                 DropToggled = not DropToggled
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
                 
              end)
           end
           function DropFunc:Add(addtext)
              ItemCount = ItemCount + 1
  
              if ItemCount == 1 then
                 FrameSize = 78
              elseif ItemCount == 2 then
                 FrameSize = 107
              elseif ItemCount >= 3 then
                 FrameSize = 133
              end
              local Item = Instance.new("TextButton")
              local ItemCorner = Instance.new("UICorner")
  
              Item.Name = "Item"
              Item.Parent = DropItemHolder
              Item.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
              Item.ClipsDescendants = true
              Item.Size = UDim2.new(0, 427, 0, 25)
              Item.AutoButtonColor = false
              Item.Font = Enum.Font.Gotham
              Item.Text = addtext
              Item.TextColor3 = Color3.fromRGB(255, 255, 255)
              Item.TextSize = 15.000
              Item.TextTransparency = 0.300
  
              ItemCorner.CornerRadius = UDim.new(0, 4)
              ItemCorner.Name = "ItemCorner"
              ItemCorner.Parent = Item
              DropItemHolder.CanvasSize = UDim2.new(0, 0, 0, DropLayout.AbsoluteContentSize.Y)
  
              Item.MouseEnter:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
              end)
  
              Item.MouseLeave:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
              end)
  
              Item.MouseButton1Click:Connect(function()
                 pcall(callback, addtext)
                 Title.Text = text
                 Selected = addtext
                 DropToggled = not DropToggled
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end)
              if DropToggled == true then
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           end
           function DropFunc:Clear()
              Title.Text = text
              FrameSize = 0
              ItemCount = 0
              for i, v in next, DropItemHolder:GetChildren() do
                 if v.Name == "Item" then
                    v:Destroy()
                 end
              end
              if DropToggled == true then
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           end
           return DropFunc
        end
        function ContainerContent:Colorpicker(text,preset,callback)
           local ColorPickerToggled = false
           local OldToggleColor = Color3.fromRGB(0, 0, 0)
           local OldColor = Color3.fromRGB(0, 0, 0)
           local OldColorSelectionPosition = nil
           local OldHueSelectionPosition = nil
           local ColorH, ColorS, ColorV = 1, 1, 1
           local RainbowColorPicker = false
           local ColorPickerInput = nil
           local ColorInput = nil
           local HueInput = nil
           
           local Colorpicker = Instance.new("Frame")
           local ColorpickerCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Hue = Instance.new("ImageLabel")
           local HueCorner = Instance.new("UICorner")
           local HueGradient = Instance.new("UIGradient")
           local HueSelection = Instance.new("ImageLabel")
           local Color = Instance.new("ImageLabel")
           local ColorCorner = Instance.new("UICorner")
           local ColorSelection = Instance.new("ImageLabel")
           local Toggle = Instance.new("TextLabel")
           local ToggleFrame = Instance.new("Frame")
           local ToggleFrameCorner = Instance.new("UICorner")
           local ToggleCircle = Instance.new("Frame")
           local ToggleCircleCorner = Instance.new("UICorner")
           local Confirm = Instance.new("TextButton")
           local ConfirmCorner = Instance.new("UICorner")
           local ConfirmTitle = Instance.new("TextLabel")
           local BoxColor = Instance.new("Frame")
           local BoxColorCorner = Instance.new("UICorner")
           local ColorpickerBtn = Instance.new("TextButton")
           local ToggleBtn = Instance.new("TextButton")
  
  
           Colorpicker.Name = "Colorpicker"
           Colorpicker.Parent = Container
           Colorpicker.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
           Colorpicker.ClipsDescendants = true
           Colorpicker.Position = UDim2.new(0.110937499, 0, 0.67653507, 0)
           Colorpicker.Size = UDim2.new(0, 457, 0, 43)
  
           ColorpickerCorner.CornerRadius = UDim.new(0, 4)
           ColorpickerCorner.Name = "ColorpickerCorner"
           ColorpickerCorner.Parent = Colorpicker
  
           Title.Name = "Title"
           Title.Parent = Colorpicker
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = "UI Color Setting"
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
           
  
           ColorpickerBtn.Name = "ColorpickerBtn"
           ColorpickerBtn.Parent = Title
           ColorpickerBtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ColorpickerBtn.BackgroundTransparency = 1.000
           ColorpickerBtn.Position = UDim2.new(-0.336283177, 0, 0, 0)
           ColorpickerBtn.Size = UDim2.new(0, 457, 0, 42)
           ColorpickerBtn.Font = Enum.Font.SourceSans
           ColorpickerBtn.Text = ""
           ColorpickerBtn.TextColor3 = Color3.fromRGB(0, 0, 0)
           ColorpickerBtn.TextSize = 14.000
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Hue.Name = "Hue"
           Hue.Parent = Title
           Hue.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Hue.Position = UDim2.new(0, 229, 0, 46)
           Hue.Size = UDim2.new(0, 25, 0, 80)
  
           HueCorner.CornerRadius = UDim.new(0, 3)
           HueCorner.Name = "HueCorner"
           HueCorner.Parent = Hue
  
           HueGradient.Color = ColorSequence.new {
              ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 0, 4)),
              ColorSequenceKeypoint.new(0.20, Color3.fromRGB(234, 255, 0)),
              ColorSequenceKeypoint.new(0.40, Color3.fromRGB(21, 255, 0)),
              ColorSequenceKeypoint.new(0.60, Color3.fromRGB(0, 255, 255)),
              ColorSequenceKeypoint.new(0.80, Color3.fromRGB(0, 17, 255)),
              ColorSequenceKeypoint.new(0.90, Color3.fromRGB(255, 0, 251)),
              ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 0, 4))
           }			
           HueGradient.Rotation = 270
           HueGradient.Name = "HueGradient"
           HueGradient.Parent = Hue
  
           HueSelection.Name = "HueSelection"
           HueSelection.Parent = Hue
           HueSelection.AnchorPoint = Vector2.new(0.5, 0.5)
           HueSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           HueSelection.BackgroundTransparency = 1.000
           HueSelection.Position = UDim2.new(0.48, 0, 1 - select(1, Color3.toHSV(preset)))
           HueSelection.Size = UDim2.new(0, 18, 0, 18)
           HueSelection.Image = "http://www.roblox.com/asset/?id=4805639000"
           HueSelection.Visible = false
  
           Color.Name = "Color"
           Color.Parent = Title
           Color.BackgroundColor3 = Color3.fromRGB(255, 0, 4)
           Color.Position = UDim2.new(0, -23, 0, 46)
           Color.Size = UDim2.new(0, 246, 0, 80)
           Color.ZIndex = 10
           Color.Image = "rbxassetid://4155801252"
  
           ColorCorner.CornerRadius = UDim.new(0, 3)
           ColorCorner.Name = "ColorCorner"
           ColorCorner.Parent = Color
  
           ColorSelection.Name = "ColorSelection"
           ColorSelection.Parent = Color
           ColorSelection.AnchorPoint = Vector2.new(0.5, 0.5)
           ColorSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ColorSelection.BackgroundTransparency = 1.000
           ColorSelection.Position = UDim2.new(preset and select(3, Color3.toHSV(preset)))
           ColorSelection.Size = UDim2.new(0, 18, 0, 18)
           ColorSelection.Image = "http://www.roblox.com/asset/?id=4805639000"
           ColorSelection.ScaleType = Enum.ScaleType.Fit
           ColorSelection.Visible = false
  
           Toggle.Name = "Toggle"
           Toggle.Parent = Title
           Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Toggle.BackgroundTransparency = 1.000
           Toggle.Position = UDim2.new(2.37430048, 0, 1.07157099, 0)
           Toggle.Size = UDim2.new(0, 137, 0, 38)
           Toggle.Font = Enum.Font.Gotham
           Toggle.Text = "Rainbow"
           Toggle.TextColor3 = Color3.fromRGB(255, 255, 255)
           Toggle.TextSize = 15.000
           Toggle.TextTransparency = 0.300
           Toggle.TextXAlignment = Enum.TextXAlignment.Left
  
           ToggleFrame.Name = "ToggleFrame"
           ToggleFrame.Parent = Toggle
           ToggleFrame.BackgroundColor3 = Color3.fromRGB(226, 227, 227)
           ToggleFrame.Position = UDim2.new(0.778387249, 0, 0.357142866, 0)
           ToggleFrame.Size = UDim2.new(0, 27, 0, 11)
  
           ToggleFrameCorner.Name = "ToggleFrameCorner"
           ToggleFrameCorner.Parent = ToggleFrame
  
           ToggleCircle.Name = "ToggleCircle"
           ToggleCircle.Parent = ToggleFrame
           ToggleCircle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ToggleCircle.Position = UDim2.new(0, 0, -0.273000002, 0)
           ToggleCircle.Selectable = true
           ToggleCircle.Size = UDim2.new(0, 17, 0, 17)
  
           ToggleCircleCorner.CornerRadius = UDim.new(2, 8)
           ToggleCircleCorner.Name = "ToggleCircleCorner"
           ToggleCircleCorner.Parent = ToggleCircle
  
           Confirm.Name = "Confirm"
           Confirm.Parent = Title
           Confirm.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
           Confirm.ClipsDescendants = true
           Confirm.Position = UDim2.new(2.3791616, 0, 1.97633278, 0)
           Confirm.Size = UDim2.new(0, 144, 0, 42)
           Confirm.AutoButtonColor = false
           Confirm.Font = Enum.Font.SourceSans
           Confirm.Text = ""
           Confirm.TextColor3 = Color3.fromRGB(0, 0, 0)
           Confirm.TextSize = 14.000
  
           ConfirmCorner.CornerRadius = UDim.new(0, 4)
           ConfirmCorner.Name = "ConfirmCorner"
           ConfirmCorner.Parent = Confirm
  
           ConfirmTitle.Name = "ConfirmTitle"
           ConfirmTitle.Parent = Confirm
           ConfirmTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ConfirmTitle.BackgroundTransparency = 1.000
           ConfirmTitle.Size = UDim2.new(0, 116, 0, 40)
           ConfirmTitle.Font = Enum.Font.Gotham
           ConfirmTitle.Text = "Confirm"
           ConfirmTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
           ConfirmTitle.TextSize = 15.000
           ConfirmTitle.TextTransparency = 0.300
           ConfirmTitle.TextXAlignment = Enum.TextXAlignment.Left
  
           BoxColor.Name = "BoxColor"
           BoxColor.Parent = Title
           BoxColor.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           BoxColor.Position = UDim2.new(3.26915574, 0, 0.261904776, 0)
           BoxColor.Size = UDim2.new(0, 35, 0, 19)
  
           BoxColorCorner.CornerRadius = UDim.new(0, 4)
           BoxColorCorner.Name = "BoxColorCorner"
           BoxColorCorner.Parent = BoxColor
  
           ToggleBtn.Name = "ToggleBtn"
           ToggleBtn.Parent = Toggle
           ToggleBtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ToggleBtn.BackgroundTransparency = 1.000
           ToggleBtn.Size = UDim2.new(0, 137, 0, 38)
           ToggleBtn.Font = Enum.Font.SourceSans
           ToggleBtn.Text = ""
           ToggleBtn.TextColor3 = Color3.fromRGB(0, 0, 0)
           ToggleBtn.TextSize = 14.000
           
           ColorpickerBtn.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           ColorpickerBtn.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
            
           ColorpickerBtn.MouseButton1Click:Connect(function()
              if ColorPickerToggled == false then
                 ColorSelection.Visible = true
                 HueSelection.Visible = true
                 Colorpicker:TweenSize(UDim2.new(0, 457, 0, 138), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 ColorSelection.Visible = false
                 HueSelection.Visible = false
                 Colorpicker:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              ColorPickerToggled = not ColorPickerToggled
           end)
           
  
           local function UpdateColorPicker(nope)
              BoxColor.BackgroundColor3 = Color3.fromHSV(ColorH, ColorS, ColorV)
              Color.BackgroundColor3 = Color3.fromHSV(ColorH, 1, 1)
  
              pcall(callback, BoxColor.BackgroundColor3)
           end
  
           ColorH =
              1 -
              (math.clamp(HueSelection.AbsolutePosition.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) /
                 Hue.AbsoluteSize.Y)
           ColorS =
              (math.clamp(ColorSelection.AbsolutePosition.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) /
                 Color.AbsoluteSize.X)
           ColorV =
              1 -
              (math.clamp(ColorSelection.AbsolutePosition.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) /
                 Color.AbsoluteSize.Y)
  
           BoxColor.BackgroundColor3 = preset
           Color.BackgroundColor3 = preset
           pcall(callback, BoxColor.BackgroundColor3)
  
           Color.InputBegan:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if RainbowColorPicker then
                       return
                    end
  
                    if ColorInput then
                       ColorInput:Disconnect()
                    end
  
                    ColorInput =
                       RunService.RenderStepped:Connect(
                          function()
                          local ColorX =
                             (math.clamp(Mouse.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) /
                                Color.AbsoluteSize.X)
                          local ColorY =
                             (math.clamp(Mouse.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) /
                                Color.AbsoluteSize.Y)
  
                          ColorSelection.Position = UDim2.new(ColorX, 0, ColorY, 0)
                          ColorS = ColorX
                          ColorV = 1 - ColorY
  
                          UpdateColorPicker(true)
                       end
                       )
                 end
              end
           )
  
           Color.InputEnded:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if ColorInput then
                       ColorInput:Disconnect()
                    end
                 end
              end
           )
  
           Hue.InputBegan:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if RainbowColorPicker then
                       return
                    end
  
                    if HueInput then
                       HueInput:Disconnect()
                    end
  
                    HueInput =
                       RunService.RenderStepped:Connect(
                          function()
                          local HueY =
                             (math.clamp(Mouse.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) /
                                Hue.AbsoluteSize.Y)
  
                          HueSelection.Position = UDim2.new(0.48, 0, HueY, 0)
                          ColorH = 1 - HueY
  
                          UpdateColorPicker(true)
                       end
                       )
                 end
              end
           )
  
           Hue.InputEnded:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if HueInput then
                       HueInput:Disconnect()
                    end
                 end
              end
           )
  
           ToggleBtn.MouseButton1Down:Connect(
              function()
                 RainbowColorPicker = not RainbowColorPicker
  
                 if ColorInput then
                    ColorInput:Disconnect()
                 end
  
                 if HueInput then
                    HueInput:Disconnect()
                 end
  
                 if RainbowColorPicker then
                    ToggleCircle:TweenPosition(UDim2.new(0.37, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                    TweenService:Create(
                       ToggleCircle,
                       TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                       {BackgroundColor3 =PresetColor}
                    ):Play()
  
                    OldToggleColor = BoxColor.BackgroundColor3
                    OldColor = Color.BackgroundColor3
                    OldColorSelectionPosition = ColorSelection.Position
                    OldHueSelectionPosition = HueSelection.Position
  
                    while RainbowColorPicker do
                       BoxColor.BackgroundColor3 = Color3.fromHSV(Flux.RainbowColorValue, 1, 1)
                       Color.BackgroundColor3 = Color3.fromHSV(Flux.RainbowColorValue, 1, 1)
  
                       ColorSelection.Position = UDim2.new(1, 0, 0, 0)
                       HueSelection.Position = UDim2.new(0.48, 0, 0, Flux.HueSelectionPosition)
  
                       pcall(callback, BoxColor.BackgroundColor3)
                       wait()
                    end
                 elseif not RainbowColorPicker then
                    ToggleCircle:TweenPosition(UDim2.new(0, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                    TweenService:Create(
                       ToggleCircle,
                       TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                       {BackgroundColor3 = Color3.fromRGB(255,255,255)}
                    ):Play()
  
                    BoxColor.BackgroundColor3 = OldToggleColor
                    Color.BackgroundColor3 = OldColor
  
                    ColorSelection.Position = OldColorSelectionPosition
                    HueSelection.Position = OldHueSelectionPosition
  
                    pcall(callback, BoxColor.BackgroundColor3)
                 end
              end
           )
  
           Confirm.MouseButton1Click:Connect(
              function()
                 ColorPickerToggled = not ColorPickerToggled
                 Colorpicker:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           )
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Line()
           local Line = Instance.new("TextButton")
           local LineCorner = Instance.new("UICorner")
  
           Line.Name = "Line"
           Line.Parent = Container
           Line.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           Line.ClipsDescendants = true
           Line.Position = UDim2.new(0, 0, 0.70091325, 0)
           Line.Size = UDim2.new(0, 457, 0, 4)
           Line.AutoButtonColor = false
           Line.Font = Enum.Font.SourceSans
           Line.Text = ""
           Line.TextColor3 = Color3.fromRGB(0, 0, 0)
           Line.TextSize = 14.000
  
           LineCorner.CornerRadius = UDim.new(0, 4)
           LineCorner.Name = "LineCorner"
           LineCorner.Parent = Line
           
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Label(text)
           local labelfunc = {}
           local Label = Instance.new("TextButton")
           local LabelCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
  
           Label.Name = "Label"
           Label.Parent = Container
           Label.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Label.ClipsDescendants = true
           Label.Position = UDim2.new(0.370312512, 0, 0.552631557, 0)
           Label.Size = UDim2.new(0, 457, 0, 43)
           Label.AutoButtonColor = false
           Label.Font = Enum.Font.SourceSans
           Label.Text = ""
           Label.TextColor3 = Color3.fromRGB(0, 0, 0)
           Label.TextSize = 14.000
  
           LabelCorner.CornerRadius = UDim.new(0, 4)
           LabelCorner.Name = "LabelCorner"
           LabelCorner.Parent = Label
  
           Title.Name = "Title"
           Title.Parent = Label
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.038480062, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
           
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
           function labelfunc:Refresh(tochange)
              Title.Text = tochange
           end
           return labelfunc
        end
        function ContainerContent:Textbox(text,desc,disapper,callback)
           if desc == "" then
              desc = "There is no description for this textbox."
           end
           local TextboxDescToggled = false
           local Textbox = Instance.new("TextButton")
           local TextboxCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local TextboxFrame = Instance.new("Frame")
           local TextboxFrameCorner = Instance.new("UICorner")
           local TextBox = Instance.new("TextBox")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
  
           Textbox.Name = "Textbox"
           Textbox.Parent = Container
           Textbox.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           Textbox.ClipsDescendants = true
           Textbox.Position = UDim2.new(0.0459499061, 0, 0.734449744, 0)
           Textbox.Size = UDim2.new(0, 457, 0, 43)
           Textbox.AutoButtonColor = false
           Textbox.Font = Enum.Font.SourceSans
           Textbox.Text = ""
           Textbox.TextColor3 = Color3.fromRGB(0, 0, 0)
           Textbox.TextSize = 14.000
  
           TextboxCorner.CornerRadius = UDim.new(0, 4)
           TextboxCorner.Name = "TextboxCorner"
           TextboxCorner.Parent = Textbox
  
           Title.Name = "Title"
           Title.Parent = Textbox
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.200942323, 0, 0.985714269, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 1
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           TextboxFrame.Name = "TextboxFrame"
           TextboxFrame.Parent = Title
           TextboxFrame.BackgroundColor3 = Color3.fromRGB(50, 53, 59)
           TextboxFrame.Position = UDim2.new(1.82300889, 0, 0.202380955, 0)
           TextboxFrame.Size = UDim2.new(0, 161, 0, 26)
  
           TextboxFrameCorner.CornerRadius = UDim.new(0, 4)
           TextboxFrameCorner.Name = "TextboxFrameCorner"
           TextboxFrameCorner.Parent = TextboxFrame
  
           TextBox.Parent = TextboxFrame
           TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           TextBox.BackgroundTransparency = 1.000
           TextBox.Size = UDim2.new(0, 161, 0, 26)
           TextBox.Font = Enum.Font.Gotham
           TextBox.Text = ""
           TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
           TextBox.TextSize = 15.000
           TextBox.TextTransparency = 0.300
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Textbox
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(86, 86, 86)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           
           TextBox.FocusLost:Connect(
              function(ep)
                 if ep then
                    if #TextBox.Text > 0 then
                       pcall(callback, TextBox.Text)
                       if disapper then
                          TextBox.Text = ""
                       end
                    end
                 end
              end
           )
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if TextboxDescToggled == false then
                 Textbox:TweenSize(UDim2.new(0, 457, 0, 81), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Textbox:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              TextboxDescToggled = not TextboxDescToggled
           end)
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Bind(text,presetbind,callback)
           local Key = presetbind.Name
           local Bind = Instance.new("TextButton")
           local BindCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local BindLabel = Instance.new("TextLabel")
  
           Bind.Name = "Bind"
           Bind.Parent = Container
           Bind.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           Bind.ClipsDescendants = true
           Bind.Position = UDim2.new(0.40625, 0, 0.828947306, 0)
           Bind.Size = UDim2.new(0, 457, 0, 43)
           Bind.AutoButtonColor = false
           Bind.Font = Enum.Font.SourceSans
           Bind.Text = ""
           Bind.TextColor3 = Color3.fromRGB(0, 0, 0)
           Bind.TextSize = 14.000
  
           BindCorner.CornerRadius = UDim.new(0, 4)
           BindCorner.Name = "BindCorner"
           BindCorner.Parent = Bind
  
           Title.Name = "Title"
           Title.Parent = Bind
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           BindLabel.Name = "BindLabel"
           BindLabel.Parent = Title
           BindLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           BindLabel.BackgroundTransparency = 1.000
           BindLabel.Position = UDim2.new(2.56011987, 0, 0, 0)
           BindLabel.Size = UDim2.new(0, 113, 0, 42)
           BindLabel.Font = Enum.Font.Gotham
           BindLabel.Text = Key
           BindLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
           BindLabel.TextSize = 15.000
           BindLabel.TextTransparency = 0.300
           BindLabel.TextXAlignment = Enum.TextXAlignment.Right
           
           Bind.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           Bind.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
  
           Bind.MouseButton1Click:connect(
              function()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 BindLabel.Text = "..."
                 local inputwait = game:GetService("UserInputService").InputBegan:wait()
                 if inputwait.KeyCode.Name ~= "Unknown" then
                    BindLabel.Text = inputwait .KeyCode.Name
                    Key = inputwait .KeyCode.Name
                 end
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
              end
           )
  
           game:GetService("UserInputService").InputBegan:connect(
           function(current, pressed)
              if not pressed then
                 if current.KeyCode.Name == Key then
                    pcall(callback)
                 end
              end
           end
           )
           
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        return ContainerContent
     end
     return Tabs
  end
  local win = Flux:Window("JPEXHUB", "Bloxfruit",getgenv().ColorUi,getgenv().OffOnUI)
 local placeId = game.PlaceId
 Magnet = true
 if placeId == 2753915549 then
    OldWorld = true
 elseif placeId == 4442272183 then
    NewWorld = true
elseif placeId == 7449423635 then
   Third = true
 end
 function Click()
    game:GetService'VirtualUser':CaptureController()
    game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
 end
 function CheckQuest()
    local MyLevel = game.Players.LocalPlayer.Data.Level.Value
    if OldWorld then
       if MyLevel == 1 or MyLevel <= 9 then -- Bandit
             Ms = "Bandit [Lv. 5]"
             NaemQuest = "BanditQuest1"
             LevelQuest = 1
             NameMon = "Bandit"
             CFrameQuest = CFrame.new(1061.66699, 16.5166187, 1544.52905, -0.942978859, -3.33851502e-09, 0.332852632, 7.04340497e-09, 1, 2.99841325e-08, -0.332852632, 3.06188177e-08, -0.942978859)
             CFrameMon = CFrame.new(1199.31287, 52.2717781, 1536.91516, -0.929782331, 6.60215846e-08, -0.368109822, 3.9077392e-08, 1, 8.06501603e-08, 0.368109822, 6.06023249e-08, -0.929782331)
       elseif MyLevel == 10 or MyLevel <= 14 then -- Monkey
             Ms = "Monkey [Lv. 14]"
             NaemQuest = "JungleQuest"
             LevelQuest = 1
             NameMon = "Monkey"
             CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
             CFrameMon = CFrame.new(-1402.74609, 98.5633316, 90.6417007, 0.836947978, 0, 0.547282517, -0, 1, -0, -0.547282517, 0, 0.836947978)
       elseif MyLevel == 15 or MyLevel <= 29 then -- Gorilla
             Ms = "Gorilla [Lv. 20]"
             NaemQuest = "JungleQuest"
             LevelQuest = 2
             NameMon = "Gorilla"
             CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
             CFrameMon = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
       elseif MyLevel == 30 or MyLevel <= 39 then -- Pirate
             Ms = "Pirate [Lv. 35]"
             NaemQuest = "BuggyQuest1"
             LevelQuest = 1
             NameMon = "Pirate"
             CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
             CFrameMon = CFrame.new(-1219.32324, 4.75205183, 3915.63452, -0.966492832, -6.91238853e-08, 0.25669381, -5.21195496e-08, 1, 7.3047012e-08, -0.25669381, 5.72206496e-08, -0.966492832)
       elseif MyLevel == 40 or MyLevel <= 59 then -- Brute
             Ms = "Brute [Lv. 45]"
             NaemQuest = "BuggyQuest1"
             LevelQuest = 2
             NameMon = "Brute"
             CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
             CFrameMon = CFrame.new(-1146.49646, 96.0936813, 4312.1333, -0.978175163, -1.53222057e-08, 0.207781896, -3.33316912e-08, 1, -8.31738873e-08, -0.207781896, -8.82843523e-08, -0.978175163)
       elseif MyLevel == 60 or MyLevel <= 74 then -- Desert Bandit
             Ms = "Desert Bandit [Lv. 60]"
             NaemQuest = "DesertQuest"
             LevelQuest = 1
             NameMon = "Desert Bandit"
             CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
             CFrameMon = CFrame.new(932.788818, 6.4503746, 4488.24609, -0.998625934, 3.08948351e-08, 0.0524050146, 2.79967303e-08, 1, -5.60361286e-08, -0.0524050146, -5.44919629e-08, -0.998625934)
       elseif MyLevel == 75 or MyLevel <= 89 then -- Desert Officre
             Ms = "Desert Officer [Lv. 70]"
             NaemQuest = "DesertQuest"
             LevelQuest = 2
             NameMon = "Desert Officer"
             CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
             CFrameMon = CFrame.new(1580.03198, 4.61375761, 4366.86426, 0.135744005, -6.44280718e-08, -0.990743816, 4.35738308e-08, 1, -5.90598574e-08, 0.990743816, -3.51534837e-08, 0.135744005)
       elseif MyLevel == 90 or MyLevel <= 99 then -- Snow Bandits
             Ms = "Snow Bandit [Lv. 90]"
             NaemQuest = "SnowQuest"
             LevelQuest = 1
             NameMon = "Snow Bandits"
             CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
             CFrameMon = CFrame.new(1370.24316, 102.403511, -1411.52905, 0.980274439, -1.12995728e-08, 0.197641045, -9.57343449e-09, 1, 1.04655214e-07, -0.197641045, -1.04482936e-07, 0.980274439)
       elseif MyLevel == 100 or MyLevel <= 119 then -- Snowman
             Ms = "Snowman [Lv. 100]"
             NaemQuest = "SnowQuest"
             LevelQuest = 2
             NameMon = "Snowman"
             CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
             CFrameMon = CFrame.new(1370.24316, 102.403511, -1411.52905, 0.980274439, -1.12995728e-08, 0.197641045, -9.57343449e-09, 1, 1.04655214e-07, -0.197641045, -1.04482936e-07, 0.980274439)
       elseif MyLevel == 120 or MyLevel <= 149 then -- Chief Petty Officer
             Ms = "Chief Petty Officer [Lv. 120]"
             NaemQuest = "MarineQuest2"
             LevelQuest = 1
             NameMon = "Chief Petty Officer"
             CFrameQuest = CFrame.new(-5035.0835, 28.6520386, 4325.29443, 0.0243340395, -7.08064647e-08, 0.999703884, -6.36926814e-08, 1, 7.23777944e-08, -0.999703884, -6.54350671e-08, 0.0243340395)
             CFrameMon = CFrame.new(-4882.8623, 22.6520386, 4255.53516, 0.273695946, -5.40380647e-08, -0.96181643, 4.37720793e-08, 1, -4.37274998e-08, 0.96181643, -3.01326679e-08, 0.273695946)
       elseif MyLevel == 150 or MyLevel <= 174 then -- Sky Bandit
             Ms = "Sky Bandit [Lv. 150]"
             NaemQuest = "SkyQuest"
             LevelQuest = 1
             NameMon = "Sky Bandit"
             CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
             CFrameMon = CFrame.new(-4970.74219, 294.544342, -2890.11353, -0.994874597, -8.61311236e-08, -0.101116329, -9.10836206e-08, 1, 4.43614923e-08, 0.101116329, 5.33441664e-08, -0.994874597)
       elseif MyLevel == 175 or MyLevel <= 224 then -- Dark Master
             Ms = "Dark Master [Lv. 175]"
             NaemQuest = "SkyQuest"
             LevelQuest = 2
             NameMon = "Dark Master"
             CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
             CFrameMon = CFrame.new(-5220.58594, 430.693298, -2278.17456, -0.925375521, 1.12086873e-08, 0.379051805, -1.05115507e-08, 1, -5.52320891e-08, -0.379051805, -5.50948407e-08, -0.925375521)
       elseif MyLevel == 225 or MyLevel <= 274 then -- Toga Warrior
             Ms = "Toga Warrior [Lv. 225]"
             NaemQuest = "ColosseumQuest"
             LevelQuest = 1
             NameMon = "Toga Warrior"
             CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
             CFrameMon = CFrame.new(-1779.97583, 44.6077499, -2736.35474, 0.984437346, 4.10396339e-08, 0.175734788, -3.62286876e-08, 1, -3.05844168e-08, -0.175734788, 2.3741821e-08, 0.984437346)
       elseif MyLevel == 275 or MyLevel <= 299 then -- Gladiato
             Ms = "Gladiator [Lv. 275]"
             NaemQuest = "ColosseumQuest"
             LevelQuest = 2
             NameMon = "Gladiato"
             CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
             CFrameMon = CFrame.new(-1274.75903, 58.1895943, -3188.16309, 0.464524001, 6.21005611e-08, 0.885560572, -4.80449414e-09, 1, -6.76054768e-08, -0.885560572, 2.71497012e-08, 0.464524001)
       elseif MyLevel == 300 or MyLevel <= 329 then -- Military Soldier
             Ms = "Military Soldier [Lv. 300]"
             NaemQuest = "MagmaQuest"
             LevelQuest = 1
             NameMon = "Military Soldier"
             CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
             CFrameMon = CFrame.new(-5363.01123, 41.5056877, 8548.47266, -0.578253984, -3.29503091e-10, 0.815856814, 9.11209668e-08, 1, 6.498761e-08, -0.815856814, 1.11920997e-07, -0.578253984)
       elseif MyLevel == 300 or MyLevel <= 374 then -- Military Spy
             Ms = "Military Spy [Lv. 330]"
             NaemQuest = "MagmaQuest"
             LevelQuest = 2
             NameMon = "Military Spy"
             CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
             CFrameMon = CFrame.new(-5787.99023, 120.864456, 8762.25293, -0.188358366, -1.84706277e-08, 0.982100308, -1.23782129e-07, 1, -4.93306951e-09, -0.982100308, -1.22495649e-07, -0.188358366)
       elseif MyLevel == 375 or MyLevel <= 399 then -- Fishman Warrior
             Ms = "Fishman Warrior [Lv. 375]"
             NaemQuest = "FishmanQuest"
             LevelQuest = 1
             NameMon = "Fishman Warrior"
             CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
             CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.91687, -0.0817126185, 8.90751153e-08, 0.996655822, 2.00889794e-08, 1, -8.77269599e-08, -0.996655822, 1.28533992e-08, -0.0817126185)
       elseif MyLevel == 400 or MyLevel <= 449 then -- Fishman Commando
             Ms = "Fishman Commando [Lv. 400]"
             NaemQuest = "FishmanQuest"
             LevelQuest = 2
             NameMon = "Fishman Commando"
             CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
             CFrameMon = CFrame.new(61885.5039, 18.4828243, 1504.17896, 0.577502489, 0, -0.816389024, -0, 1.00000012, -0, 0.816389024, 0, 0.577502489)
       elseif MyLevel == 450 or MyLevel <= 474 then -- God's Guards
             Ms = "God's Guard [Lv. 450]"
             NaemQuest = "SkyExp1Quest"
             LevelQuest = 1
             NameMon = "God's Guards"
             CFrameQuest = CFrame.new(-4721.71436, 845.277161, -1954.20105, -0.999277651, -5.56969759e-09, 0.0380011722, -4.14751478e-09, 1, 3.75035256e-08, -0.0380011722, 3.73188307e-08, -0.999277651)
             CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.92542, -0.93441087, -6.77488776e-09, -0.356197298, 1.12145182e-08, 1, -4.84390199e-08, 0.356197298, -4.92565206e-08, -0.93441087)
       elseif MyLevel == 475 or MyLevel <= 524 then -- Shandas
             Ms = "Shanda [Lv. 475]"
             NaemQuest = "SkyExp1Quest"
             LevelQuest = 2
             NameMon = "Shandas"
             CFrameQuest = CFrame.new(-7863.63672, 5545.49316, -379.826324, 0.362120807, -1.98046344e-08, -0.93213129, 4.05822291e-08, 1, -5.48095125e-09, 0.93213129, -3.58431969e-08, 0.362120807)
             CFrameMon = CFrame.new(-7685.12354, 5601.05127, -443.171509, 0.150056243, 1.79768236e-08, -0.988677442, 6.67798661e-09, 1, 1.91962481e-08, 0.988677442, -9.48289181e-09, 0.150056243)
       elseif MyLevel == 525 or MyLevel <= 549 then -- Royal Squad
             Ms = "Royal Squad [Lv. 525]"
             NaemQuest = "SkyExp2Quest"
             LevelQuest = 1
             NameMon = "Royal Squad"
             CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
             CFrameMon = CFrame.new(-7685.02051, 5606.87842, -1442.729, 0.561947823, 7.69527464e-09, -0.827172697, -4.24974544e-09, 1, 6.41599973e-09, 0.827172697, -9.01838604e-11, 0.561947823)
       elseif MyLevel == 550 or MyLevel <= 624 then -- Royal Soldier
             Ms = "Royal Soldier [Lv. 550]"
             NaemQuest = "SkyExp2Quest"
             LevelQuest = 2
             NameMon = "Royal Soldier"
             CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
             CFrameMon = CFrame.new(-7864.44775, 5661.94092, -1708.22351, 0.998389959, 2.28686137e-09, -0.0567218624, 1.99431383e-09, 1, 7.54200258e-08, 0.0567218624, -7.54117195e-08, 0.998389959)
       elseif MyLevel == 625 or MyLevel <= 649 then -- Galley Pirate
             Ms = "Galley Pirate [Lv. 625]"
             NaemQuest = "FountainQuest"
             LevelQuest = 1
             NameMon = "Galley Pirate"
             CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
             CFrameMon = CFrame.new(5595.06982, 41.5013695, 3961.47095, -0.992138803, -2.11610267e-08, -0.125142589, -1.34249509e-08, 1, -6.26613996e-08, 0.125142589, -6.04887518e-08, -0.992138803)
       elseif MyLevel >= 650 then -- Galley Captain
             Ms = "Galley Captain [Lv. 650]"
             NaemQuest = "FountainQuest"
             LevelQuest = 2
             NameMon = "Galley Captain"
             CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
             CFrameMon = CFrame.new(5658.5752, 38.5361786, 4928.93506, -0.996873081, 2.12391046e-06, -0.0790185928, 2.16989656e-06, 1, -4.96097414e-07, 0.0790185928, -6.66008248e-07, -0.996873081)
       end
    end
    if NewWorld then
       if MyLevel == 700 or MyLevel <= 724 then -- Raider [Lv. 700]
             Ms = "Raider [Lv. 700]"
             NaemQuest = "Area1Quest"
             LevelQuest = 1
             NameMon = "Raider"
             CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
             CFrameMon = CFrame.new(-737.026123, 39.1748352, 2392.57959, 0.272128761, 0, -0.962260842, -0, 1, -0, 0.962260842, 0, 0.272128761)
       elseif MyLevel == 725 or MyLevel <= 774 then -- Mercenary [Lv. 725]
             Ms = "Mercenary [Lv. 725]"
             NaemQuest = "Area1Quest"
             LevelQuest = 2
             NameMon = "Mercenary"
             CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
             CFrameMon = CFrame.new(-973.731995, 95.8733215, 1836.46936, 0.999135971, 2.02326991e-08, -0.0415605344, -1.90767793e-08, 1, 2.82094952e-08, 0.0415605344, -2.73922804e-08, 0.999135971)
       elseif MyLevel == 775 or MyLevel <= 799 then -- Swan Pirate [Lv. 775]
             Ms = "Swan Pirate [Lv. 775]"
             NaemQuest = "Area2Quest"
             LevelQuest = 1
             NameMon = "Swan Pirate"
             CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
             CFrameMon = CFrame.new(970.369446, 142.653198, 1217.3667, 0.162079468, -4.85452638e-08, -0.986777723, 1.03357589e-08, 1, -4.74980872e-08, 0.986777723, -2.50063148e-09, 0.162079468)
       elseif MyLevel == 800 or MyLevel <= 874 then -- Factory Staff [Lv. 800]
             Ms = "Factory Staff [Lv. 800]"
             NaemQuest = "Area2Quest"
             LevelQuest = 2
             NameMon = "Factory Staff"
             CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
             CFrameMon = CFrame.new(296.786499, 72.9948196, -57.1298141, -0.876037002, -5.32364979e-08, 0.482243896, -3.87658332e-08, 1, 3.99718729e-08, -0.482243896, 1.63222538e-08, -0.876037002)
       elseif MyLevel == 875 or MyLevel <= 899 then -- Marine Lieutenant [Lv. 875]
             Ms = "Marine Lieutenant [Lv. 875]"
             NaemQuest = "MarineQuest3"
             LevelQuest = 1
             NameMon = "Marine Lieutenant"
             CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
             CFrameMon = CFrame.new(-2913.26367, 73.0011826, -2971.64282, 0.910507619, 0, 0.413492233, 0, 1.00000012, 0, -0.413492233, 0, 0.910507619)
       elseif MyLevel == 900 or MyLevel <= 949 then -- Marine Captain [Lv. 900]
             Ms = "Marine Captain [Lv. 900]"
             NaemQuest = "MarineQuest3"
             LevelQuest = 2
             NameMon = "Marine Captain"
             CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
             CFrameMon = CFrame.new(-1868.67688, 73.0011826, -3321.66333, -0.971402287, 1.06502087e-08, 0.237439692, 3.68856199e-08, 1, 1.06050372e-07, -0.237439692, 1.11775684e-07, -0.971402287)
       elseif MyLevel == 950 or MyLevel <= 974 then -- Zombie [Lv. 950]
             Ms = "Zombie [Lv. 950]"
             NaemQuest = "ZombieQuest"
             LevelQuest = 1
             NameMon = "Zombie"
             CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
             CFrameMon = CFrame.new(-5634.83838, 126.067039, -697.665039, -0.992770672, 6.77618939e-09, 0.120025545, 1.65461245e-08, 1, 8.04023372e-08, -0.120025545, 8.18070234e-08, -0.992770672)
       elseif MyLevel == 975 or MyLevel <= 999 then -- Vampire [Lv. 975]
             Ms = "Vampire [Lv. 975]"
             NaemQuest = "ZombieQuest"
             LevelQuest = 2
             NameMon = "Vampire"
             CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
             CFrameMon = CFrame.new(-6030.32031, 6.4377408, -1313.5564, -0.856965423, 3.9138893e-08, -0.515373945, -1.12178942e-08, 1, 9.45958547e-08, 0.515373945, 8.68467822e-08, -0.856965423)
       elseif MyLevel == 1000 or MyLevel <= 1049 then -- Snow Trooper [Lv. 1000] **
             Ms = "Snow Trooper [Lv. 1000]"
             NaemQuest = "SnowMountainQuest"
             LevelQuest = 1
             NameMon = "Snow Trooper"
             CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
             CFrameMon = CFrame.new(535.893433, 401.457062, -5329.6958, -0.999524176, 0, 0.0308452044, 0, 1, -0, -0.0308452044, 0, -0.999524176)
       elseif MyLevel == 1050 or MyLevel <= 1099 then -- Winter Warrior [Lv. 1050]
             Ms = "Winter Warrior [Lv. 1050]"
             NaemQuest = "SnowMountainQuest"
             LevelQuest = 2
             NameMon = "Winter Warrior"
             CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
             CFrameMon = CFrame.new(1223.7417, 454.575226, -5170.02148, 0.473996818, 2.56845354e-08, 0.880526543, -5.62456428e-08, 1, 1.10811016e-09, -0.880526543, -5.00510211e-08, 0.473996818)
       elseif MyLevel == 1100 or MyLevel <= 1124 then -- Lab Subordinate [Lv. 1100]
             Ms = "Lab Subordinate [Lv. 1100]"
             NaemQuest = "IceSideQuest"
             LevelQuest = 1
             NameMon = "Lab Subordinate"
             CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
             CFrameMon = CFrame.new(-5769.2041, 37.9288292, -4468.38721, -0.569419742, -2.49055017e-08, 0.822046936, -6.96206541e-08, 1, -1.79282633e-08, -0.822046936, -6.74401548e-08, -0.569419742)
       elseif MyLevel == 1125 or MyLevel <= 1174 then -- Horned Warrior [Lv. 1125]
             Ms = "Horned Warrior [Lv. 1125]"
             NaemQuest = "IceSideQuest"
             LevelQuest = 2
             NameMon = "Horned Warrior"
             CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
             CFrameMon = CFrame.new(-6400.85889, 24.7645149, -5818.63574, -0.964845479, 8.65926566e-08, -0.262817472, 3.98261392e-07, 1, -1.13260398e-06, 0.262817472, -1.19745812e-06, -0.964845479)
       elseif MyLevel == 1175 or MyLevel <= 1199 then -- Magma Ninja [Lv. 1175]
             Ms = "Magma Ninja [Lv. 1175]"
             NaemQuest = "FireSideQuest"
             LevelQuest = 1
             NameMon = "Magma Ninja"
             CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
             CFrameMon = CFrame.new(-5496.65576, 58.6890411, -5929.76855, -0.885073781, 0, -0.465450764, 0, 1.00000012, -0, 0.465450764, 0, -0.885073781)
       elseif MyLevel == 1200 or MyLevel <= 1249 then -- Lava Pirate [Lv. 1200]
             Ms = "Lava Pirate [Lv. 1200]"
             NaemQuest = "FireSideQuest"
             LevelQuest = 2
             NameMon = "Lava Pirate"
             CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
             CFrameMon = CFrame.new(-5169.71729, 34.1234779, -4669.73633, -0.196780294, 0, 0.98044765, 0, 1.00000012, -0, -0.98044765, 0, -0.196780294)
       elseif MyLevel == 1250 or MyLevel <= 1274 then -- Ship Deckhand [Lv. 1250]
             Ms = "Ship Deckhand [Lv. 1250]"
             NaemQuest = "ShipQuest1"
             LevelQuest = 1
             NameMon = "Ship Deckhand"
             CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
             CFrameMon = CFrame.new(1163.80872, 138.288452, 33058.4258, -0.998580813, 5.49076979e-08, -0.0532564968, 5.57436763e-08, 1, -1.42118655e-08, 0.0532564968, -1.71604082e-08, -0.998580813)
       elseif MyLevel == 1275 or MyLevel <= 1299 then -- Ship Engineer [Lv. 1275]
             Ms = "Ship Engineer [Lv. 1275]"
             NaemQuest = "ShipQuest1"
             LevelQuest = 2
             NameMon = "Ship Engineer"
             CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
             CFrameMon = CFrame.new(916.666504, 44.0920448, 32917.207, -0.99746871, -4.85034697e-08, -0.0711069331, -4.8925461e-08, 1, 4.19294288e-09, 0.0711069331, 7.66126895e-09, -0.99746871)
       elseif MyLevel == 1300 or MyLevel <= 1324 then -- Ship Steward [Lv. 1300]
             Ms = "Ship Steward [Lv. 1300]"
             NaemQuest = "ShipQuest2"
             LevelQuest = 1
             NameMon = "Ship Steward"
             CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
             CFrameMon = CFrame.new(918.743286, 129.591064, 33443.4609, -0.999792814, -1.7070947e-07, -0.020350717, -1.72559169e-07, 1, 8.91351277e-08, 0.020350717, 9.2628369e-08, -0.999792814)
       elseif MyLevel == 1325 or MyLevel <= 1349 then -- Ship Officer [Lv. 1325]
          Ms = "Ship Officer [Lv. 1325]"
          NaemQuest = "ShipQuest2"
          LevelQuest = 2
          NameMon = "Ship Officer"
          CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
          CFrameMon = CFrame.new(786.051941, 181.474106, 33303.2969, 0.999285698, -5.32193063e-08, 0.0377905183, 5.68968588e-08, 1, -9.62386864e-08, -0.0377905183, 9.83201005e-08, 0.999285698)
       elseif MyLevel == 1350 or MyLevel <= 1374 then -- Arctic Warrior [Lv. 1350]
          Ms = "Arctic Warrior [Lv. 1350]"
          NaemQuest = "FrostQuest"
          LevelQuest = 1
          NameMon = "Arctic Warrior"
          CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
          CFrameMon = CFrame.new(5995.07471, 57.3188477, -6183.47314, 0.702747107, -1.53454167e-07, -0.711440146, -1.08168464e-07, 1, -3.22542007e-07, 0.711440146, 3.03620908e-07, 0.702747107)
       elseif MyLevel == 1375 or MyLevel <= 1424 then -- Snow Lurker [Lv. 1375]
          Ms = "Snow Lurker [Lv. 1375]"
          NaemQuest = "FrostQuest"
          LevelQuest = 2
          NameMon = "Snow Lurker"
          CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
          CFrameMon = CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393)
       elseif MyLevel == 1425 or MyLevel <= 1449 then -- Sea Soldier [Lv. 1425]
          Ms = "Sea Soldier [Lv. 1425]"
          NaemQuest = "ForgottenQuest"
          LevelQuest = 1
          NameMon = "Sea Soldier"
          CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
          CFrameMon = CFrame.new(-3029.78467, 66.944252, -9777.38184, -0.998552859, 1.09555076e-08, 0.0537791774, 7.79564235e-09, 1, -5.89660658e-08, -0.0537791774, -5.84614881e-08, -0.998552859)
       elseif MyLevel >= 1450 then -- Water Fighter [Lv. 1450]
          Ms = "Water Fighter [Lv. 1450]"
          NaemQuest = "ForgottenQuest"
          LevelQuest = 2
          NameMon = "Water Fighter"
          CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
          CFrameMon = CFrame.new(-3262.00098, 298.699615, -10553.6943, -0.233570755, -4.57538185e-08, 0.972339869, -5.80986068e-08, 1, 3.30992194e-08, -0.972339869, -4.87605725e-08, -0.233570755)
       end
    elseif Third then
        if MyLevel == 1500 or MyLevel <= 1524 then
           Ms = "Pirate Millionaire [Lv. 1500]"
          NaemQuest = "PiratePortQuest"
          LevelQuest = 1
          NameMon = "Pirate Millionaire"
          CFrameQuest = CFrame.new(-290.169861, 39.691246, 5581.43408, 0.25875926, 0, 0.965941846, 0, 1, 0, -0.965941846, 0, 0.25875926)
          CFrameMon = CFrame.new(-350.896179, 35.8283691, 5799.72607, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
        elseif MyLevel == 1525 or MyLevel <= 1574 then
       Ms = "Pistol Billionaire [Lv. 1525]"
          NaemQuest = "PiratePortQuest"
          LevelQuest = 2
          
          NameMon = "Pistol Billionaire"
          CFrameQuest = CFrame.new(-290.169861, 39.691246, 5581.43408, 0.25875926, 0, 0.965941846, 0, 1, 0, -0.965941846, 0, 0.25875926)
          CFrameMon = CFrame.new(-350.896179, 35.8283691, 5799.72607, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
        elseif MyLevel == 1575  or MyLevel <= 1599  then
            Ms = "Dragon Crew Warrior [Lv. 1575]"
          NaemQuest = "AmazonQuest"
          LevelQuest = 1
          NameMon = "Dragon Crew Warrior"
          CFrameQuest = CFrame.new(5832.79688, 53.2015953, -1101.43604, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
          CFrameMon = CFrame.new(6130.97705, 36.111084, -1175.04663, -1, 0, 0, 0, 1, 0, 0, 0, -1)  
        elseif MyLevel == 1600 or MyLevel <= 1624 then
             Ms = "Dragon Crew Archer [Lv. 1600]"
          NaemQuest = "AmazonQuest"
          LevelQuest = 2
          NameMon = "Dragon Crew Archer"
          CFrameQuest = CFrame.new(5832.79688, 53.2015953, -1101.43604, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
          CFrameMon = CFrame.new(6786.99609, 398.514587, 449.414917, 0.681973696, -0, -0.731376648, 0, 1, -0, 0.731376648, 0, 0.681973696)
        elseif MyLevel == 1625 or MyLevel <= 1649 then
          Ms = "Female Islander [Lv. 1625]"
          NaemQuest = "AmazonQuest2"
          
          LevelQuest = 1
          NameMon = "Female Islander"
          CFrameQuest = CFrame.new(5448.86133, 603.349365, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
          CFrameMon = CFrame.new(4659.69775, 647.820557, 834.697205, 0, 0, -1, 0, 1, 0, 1, 0, 0)
         elseif MyLevel == 1650 or MyLevel <= 1699 then
          Ms = "Giant Islander [Lv. 1650]"
          NaemQuest = "AmazonQuest2"
          
          LevelQuest = 2
          NameMon = "Giant Islander"
                    CFrameQuest = CFrame.new(5448.86133, 603.349365, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
          CFrameMon = CFrame.new(4869.33643, 596.635315, 37.1867523, -0.958187938, 0, -0.286139995, 0, 1, 0, 0.286139995, 0, -0.958187938)
         elseif MyLevel == 1700 or MyLevel <= 1724 then
            Ms = "Marine Commodore [Lv. 1700]"
          NaemQuest = "MarineTreeIsland"
          
          LevelQuest = 1
          NameMon = "Marine Commodore"
          CFrameQuest = CFrame.new(2180.54126, 30.3531189, -6741.55029, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
          CFrameMon = CFrame.new(2996.99634, 65.6201782, -7282.29541, 0.173624337, -0, -0.984811902, 0, 1, -0, 0.984811902, 0, 0.173624337) 
          elseif MyLevel == 1725 or MyLevel <= 1774 then
            Ms = "Marine Rear Admiral [Lv. 1725]"
          NaemQuest = "MarineTreeIsland"
          
          LevelQuest = 2
          NameMon = "Marine Rear Admiral"
          CFrameQuest = CFrame.new(2180.54126, 30.3531189, -6741.55029, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
          CFrameMon = CFrame.new(3695.38403, 155.158585, -7004.74805, -0.325602531, 0, -0.945506752, 0, 1, 0, 0.945506752, 0, -0.325602531) 
                     elseif MyLevel == 1775 or MyLevel <= 1800 then
            Ms = "Fishman Raider [Lv. 1775]"
          NaemQuest = "DeepForestIsland3"
          
          LevelQuest = 1
          NameMon = "Fishman Raider"
          CFrameQuest = CFrame.new(-10581.6563, 333.41037, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
          CFrameMon = CFrame.new(-10457.1738, 323.998352, -8450.38086, -1, 0, 0, 0, 1, 0, 0, 0, -1) 
         
                                 elseif MyLevel == 1800 or MyLevel <= 1824 then
            Ms = "Fishman Captain [Lv. 1800]"
          NaemQuest = "DeepForestIsland3"
          
          LevelQuest = 2
          NameMon = "Fishman Captain"
          CFrameQuest = CFrame.new(-10581.6563, 333.41037, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
          CFrameMon = CFrame.new(-11120.0332, 313.449188, -8791.31348, -1, 0, 0, 0, 1, 0, 0, 0, -1) 
                                            elseif MyLevel == 1825 or MyLevel <= 1849 then
            Ms = "Forest Pirate [Lv. 1825]"
          NaemQuest = "DeepForestIsland"
          
          LevelQuest = 1
          NameMon = "Forest Pirate"
          CFrameQuest = CFrame.new(-13234.04, 334.025909, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
          CFrameMon = CFrame.new(-13614.1426, 343.146973, -7756.50977, -0.515632391, 0, 0.856810033, 0, 1, 0, -0.856810033, 0, -0.515632391) 
                                                      elseif MyLevel == 1850 or MyLevel <= 1899 then
            Ms = "Mythological Pirate [Lv. 1850]"
          NaemQuest = "DeepForestIsland"
          
          LevelQuest = 2
          NameMon = "Mythological Pirate"
          CFrameQuest = CFrame.new(-13234.04, 334.025909, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
          CFrameMon = CFrame.new(-13681.8945, 420.407867, -7004.06641, -0.345898986, 0, 0.938271761, 0, 1, 0, -0.938271761, 0, -0.345898986) 
                                                                 elseif MyLevel == 1900 or MyLevel <= 1924 then
            Ms = "Jungle Pirate [Lv. 1900]"
          NaemQuest = "DeepForestIsland2"
          
          LevelQuest = 1
          NameMon = "Jungle Pirate"
          CFrameQuest = CFrame.new(-12680.3818, 392.508453, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
          CFrameMon = CFrame.new(-11861.918, 325.507813, -10098.6348, -1, 0, 0, 0, 1, 0, 0, 0, -1)
                                                                            elseif MyLevel >= 1925 then
            Ms = "Musketeer Pirate [Lv. 1925]"
          NaemQuest = "DeepForestIsland2"
          
          LevelQuest = 2
          NameMon = "Musketeer Pirate"
          CFrameQuest = CFrame.new(-12680.3818, 392.508453, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
          CFrameMon = CFrame.new(-13457.0059, 386.467651, -9819.51953, 0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, 0.374604106) 
       end
   
    end
 end
 CheckQuest()
 -----------------------------------------------------------------------------------------------------------------------------------------------
 local AutoFram = win:Tab("Auto Fram","http://www.roblox.com/asset/?id=7100202580")
 -- Equip Weapon
 SelectToolWeapon = ""
 function EquipWeapon(ToolSe)
    if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
       local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
       wait(.4)
       game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
    end
 end
 AutoFram:Toggle("Auto Farm","",_G.Save["AutoFarm"],function(vu)
     
   if  SelectToolWeapon == "" and vu then
       Flux:Notification("SelectWeapon First","OK")
   else
       _G.Save["AutoFarm"] = vu
       AFM = vu
       AFMMain = vu
       SaveSetting()
   end
 end)
 spawn(function()
    while wait() do
       if AFM then
           pcall(function()
               autofarm()
           end)
       end
    end
 end)
 game:GetService("RunService").Heartbeat:Connect(
    function()
       if AFM or Observation or AutoNew or Factory or Superhuman or DeathStep or Mastery or GunMastery or FramBoss or FramAllBoss or AutoBartilo or AutoNear or AutoRengoku or AutoSharkman or AutoFramEctoplasm or ST or _G.Tishita or Selctcan or _G.Training or HakiV2 or _G.v then
          if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
             game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
          end
       end
    end
    )
    local FarmQuest
    local GetQuest
   AutoFram:Toggle("Auto Quest","",_G.Save["AutoQuest"],function(a)
local args = {
  [1] = "AbandonQuest"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

       if a == true then
           _G.Save["AutoQuest"] = a
       GetQuest = false
       FarmQuest = true
       else
           _G.Save["AutoQuest"] = a
       GetQuest = true
       FarmQuest = false
       end
       SaveSetting()
   end)
   FastSpeed = 16
AutoFram:Slider("Select FastAttk Speed","",0,16,10,function(A)
   FastSpeed = A
end)
AutoFram:Toggle("FastAttk","",_G.Save["FastAttk"],function(a)
   FastAttk = a
   _G.Save["FastAttk"] = a
   SaveSetting()
end)
local c = game.Workspace.CurrentCamera
repeat wait() until game.Players.LocalPlayer.Character
local hed = game.Players.LocalPlayer.Character:WaitForChild("Head")
local r = math.random
local rad = math.rad
 local LocalPlayer = game:GetService("Players").LocalPlayer
 local VirtualUser = game:GetService('VirtualUser')
 function autofarm()
    if AFM then
       if LocalPlayer.PlayerGui.Main.Quest.Visible == GetQuest then
          StatrMagnet = false
          CheckQuest()
          print()
          LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
          wait(1.1)
          game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NaemQuest, LevelQuest)
       elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == FarmQuest then
          CheckQuest()
        LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
          if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
             pcall(
                function()
                   for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                      CheckQuest()
                      if v.Name == Ms then
                         repeat wait()
                             
                            EquipWeapon(SelectToolWeapon)
                            if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
                               if string.find(LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
                                  if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                     local args = {
                                           [1] = "Buso"
                                     }
                                     game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                  end
                                   if FastAttk then
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
     game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
     game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
     game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
   
  game:GetService'VirtualUser':Button1Down(Vector2.new(0.1, 0.1))
  else
  game:GetService'VirtualUser':Button1Down(Vector2.new(999, 999))
                                   end
                                   game.Players.LocalPlayer.Character.Humanoid:ChangeState(14)
                                  game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10,0)
                                  game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 0
                                  game.Players.LocalPlayer.Character.Humanoid.JumpPower = 0
                                  if HideHitBlox then
                                     v.HumanoidRootPart.Transparency = 1
                                  else
                                     v.HumanoidRootPart.Transparency = 0.75
                                  end
                                  v.HumanoidRootPart.CanCollide = false
                                  v.HumanoidRootPart.Size = Vector3.new(100, 100, 100)
                                  v.Head.CFrame = v.Head.CFrame
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999999)
                                  if Magnet then
                                       PosMon = v.HumanoidRootPart.CFrame
                                     StatrMagnet = true
                                  end
                                  v.HumanoidRootPart.CanCollide = false
                               else
                                
                                  StatrMagnet = false
                                  CheckQuest()
                                  print()
                                  LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
                                  wait(1.5)
                                  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NaemQuest, LevelQuest)
                               end
                            else
                               CheckQuest()
                            end
                         until not v.Parent or v.Humanoid.Health <= 0 or AFM == false or LocalPlayer.PlayerGui.Main.Quest.Visible == GetQuest
                         StatrMagnet = false
                         CheckQuest()
                      end
                   end
                end
             )
          else
             CheckQuest()
          end
       end
    end
 end
local RigC = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework) 
function stopweaponcd()
       pcall(function()
           RigC.activeController.timeToNextAttack = 0
       end)
end
pcall(function()
    spawn(function()
        while true do
            wait()
           stopweaponcd()
       end
   end)
end)
                       kkii = require(game.ReplicatedStorage.Util.CameraShaker)
 kkii:Stop()
       pcall(function()
           spawn(function()
               while true do
                   wait()
                   if AFM then
                       CheckQuest()
                       kkii = require(game.ReplicatedStorage.Util.CameraShaker)
 kkii:Stop()
                   if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.HumanoidRootPart)
                               box.Archivable = true
                                                                                         box.P = 0
                   end
                                       if not game.Workspace.Camera:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Workspace.Camera)
                               box.Archivable = true
                                                                                         box.P = 0
                   end
                                       if not game.Players.LocalPlayer.Character.LeftLowerArm:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.LeftLowerArm)
                               box.Archivable = true
                                                                                         box.P = 0
                                       end
                                                       if not game.Players.LocalPlayer.Character.LeftUpperArm:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.LeftUpperArm)
                               box.Archivable = true
                                                                                         box.P = 0
                                                       end
                                                                       if not game.Players.LocalPlayer.Character.Head:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.Head)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                       end
                                                                                       if not game.Players.LocalPlayer.Character.RightLowerArm:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.RightLowerArm)
                               box.Archivable = true                                                          
                               box.P = 0
                                                                                       end
                                                                                                       if not game.Players.LocalPlayer.Character.RightUpperArm:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.RightUpperArm)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                                                       end
                                                                                                                       if not game.Players.LocalPlayer.Character.LeftFoot:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.LeftFoot)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                                                                       end
                                                                                                                                       if not game.Players.LocalPlayer.Character.LeftFoot:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.LeftFoot)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                                                                                                                       end
                                                                                                                                       if not game.Players.LocalPlayer.Character.LeftLowerLeg:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.LeftLowerLeg)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                                                                                       end
                                                                                                                                                       if not game.Players.LocalPlayer.Character.LeftUpperLeg:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.LeftUpperLeg)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                                                                                                       end
                                                                                                                                                                       if not game.Players.LocalPlayer.Character.RightFoot:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.RightFoot)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                                                                                                                       end
                                                                                                                                                                                       if not game.Players.LocalPlayer.Character.RightLowerLeg:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.RightLowerLeg)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                                                                                                                                       end
                                                                                                                                                                                                       if not game.Players.LocalPlayer.Character.RightUpperLeg:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.RightUpperLeg)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                                                                                                         end
                                                                                                                                                                                                                       if not game.Players.LocalPlayer.Character.UpperTorso:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.UpperTorso)
                               box.Archivable = true
                                                                                         box.P = 0

                                                                                                                                                                                                                                       end
                                                                                                                                                                                    if not game.Players.LocalPlayer.Character.Humanoid:FindFirstChild("BodyVelocity") then
                               box = Instance.new('BodyVelocity',game.Players.LocalPlayer.Character.Humanoid)
                               box.Archivable = true
                                                                                         box.P = 0
                                                                                                                                                                                    end
                           if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.HumanoidRootPart)
                               box.Archivable = true
                               box.P = 0
                               box.D = 0
                   end
                                       if not game.Players.LocalPlayer.Character.LeftLowerArm:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.LeftLowerArm)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                       end
                                                       if not game.Players.LocalPlayer.Character.LeftUpperArm:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.LeftUpperArm)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                       end
                                                                       if not game.Players.LocalPlayer.Character.Head:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.Head)
                               box.Archivable = true
                               
                                                               box.P = 0
                               box.D = 0
                                                                       end
                                                                                       if not game.Players.LocalPlayer.Character.RightLowerArm:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.RightLowerArm)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                       end
                                                                                                       if not game.Players.LocalPlayer.Character.RightUpperArm:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.RightUpperArm)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                                       end
                                                                                                                       if not game.Players.LocalPlayer.Character.LeftFoot:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.LeftFoot)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                                                       end
                                                                                                                                       if not game.Players.LocalPlayer.Character.LeftFoot:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.LeftFoot)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                                                                       end
                                                                                                                                       if not game.Players.LocalPlayer.Character.LeftLowerLeg:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.LeftLowerLeg)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                                                                       end
                                                                                                                                                       if not game.Players.LocalPlayer.Character.LeftUpperLeg:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.LeftUpperLeg)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                                                                                       end
                                                                                                                                                                       if not game.Players.LocalPlayer.Character.RightFoot:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.RightFoot)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                                                                                                       end
                                                                                                                                                                                       if not game.Players.LocalPlayer.Character.RightLowerLeg:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.RightLowerLeg)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                                                                                                                       end
                                                                                                                                                                                                       if not game.Players.LocalPlayer.Character.RightUpperLeg:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.RightUpperLeg)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                                                                                                                                       end
                                                                                                                                                                                                                       if not game.Players.LocalPlayer.Character.UpperTorso:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.UpperTorso)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0

                                                                                                                                                                                                                                       end
                                                                                                                                                                                    if not game.Players.LocalPlayer.Character.Humanoid:FindFirstChild("BodyPosition") then
                               box = Instance.new('BodyPosition',game.Players.LocalPlayer.Character.Humanoid)
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                                                                                                                                                                                    end
                       
                               box = Instance.new('BodyPosition',game.Workspace.Enemies:FindFirstChild(Ms))
                               box.Archivable = true
                                                               box.P = 0
                               box.D = 0
                               end
               end
           end)
       end)
 -- Auto New World
 AutoFram:Toggle("Auto New World","",_G.Save["AutoNew"],function(vu)
  AutoNew = vu
  _G.Save["AutoNew"] = vu
  SaveSetting()
end)
   --Auto New
AutoFram:Toggle("Auto New World 3 st","",_G.Save["AutoNew2"],function(a)
   ST = a
  _G.Save["AutoNew2"] = vu
  SaveSetting()
end)
function Newbn()
   if ST then
       game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
  local args = {
        [1] = "Buso"
  }
  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end
        local MyLevel = game.Players.localPlayer.Data.Level.Value
        if MyLevel >= 1525 and NewWorld then
            AFM = false
            HJ = true
if HJ == true then
   game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1938.46362, 7.63781738, 1734.47144, 0.29242152, 0, 0.95628953, 0, 1, 0, -0.95628953, 0, 0.29242152)
   wait(1)
local args = {
   [1] = "ZQuestProgress",
   [2] = "Begin"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
HJ = false
end
wait(1)
Newq = false
if Newq == false then
   wait(120)
   Newq = true
end
       New = true
       if New == true then
           for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                   if v.Name == "rip_indra [Lv. 1500] [Boss]" then
                       repeat wait()
                           game:GetService'VirtualUser':CaptureController()
                                  game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                   v.HumanoidRootPart.CanCollide = false
                                  v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                                  v.HumanoidRootPart.Transparency = 1
                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,15,0)
                       until Newq == true or ST == false
                       New = false
                       end
           end
               end
           if New == false then
               game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1946.14075, 4.97466373, -2591.95679, 0.815817952, 0, 0.578308821, 0, 1, 0, -0.578308821, 0, 0.815817952)
               wait(1)
local args = {
   [1] = "TravelZou"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

           end
       end
   end
end
spawn(function()
   while wait() do
       if ST then
           Newbn()
       end
   end
end)
spawn(function()
  while wait(.1) do
     if AutoNew then
game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
  local args = {
        [1] = "Buso"
  }
  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end
        local MyLevel = game.Players.localPlayer.Data.Level.Value
        if MyLevel >= 700 and OldWorld then
           AFM = false
           SelectToolWeapon = "Key"
           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(4849.29883, 5.65138149, 719.611877)
           wait(0.5)
           local args = {
              [1] = "DressrosaQuestProgress",
              [2] = "Detective"
           }
           game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
           wait(0.5)
           if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") then
              local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Key")
              wait(.4)
              game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
           end
           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1347.7124, 37.3751602, -1325.6488)
           wait(0.5)
           function click()
              game:GetService'VirtualUser':CaptureController()
              game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
           end
           if game.Workspace.Enemies:FindFirstChild("Ice Admiral [Lv. 700] [Boss]") and game.Workspace.Map.Ice.Door.CanCollide == false and game.Workspace.Map.Ice.Door.Transparency == 1 then
              CheckBoss = true
              SelectToolWeapon = SelectToolWeaponOld
              for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                 if CheckBoss and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == "Ice Admiral [Lv. 700] [Boss]" then
                    repeat wait(.1)
                       pcall(function() 
                          v.HumanoidRootPart.Transparency = 0.5
                          v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
                          v.HumanoidRootPart.BrickColor = BrickColor.new("White")
                          v.HumanoidRootPart.CanCollide = false
                          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame*CFrame.new(0, 10, 10)
                          click()
                       end)
                    until not CheckBoss or not v.Parent or v.Humanoid.Health <= 0 or AutoNew == false
                 end
              end
              CheckBoss = false
              wait(0.5)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1166.23743, 7.65220165, 1728.36487)
              wait(0.5)
              local args = {
                  [1] = "TravelDressrosa" -- OLD WORLD to NEW WORLD
              }
              game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
           else
              if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") then
                 local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Key")
                 wait(.4)
                 game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
              end
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1347.7124, 37.3751602, -1325.6488)
           end 
        end
     end 
  end
end)
Checka = true
AutoFram:Toggle("Auto Canvandit Sworld + Hop","",_G.Save["AutoCavandit"],function(A)
   _G.Canvandit = A
   _G.Save["AutoCavandit"] = A
   SaveSetting()
   while _G.Canvandit do wait()
       if Checka == true then
           game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5310.53027, 18.8935547, 110.599594, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
           Checka = false
       end
       if Checka == false then
           for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
               if v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" then
                   repeat wait()
                       v.HumanoidRootPart.Size = Vector3.new(35,35,35)
                       v.HumanoidRootPart.CanCollide = false
                       v.HumanoidRootPart.Transparency = 0
               game:GetService'VirtualUser':CaptureController()
              game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,20,5)
                   until v.Humanoid.Health <= 0 or _G.Canvandit == false
               if v.Humanoid.Health <= 0 then
                   Hop()
               end
               end
           end
       end
   end 
end)

 AutoFram:Toggle("Auto Saber","",_G.Save["AutoSeber"],function(Value)
  _G.AutoOpenSaber = Value
  _G.Save["AutoSeber"] = Value
  SaveSetting()
end)
spawn(function()
  while wait(.1) do
     if _G.AutoOpenSaber then
        local off = game:GetService("Workspace").Map.Jungle.Final:FindFirstChild("Part")
        local MyLevel = game.Players.localPlayer.Data.Level.Value
        if MyLevel >= 200 and AFM == true then
           repeat wait(.1)
              AFM = false
              function accept1()
                 local string_1 = "ProQuestProgress";
                 local string2 = "SickMan";
                 local Target = game:GetService("ReplicatedStorage").Remotes["CommF"];
                 Target:InvokeServer(string_1, string_2);
              end

              function accept2()
                 local string_1 = "ProQuestProgress";
                 local string2 = "RichSon";
                 local Target = game:GetService("ReplicatedStorage").Remotes["CommF"];
                 Target:InvokeServer(string_1, string2);
              end
              function saber()
                 if game:GetService("Workspace").Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                       if v.Name == "Mob Leader [Lv. 120] [Boss]" and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
                          repeat wait()
                             pcall(function()
                                if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                   local args = {
                                      [1] = "Buso"
                                   }
                                   game:GetService("ReplicatedStorage").Remotes.CommF:InvokeServer(unpack(args))
                                end
                                EquipWeapon(SelectToolWeapon)
                                v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
                                v.HumanoidRootPart.CanCollide = false
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame*CFrame.new(0, 10, 10)
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                             end)
                          until v.Humanoid.Health == 0
                       end
                    end
                 end

                 function accept3()
                    local string_1 = "ProQuestProgress";
                    local string2 = "RichSon";
                    local Target = game:GetService("ReplicatedStorage").Remotes["CommF"];
                    Target:InvokeServer(string_1, string_2);
                 end

                 wait(.1)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1421.87024, 55.4666862, 21.7750397)
                 wait(1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1647.19556, 29.1544189, 438.299408)
                 wait(1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1324.10144, 31.4560413, -461.404114)
                 wait(1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1152.38464, 9.74718285, -700.309875)
                 wait(1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1180.89563, 21.0007095, 187.861374)
                 wait(1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1610.00757, 11.5049858, 164.001587)
                 wait(2)
                 local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Torch")
                 wait(.4)
                 game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
                 wait(.1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1114.55762, 4.9214654, 4349.2334, -0.618430376, -1.56903435e-09, 0.785839617, -5.04992048e-09, 1, -1.97748973e-09, -0.785839617, -5.19136734e-09, -0.618430376)
                 wait(5.5)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1114.26721, 4.16943789, 4366.15332)
                 wait(1)
                 local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Cup")
                 wait(.4)
                 game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
                 wait(1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1397.0614, 37.3480072, -1321.03955, -0.0699888021, -5.05999473e-08, 0.997547925, -7.48410045e-08, 1, 4.54734241e-08, -0.997547925, -7.14748296e-08, -0.0699888021)
                 wait(4.5)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1457.87976, 88.2521744, -1390.39575)
                 wait(1.5)
                 accept1()
                 wait(1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-909.106689, 13.7520342, 4077.34888)
                 wait(1.1)
                 accept2()
                 wait(1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2852.90234, 7.56227827, 5367.72412)
                 wait(1.5)
                 EquipWeapon(SelectToolWeapon)
                 wait(1)
                 saber()
                 wait(2)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-909.106689, 13.7520342, 4077.34888)
                 wait(1.1)
                 accept3()
                 wait(1)
                 local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Relic")
                 wait(.4)
                 game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
wait(1)
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1405.84094, 29.8519993, 5.05432224, 0.859020233, -4.18967083e-08, 0.511941671, 4.07572731e-09, 1, 7.49999103e-08, -0.511941671, -6.23399004e-08, 0.859020233)
                 wait(1)
                 if off.CanCollide == false then
                    _G.AutoOpenSaber = false
                    AFM = true
                 end
              end
           until _G.AutoOpenSaber == false or off.CanCollide == false or _G.AFM == true

        elseif MyLevel >= 200 then
           repeat wait(.1)
              function accept1()
                 local string_1 = "ProQuestProgress";
                 local string2 = "SickMan";
                 local Target = game:GetService("ReplicatedStorage").Remotes["CommF"];
                 Target:InvokeServer(string_1, string_2);
              end

              function accept2()
                 local string_1 = "ProQuestProgress";
                 local string2 = "RichSon";
                 local Target = game:GetService("ReplicatedStorage").Remotes["CommF"];
                 Target:InvokeServer(string_1, string2);
              end
              function saber()
                 for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                    if v.Name == "Mob Leader [Lv. 120] [Boss]" then
                       repeat wait()
                          for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                             if v.Name == "Mob Leader [Lv. 120] [Boss]" then
                                if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                   local args = {
                                      [1] = "Buso"
                                   }
                                   game:GetService("ReplicatedStorage").Remotes.CommF:InvokeServer(unpack(args))
                                end
                                EquipWeapon(SelectToolWeapon)
                                v.HumanoidRootPart.CanCollide = false
                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,15,0)
                                game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                             end
                          end
                       until v.Humanoid.Health == 0
                    end
                 end
              end

              function accept3()
local string_1 = "ProQuestProgress";
                 local string2 = "RichSon";
                 local Target = game:GetService("ReplicatedStorage").Remotes["CommF"];
                 Target:InvokeServer(string_1, string_2);
              end

              wait(.1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1421.87024, 55.4666862, 21.7750397)
              wait(1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1647.19556, 29.1544189, 438.299408)
              wait(1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1324.10144, 31.4560413, -461.404114)
              wait(1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1152.38464, 9.74718285, -700.309875)
              wait(1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1180.89563, 21.0007095, 187.861374)
              wait(1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1610.00757, 11.5049858, 164.001587)
              wait(2)
              local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Torch")
              wait(.4)
              game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
              wait(.1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1114.55762, 4.9214654, 4349.2334, -0.618430376, -1.56903435e-09, 0.785839617, -5.04992048e-09, 1, -1.97748973e-09, -0.785839617, -5.19136734e-09, -0.618430376)
              wait(5.5)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1114.26721, 4.16943789, 4366.15332)
              wait(1)
              local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Cup")
              wait(.4)
              game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
              wait(1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1397.0614, 37.3480072, -1321.03955, -0.0699888021, -5.05999473e-08, 0.997547925, -7.48410045e-08, 1, 4.54734241e-08, -0.997547925, -7.14748296e-08, -0.0699888021)
              wait(4.5)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1457.87976, 88.2521744, -1390.39575)
              wait(1.5)
              accept1()
              wait(1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-909.106689, 13.7520342, 4077.34888)
              wait(1.1)
              accept2()
              wait(1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2852.90234, 7.56227827, 5367.72412)
              wait(1.5)
              EquipWeapon(SelectToolWeapon)
              wait(1)
              saber()
              wait(2)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-909.106689, 13.7520342, 4077.34888)
              wait(1.1)
              accept3()
              wait(1)
local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Relic")
              wait(.4)
              game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
              wait(1)
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1405.84094, 29.8519993, 5.05432224, 0.859020233, -4.18967083e-08, 0.511941671, 4.07572731e-09, 1, 7.49999103e-08, -0.511941671, -6.23399004e-08, 0.859020233)
              wait(1)
              if off.CanCollide == false then
                 _G.AutoOpenSaber = false
              end
           until G.AutoOpenSaber == false or off.CanCollide == false
           if game:GetService("Workspace").Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
              for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                 if v.Name == "Saber Expert [Lv. 200] [Boss]" and v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
                    repeat wait()
                       pcall(function()
                          if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                             local args = {
                                [1] = "Buso"
                             }
                             game:GetService("ReplicatedStorage").Remotes.CommF:InvokeServer(unpack(args))
                          end
                          EquipWeapon(SelectToolWeapon)
                          v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
                          v.HumanoidRootPart.CanCollide = false
                          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame*CFrame.new(0, 15, 10)
                          game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                          game:GetService'VirtualUser':CaptureController()
                          game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                          game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                       end)
                    until _G.AutoOpenSaber == true or v.Humanoid.Health <= 0
                 end
              end
           end
        end
     end
  end
end)
 AutoFram:Toggle("Auto Factory","",_G.Save["AutoFac"],function(vu)
    Factory = vu
    _G.Save["AutoFac"] = vu
    SaveSetting()
    while Factory do wait()
       if game.Workspace.Enemies:FindFirstChild("Core") then
          Core = true
          AFM = false
          for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
             if Core and v.Name == "Core" and v.Humanoid.Health > 0 then
                repeat wait(.1)
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(448.46756, 199.356781, -441.389252)
                   EquipWeapon(SelectToolWeapon)
                   game:GetService'VirtualUser':CaptureController()
                   game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                until not Core or v.Humanoid.Health <= 0  or Factory == false
             end
          end
       elseif game.ReplicatedStorage:FindFirstChild("Core") then
          Core = true
          AFM = false
          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(448.46756, 199.356781, -441.389252)
       elseif AFMMain then
          Core = false
          AFM = true
       end
    end
 end)
 AutoFram:Toggle("Auto Superhuman","",_G.Save["AutoSuperhuman"],function(vu)
    Superhuman = vu
    _G.Save["AutoSuperhuman"] = vu
    SaveSetting()
    spawn(function()
     while wait(.1) do
        if Superhuman then
           if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
              local args = {
                 [1] = "BuyBlackLeg"
              }
              game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
           end   
           if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") or game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") or game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") or game.Players.LocalPlayer.Character:FindFirstChild("Electro") or game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") or game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") or game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") or game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") then
              if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 299 then
                 SelectToolWeapon = "Black Leg"
              end
              if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 299 then
                 SelectToolWeapon = "Electro"
              end
              if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 299 then
                 SelectToolWeapon = "Fishman Karate"
              end
              if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 299 then
                 SelectToolWeapon = "Dragon Claw"
              end
              if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 then
                 local args = {
                    [1] = "BuyElectro"
                 }
                 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
              end
              if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 then
                 local args = {
                    [1] = "BuyElectro"
                 }
                 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
              end
              if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 then
                 local args = {
                    [1] = "BuyFishmanKarate"
                 }
                 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
              end
              if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 then
                 local args = {
                    [1] = "BuyFishmanKarate"
                 }
                 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
              end
              if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300 then
                  if Fully then
                      if game.Players.LocalPlayer.Data.Fragments.Value <= 1499 then
                          _G.autoraid = true
                      elseif game.Players.LocalPlayer.Data.Fragments.Value <= 1499 then
                           local args = {
                      [1] = "BlackbeardReward",
                      [2] = "DragonClaw",
                      [3] = "1"
                   }
                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                   local args = {
                      [1] = "BlackbeardReward",
                      [2] = "DragonClaw",
                      [3] = "2"
                   }
                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args)) 
                      end
                  elseif not Fully then
                        local args = {
                      [1] = "BlackbeardReward",
                      [2] = "DragonClaw",
                      [3] = "1"
                   }
                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                   local args = {
                      [1] = "BlackbeardReward",
                      [2] = "DragonClaw",
                      [3] = "2"
                   }
                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args)) 
                  end
               end
              if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 then
                 local args = {
                    [1] = "BuySuperhuman"
                 }
                 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
              end
              if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 then
                 local args = {
                    [1] = "BuySuperhuman"
                 }
                 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
              end
           end
        end
     end
  end)
 end)
 --Auto
 -- Auto Death Step
 AutoFram:Toggle("Auto Electric v2 ","",_G.Save["AutoElectric"],function(a)
     Electric = a
     _G.Save["AutoElectric"] = a 
     SaveSetting()
       while Electric do wait()
           if not game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") then
               local args = {
                    [1] = "BuyElectro"
                 }
               game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
               
           elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") then
               if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 399 then
                   SelectToolWeapon = "Electro"
               elseif  game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 then
               if FullyE then
                   if game.Players.LocalPlayer.Data.Fragments.Value >= 5000 then
                       AFM = false
                       _G.autoraid = false
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-10371.6201, 330.80191, -10131.6211, -0.804111481, 0, -0.594478488, 0, 1, 0, 0.594478488, 0, -0.804111481)
                   wait(1)
                   local args = {
                       [1] = "BuyElectricClaw",
                       [2] = "Start"
                   }
                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12550.4258, 331.903687, -7496.61035, 1, 0, 0, 0, 1, 0, 0, 0, 1)
                   wait(1)
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-10371.6201, 330.80191, -10131.6211, -0.804111481, 0, -0.594478488, 0, 1, 0, 0.594478488, 0, -0.804111481)
                   local args = {
                       [1] = "BuyElectricClaw"
                   }
                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                   AFM = true
                   elseif game.Players.LocalPlayer.Data.Fragments.Value <= 4999 and FullyE then
                       _G.autoraid = true
                   end
                   elseif not FullyE then
                                               AFM = false
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-10371.6201, 330.80191, -10131.6211, -0.804111481, 0, -0.594478488, 0, 1, 0, 0.594478488, 0, -0.804111481)
                   wait(1)
                   local args = {
                       [1] = "BuyElectricClaw",
                       [2] = "Start"
                   }
                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12550.4258, 331.903687, -7496.61035, 1, 0, 0, 0, 1, 0, 0, 0, 1)
                   wait(1)
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-10371.6201, 330.80191, -10131.6211, -0.804111481, 0, -0.594478488, 0, 1, 0, 0.594478488, 0, -0.804111481)
                   local args = {
                       [1] = "BuyElectricClaw"
                   }
                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                   AFM = true
                   end
               end
           end
       end
   end)
 AutoFram:Toggle("Auto DeathStep","",_G.Save["AutoDeathStep"],function(vu)
    DeathStep = vu
    _G.Save["AutoDeathStep"] = vu 
    SaveSetting()
    while DeathStep do wait()
       if DeathStep then
          if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") or game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") or game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") or game.Players.LocalPlayer.Character:FindFirstChild("Death Step") then
             if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 450 then
                local args = {
                      [1] = "Buy DeathStep"
                }
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                SelectToolWeapon = "Death Step"
             end
             if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 450 then
                local args = {
                      [1] = "Buy DeathStep"
                }
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

                SelectToolWeapon = "Death Step"
             end
             if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 449 then
                SelectToolWeapon = "Black Leg"
             end
          else
             local args = {
                [1] = "BuyBlackLeg"
             }
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
          end
       end
    end
 end)

 AutoFram:Toggle("Auto Yama","",_G.Save["AutoYama"],function(a)
     _G.Tishita = a
     _G.Save["AutoYama"] = a
     SaveSetting()
     while _G.Tishita do wait()
         game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5417.83545, 313.063538, -2823.35913, 0.927179396, 0, 0.374617696, 0, 1, 0, -0.374617696, 0, 0.927179396)
           if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
local args = {
   [1] = "EliteHunter"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
           elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
               for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
                   if v.Name == "Diablo [Lv. 1750]" or v.Name == "Urban [Lv. 1750]" or v.Name == "Deandre [Lv. 1750]" then
                       repeat wait()
                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
                       until _G.Tishita == false or game:GetService("Workspace").Enemies:FindFirstChild(v.Name)
                       
                   for _,v2 in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                       if v2.Name == "Diablo [Lv. 1750]" or v2.Name == "Urban [Lv. 1750]" or v2.Name == "Deandre [Lv. 1750]" then
                           repeat wait()
                           game:GetService'VirtualUser':CaptureController()
                                  game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                   v.HumanoidRootPart.CanCollide = false
                                  v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                                v.HumanoidRootPart.Transparency = 1
                          game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v2.HumanoidRootPart.CFrame * CFrame.new(0,20,0)
                           until _G.Tishita == false or v2.Humanoid.Health == 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
                               end
                           end
                       end
               end
           end
       end
 end)
 AutoFram:Toggle("Auto PlayersHunter","",_G.Save["AutoPlayerHunter"],function(a)
   _G.Training = a
   _G.Save["AutoPlayerHunter"] = a 
   SaveSetting()
   while _G.Training do wait()
       if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
 wait(1)
           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5417.83545, 313.063538, -2823.35913, 0.927179396, 0, 0.374617696, 0, 1, 0, -0.374617696, 0, 0.927179396)
game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
       elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
           for i,v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
               if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,v.Name) then
                   repeat wait()
                       game:GetService'VirtualUser':CaptureController()
                                  game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                         v.HumanoidRootPart.CanCollide = false
                                  v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                                v.HumanoidRootPart.Transparency = 1
                       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,20,0)
                   until _G.Training == false or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false or v.Humanoid.Health == 0
               end
           end
       end
   end
 end
)
 AutoFram:Toggle("Auto Buy LegendarySword","",_G.Save["AutoBuyLegen"],function(Value)
    LegebdarySword = Value
    _G.Save["AutoBuyLegen"] = Value 
    SaveSetting()
    while LegebdarySword do wait()
       if LegebdarySword then
             local args = {
                [1] = "LegendarySwordDealer",
                [2] = "2"
             }
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
       end
    end
 end)
 
 AutoFram:Toggle("Auto Buy LegendarySword + Hop","",_G.Save["AutoBuyLegenHop"],function(Value)
  LegebdarySword = Value
  _G.Save["AutoBuyLegenHop"] = Value 
  SaveSetting()
  while LegebdarySword do wait()
     if LegebdarySword then
           local args = {
              [1] = "LegendarySwordDealer",
              [2] = "2"
           }
           game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
         wait(1)
         local PlaceID = game.PlaceId
  local AllIDs = {}
  local foundAnything = ""
  local actualHour = os.date("!*t").hour
  local Deleted = false
  function TPReturner()
     local Site;
     if foundAnything == "" then
        Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
     else
        Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
     end
     local ID = ""
     if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
        foundAnything = Site.nextPageCursor
     end
     local num = 0;
     for i,v in pairs(Site.data) do
        local Possible = true
        ID = tostring(v.id)
        if tonumber(v.maxPlayers) > tonumber(v.playing) then
           for _,Existing in pairs(AllIDs) do
              if num ~= 0 then
                    if ID == tostring(Existing) then
                       Possible = false
                    end
              else
                    if tonumber(actualHour) ~= tonumber(Existing) then
                       local delFile = pcall(function()
                          -- delfile("NotSameServers.json")
                          AllIDs = {}
                          table.insert(AllIDs, actualHour)
                       end)
                    end
              end
              num = num + 1
           end
           if Possible == true then
              table.insert(AllIDs, ID)
              wait()
              pcall(function()
                    -- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
                    wait()
                    game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
              end)
              wait(4)
           end
        end
     end
  end
  function Teleport()
     while wait() do
        pcall(function()
           TPReturner()
           if foundAnything ~= "" then
              TPReturner()
           end
        end)
     end
  end
  Teleport()
     end
  end
end)
 AutoFram:Toggle("Auto Buy Enhancement","",_G.Save["AutoEnhan"],function(Value)
    Enhancement = Value
    _G.Save["AutoEnhan"] = Value 
    SaveSetting()
    while Enhancement do wait()
       if Enhancement then
          local args = {
             [1] = "ColorsDealer",
             [2] = "2"
          }
          game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
       end
    end
 end)
  Wapon = {}
 for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
    if v:IsA("Tool") then
       table.insert(Wapon ,v.Name)
    end
 end
 for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
    if v:IsA("Tool") then
       table.insert(Wapon, v.Name)
    end
 end
 local SelectWeapona = AutoFram:Dropdown("Select Weapon",Wapon,function(Value)
    SelectToolWeapon = Value
    _G.Save["SelctToolFarm"] = Value
    SelectToolWeaponOld = Value
    SaveSetting()
 end)
 SelectToolWeapon = _G.Save["SelctToolFarm"]
 AutoFram:Button("Refresh Weapon","",function()
    SelectToolWeapon = ""
    SelectWeapona:Clear()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
       if v:IsA("Tool") then
          SelectWeapona:Add(v.Name)
       end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
       if v:IsA("Tool") then
          SelectWeapona:Add(v.Name)
       end
    end
 end)
 AutoFram:Toggle("Auto Collect Fist of DarkNess (Every 4 Hours)","",_G.Save["AutoCollectFirst"],function(a)
  if OldWorld then
     Flux:Notification("Use in NewWorld","OK")
  else
     _G.Save["AutoCollectFirst"] = a
     DrakFist = a
     SaveSetting()
  end
end)
spawn(function()
  while wait() do  
     if DrakFist then
        wait(14400)
        for i,v in pairs(game:GetDescendants()) do
           if v.ClassName == "Part" then
              repeat wait()
           local tr = game:GetService('TweenService')
           local nn = game.Players.LocalPlayer.Character
           local part = nn.HumanoidRootPart
           local ti = TweenInfo.new(2, Enum.EasingStyle.Linear)
           local tp = {CFrame = v.Parent.CFrame}
           tr:Create(part,ti,tp):Play()
              until game.Players.LocalPlayer.Backpack:FindFirstChild("Fist of Darkness") or DarkDist == false
           end
        end
     end 
  end
end)
 AutoFram:Line()

 AutoFram:Label("Auto Accessories")
 
 WaponAccessories = {}
 for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
    if v:IsA("Tool") then
       if v.ToolTip == "Wear" then
          table.insert(WaponAccessories, v.Name)
       end
    end
 end
 SelectTooAccessories = ""
 AutoFram:Toggle("Auto Accessories","",_G.Save["AutoAccessories"],function(Value)
    if SelectTooAccessories == "" and Value then
       Flux:Notification("Select Accessories First","OK")
    else
       _G.Save["AutoAccessories"] = Value
       AutoAccessories = Value
       SaveSetting()
    end
 end)
 spawn(function()
    while wait() do
       if AutoAccessories then
          CheckAccessories = game.Players.LocalPlayer.Character
          if game.Players.LocalPlayer.Character:FindFirstChild("Humanoid") and game.Players.LocalPlayer.Character:FindFirstChild("Humanoid").Health > 0 then
             if CheckAccessories:FindFirstChild("CoolShades") or CheckAccessories:FindFirstChild("BlackSpikeyCape") or CheckAccessories:FindFirstChild("BlueSpikeyCape") or CheckAccessories:FindFirstChild("RedSpikeyCape") or CheckAccessories:FindFirstChild("Chopper") or CheckAccessories:FindFirstChild("MarineCape") or CheckAccessories:FindFirstChild("GhoulMask") or CheckAccessories:FindFirstChild("MarineCap") or CheckAccessories:FindFirstChild("PinkCape") or CheckAccessories:FindFirstChild("SaboTopHat") or CheckAccessories:FindFirstChild("SwanGlasses") or CheckAccessories:FindFirstChild("UsoapHat") or CheckAccessories:FindFirstChild("Corrida") or CheckAccessories:FindFirstChild("ZebraCap") or CheckAccessories:FindFirstChild("TomoeRing") or CheckAccessories:FindFirstChild("BlackCape") or CheckAccessories:FindFirstChild("SwordsmanHat") or CheckAccessories:FindFirstChild("SantaHat") or CheckAccessories:FindFirstChild("ElfHat") or CheckAccessories:FindFirstChild("DarkCoat") then
             else
                EquipWeapon(SelectTooAccessories)
                wait(0.1)
                game:GetService'VirtualUser':CaptureController()
                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                wait(0.1)
                if game.Players.LocalPlayer.Character:FindFirstChild(SelectTooAccessories) then
                   game.Players.LocalPlayer.Character:FindFirstChild(SelectTooAccessories).Parent = game.Players.LocalPlayer:FindFirstChild("Backpack")
                end
                wait(1)
             end
          end
       end
    end
 end)
 local SelectAccessories = AutoFram:Dropdown("Select Accessories",WaponAccessories,function(Value)
    SelectTooAccessories = Value
    _G.Save["SelctAccessories"] = Value
    SaveSetting()
 end)
 AutoFram:Button("Refresh Accessories","",function()
    SelectAccessories:Clear()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
       if v:IsA("Tool") then
          if v.ToolTip == "Wear" then
             SelectAccessories:Add(v.Name)
          end
       end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
       if v:IsA("Tool") then
          if v.ToolTip == "Wear" then
             SelectAccessories:Add(v.Name)
          end
       end
    end
 end)
 -- Mastery Tab
   AutoFram:Line()
 AutoFram:Label("MasteryFram")
 game:GetService("RunService").Heartbeat:Connect(
    function()
       if Mastery then
          game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
       end
       if GunMastery then
          game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
       end
    end
 )
 WeaponMastery = ""
 AutoFram:Toggle("Auto Farm Mastery DevilFruit","",_G.Save["AutoDevilFruitMastery"],function(v)
    if WeaponMastery == "" and v then
       Flux:Notification("Select Weapon First","OK")
    else
        _G.Save["AutoDevilFruitMastery"] = v
        SaveSetting()
       CheckQuest()
       Mastery = v
       Ms = ""
    end
    while Mastery do wait()
       AutoDevilFruitMastery()
    end
 end)
 function AutoDevilFruitMastery()
    if Mastery then
       if LocalPlayer.PlayerGui.Main.Quest.Visible == false then
          StatrMagnetDevilFruitMastery = false
          CheckQuest()
          print()
          LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
          wait(1.1)
          game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NaemQuest, LevelQuest)
       elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
          CheckQuest()
          LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
          if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
             pcall(
                function()
                   for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                      CheckQuest()
                      if v.Name == Ms then
                         repeat wait() CheckQuest()
                            if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
                               if string.find(LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
                                  if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                     local args = {
                                           [1] = "Buso"
                                     }
                                     game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                  end
                                  HealthMin = v.Humanoid.MaxHealth*Persen/100
                                  PosMon = v.HumanoidRootPart.CFrame
                                  if v.Humanoid.Health <= HealthMin then
                                     UseDF = true
                                     EquipWeapon(game.Players.LocalPlayer.Data.DevilFruit.Value)
                                     v.HumanoidRootPart.CanCollide = false
                                     v.HumanoidRootPart.Size = Vector3.new(2, 2, 1)
                                     v.HumanoidRootPart.Transparency = 0.75
                                     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,0,20)
                                     if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon-Dragon") then
                                        if SkillZ and v.Humanoid.Health <= HealthMin then
                                           local args = {
                                              [1] = v.HumanoidRootPart.Position
                                           }
                                           game:GetService("Players").LocalPlayer.Character["Dragon-Dragon"].RemoteEvent:FireServer(unpack(args))
                                           local args = {
                                              [1] = "Z",
                                              [2] = Vector3.new(0,0,0)
                                           }
                                           game:GetService("Players").LocalPlayer.Character["Dragon-Dragon"].RemoteFunction:InvokeServer(unpack(args))
                                        end
                                        if SkillX and v.Humanoid.Health <= HealthMin then
                                           local args = {
                                              [1] = v.HumanoidRootPart.Position
                                           }
                                           game:GetService("Players").LocalPlayer.Character["Dragon-Dragon"].RemoteEvent:FireServer(unpack(args))
                                           local args = {
                                              [1] = "X"
                                           }
                                           game:GetService("Players").LocalPlayer.Character["Dragon-Dragon"].RemoteFunction:InvokeServer(unpack(args))
                                        end
                                     elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild(game.Players.LocalPlayer.Data.DevilFruit.Value) then
                                        if SkillZ and v.Humanoid.Health <= HealthMin then
                                           local args = {
                                              [1] = v.HumanoidRootPart.Position
                                           }
                                           game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].RemoteEvent:FireServer(unpack(args))
                                           local args = {
                                              [1] = "Z",
                                              [2] = Vector3.new(0,0,0)
                                           }
                                           game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].RemoteFunction:InvokeServer(unpack(args))
                                        end
                                        if SkillX and v.Humanoid.Health <= HealthMin then
                                           local args = {
                                              [1] = v.HumanoidRootPart.Position
                                           }
                                           game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].RemoteEvent:FireServer(unpack(args))
                                           local args = {
                                              [1] = "X",
                                              [2] = Vector3.new(0,0,0)
                                           }

                                           game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].RemoteFunction:InvokeServer(unpack(args))
                                        end
                                        if SkillC and v.Humanoid.Health <= HealthMin then
                                           local args = {
                                              [1] = v.HumanoidRootPart.Position
                                           }
                                           game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].RemoteEvent:FireServer(unpack(args))
                                           local args = {
                                              [1] = "C",
                                              [2] = Vector3.new(0,0,0)
                                           }
                                           game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].RemoteFunction:InvokeServer(unpack(args))
                                        end
                                        if SkillV and v.Humanoid.Health <= HealthMin then
                                           local args = {
                                              [1] = v.HumanoidRootPart.Position
                                           }
                                           game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].RemoteEvent:FireServer(unpack(args))
                                           local args = {
                                              [1] = "V",
                                              [2] = Vector3.new(0,0,0)
                                           }
                                           game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].RemoteFunction:InvokeServer(unpack(args))
                                        end
                                     end
                                  else
                                     UseDF = false
                                     EquipWeapon(WeaponMastery)
                                     if HideHitBlox then
                                        v.HumanoidRootPart.Transparency = 1
                                     else
                                        v.HumanoidRootPart.Transparency = 0.75
                                     end
                                     v.HumanoidRootPart.CanCollide = false
                                     v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                                     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,15,0)
                                     game:GetService'VirtualUser':CaptureController()
                                     game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                  end
                                  StatrMagnetDevilFruitMastery = true
                               else
                                  StatrMagnet = false
                                  CheckQuest()
                                  print()
                                  LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
                                  wait(1.5)
                                  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NaemQuest, LevelQuest)
                               end
                            else
                               CheckQuest()
                               game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
                            end
                         until not v.Parent or v.Humanoid.Health <= 0 or AFM == false or LocalPlayer.PlayerGui.Main.Quest.Visible == false
                         StatrMagnetDevilFruitMastery = false
                         CheckQuest()
                         game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
                      end
                   end
                end
             )
          else
             CheckQuest()
             game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
          end
       end
    end
 end
 spawn(function()
    while wait() do
       for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
          if v:IsA("Tool") then
             if v:FindFirstChild("RemoteFunctionShoot") then
                SelectToolWeaponGun = v.Name
             end
          end
       end
    end
 end)
 AutoFram:Toggle("Auto Farm Gun Mastery","",false,function(v)
    if WeaponMastery == "" and v then
       Flux:Notification("Select Weapon First","ok")
    else
       CheckQuest()
       _G.Save["AutoGunMastery"] = v
       SaveSetting()
       GunMastery = v
       Ms = ""
    end
    while GunMastery do wait()
       AutoGunMastery()
    end
 end)
 function AutoGunMastery()
    if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
       CheckQuest()
       print()
       StatrMag  = true
       LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
       wait(1.1)
       game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NaemQuest, LevelQuest)
       wait(0.5)
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
    elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
       for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
       CheckQuest()
             pcall(function()
                if game.Workspace.Enemies:FindFirstChild(Ms) then
                   if GunMastery and v.Name == Ms then
                      repeat wait()
                         pcall(function()
                            if game.Workspace.Enemies:FindFirstChild(Ms) then
                               if string.find(LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
                                  HealthMin = v.Humanoid.MaxHealth*Persen/100
                                  if v.Humanoid.Health <= HealthMin then
                                     EquipWeapon(SelectToolWeaponGun)
                                     v.HumanoidRootPart.CanCollide = false
                                     v.HumanoidRootPart.Size = Vector3.new(2, 2, 1)
                                     v.HumanoidRootPart.Transparency = 0.75
                                     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,10,15)
                                     local args = {
                                        [1] = v.HumanoidRootPart.Position,
                                        [2] = v.HumanoidRootPart
                                     }
                                     game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
                                  else
                                     EquipWeapon(WeaponMastery)
                                     if HideHitBlox then
                                      v.HumanoidRootPart.Transparency = 1
                                      Statsar = true
                                   else
                                     Statsar = false
                                      v.HumanoidRootPart.Transparency = 0.75
                                   end
                                   v.HumanoidRootPart.CanCollide = false
                                   v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                                   if Magnet then
                                    
                                     PosMonF = v.HumanoidRootPart.CFrame
                                     game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = PosMon * CFrame.new(0, 15, 0)
                                   end
                                     v.HumanoidRootPart.CanCollide = false
                                     v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                                     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,15,0)
                                     game:GetService'VirtualUser':CaptureController()
                                     game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                  end
                                  StatrMag = false
                               else
                                  CheckQuest()
                                  print()
                                  LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
                                  wait(1.1)
                                  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NaemQuest, LevelQuest)
                                  wait(0.5)
                                  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
                               end
                            else
                               CheckQuest()
                               game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
                            end
                         end)
                      until game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false or GunMastery == false or v.Humanoid.Health <= 0 or not v.Parent or v.Humanoid.Health <= 0
                   end
                else
                   CheckQuest()
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
                end
             end)
       end
    end
 end
 Persen = 15
 AutoFram:Slider("Health",1,1,100,Persen,function(v)
    Persen = v
   _G.Save["Health"] = v
   SaveSetting()
 end)
 local AMS = AutoFram:Dropdown("Select Weapon",Wapon,function(v)
    WeaponMastery = v
    WeaponOldMastery = v
    _G.Save["SelctToolHun"] = v
    SaveSetting()
 end)
 AutoFram:Button("Refresh Weapon","",function()
    AMS:Clear()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
       if v:IsA("Tool") then
          AMS:Add(v.Name)
       end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
       if v:IsA("Tool") then
          AMS:Add(v.Name)
       end
    end
 end)
 -- Fram Boss Tab
   AutoFram:Line()
 AutoFram:Label("Auto Fram Boss")

 function CheckQuestBoss()
  if SelectBoss == "Diamond [Lv. 750] [Boss]" then
     MsBoss = "Diamond [Lv. 750] [Boss]"
     NaemQuestBoss = "Area1Quest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
     CFrameBoss = CFrame.new(-1736.26587, 198.627731, -236.412857, -0.997808516, 0, -0.0661673471, 0, 1, 0, 0.0661673471, 0, -0.997808516)
  elseif SelectBoss == "Jeremy [Lv. 850] [Boss]" then
     MsBoss = "Jeremy [Lv. 850] [Boss]"
     NaemQuestBoss = "Area2Quest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
     CFrameBoss = CFrame.new(2203.76953, 448.966034, 752.731079, -0.0217453763, 0, -0.999763548, 0, 1, 0, 0.999763548, 0, -0.0217453763)
  elseif SelectBoss == "Fajita [Lv. 925] [Boss]" then
     MsBoss = "Fajita [Lv. 925] [Boss]"
     NaemQuestBoss = "MarineQuest3"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
     CFrameBoss = CFrame.new(-2297.40332, 115.449463, -3946.53833, 0.961227536, -1.46645796e-09, -0.275756449, -2.3212845e-09, 1, -1.34094433e-08, 0.275756449, 1.35296352e-08, 0.961227536)
  elseif SelectBoss == "Don Swan [Lv. 1000] [Boss]" then
     MsBoss = "Don Swan [Lv. 1000] [Boss]"
     CFrameBoss = CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072)
  elseif SelectBoss == "Smoke Admiral [Lv. 1150] [Boss]" then
     MsBoss = "Smoke Admiral [Lv. 1150] [Boss]"
     NaemQuestBoss = "IceSideQuest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(-6059.96191, 15.9868021, -4904.7373, -0.444992423, -3.0874483e-09, 0.895534337, -3.64098796e-08, 1, -1.4644522e-08, -0.895534337, -3.91229982e-08, -0.444992423)
     CFrameBoss = CFrame.new(-5115.72754, 23.7664986, -5338.2207, 0.251453817, 1.48345061e-08, -0.967869282, 4.02796978e-08, 1, 2.57916977e-08, 0.967869282, -4.54708946e-08, 0.251453817)
  elseif SelectBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" then
     MsBoss = "Cursed Captain [Lv. 1325] [Raid Boss]"
     CFrameBoss = CFrame.new(916.928589, 181.092773, 33422, -0.999505103, 9.26310495e-09, 0.0314563364, 8.42916226e-09, 1, -2.6643713e-08, -0.0314563364, -2.63653774e-08, -0.999505103)
  elseif SelectBoss == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
     MsBoss = "Awakened Ice Admiral [Lv. 1400] [Boss]"
     NaemQuestBoss = "FrostQuest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(5669.33203, 28.2118053, -6481.55908, 0.921275556, -1.25320829e-08, 0.388910472, 4.72230788e-08, 1, -7.96414241e-08, -0.388910472, 9.17372489e-08, 0.921275556)
     CFrameBoss = CFrame.new(6407.33936, 340.223785, -6892.521, 0.49051559, -5.25310213e-08, -0.871432424, -2.76146022e-08, 1, -7.58250565e-08, 0.871432424, 6.12576301e-08, 0.49051559)
   elseif SelectBoss == "Tide Keeper [Lv. 1475] [Boss]" then
      MsBoss = "Tide Keeper [Lv. 1475] [Boss]"
      NaemQuestBoss = "ForgottenQuest"             
      LevelQuestBoss = 3
      CFrameQuestBoss = CFrame.new(-3053.89648, 236.881363, -10148.2324, -0.985987961, -3.58504737e-09, 0.16681771, -3.07832915e-09, 1, 3.29612559e-09, -0.16681771, 2.73641976e-09, -0.985987961)
      CFrameBoss = CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202)
     -- Old World
  elseif SelectBoss == "Saber Expert [Lv. 200] [Boss]" then
     MsBoss = "Saber Expert [Lv. 200] [Boss]"
     CFrameBoss = CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094)
  elseif SelectBoss == "The Gorilla King [Lv. 25] [Boss]" then
     MsBoss = "The Gorilla King [Lv. 25] [Boss]"
     NaemQuestBoss = "JungleQuest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
     CFrameBoss = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
  elseif SelectBoss == "Bobby [Lv. 55] [Boss]" then
     MsBoss = "Bobby [Lv. 55] [Boss]"
     NaemQuestBoss = "BuggyQuest1"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
     CFrameBoss = CFrame.new(-1147.65173, 32.5966301, 4156.02588, 0.956680477, -1.77109952e-10, -0.29113996, 5.16530874e-10, 1, 1.08897802e-09, 0.29113996, -1.19218679e-09, 0.956680477)
  elseif SelectBoss == "Yeti [Lv. 110] [Boss]" then
     MsBoss = "Yeti [Lv. 110] [Boss]"
     NaemQuestBoss = "SnowQuest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(1384.90247, 87.3078308, -1296.6825, 0.280209213, 2.72035177e-08, -0.959938943, -6.75690828e-08, 1, 8.6151708e-09, 0.959938943, 6.24481444e-08, 0.280209213)
     CFrameBoss = CFrame.new(1221.7356, 138.046906, -1488.84082, 0.349343032, -9.49245944e-08, 0.936994851, 6.29478194e-08, 1, 7.7838429e-08, -0.936994851, 3.17894653e-08, 0.349343032)
  elseif SelectBoss == "Mob Leader [Lv. 120] [Boss]" then
     MsBoss = "Mob Leader [Lv. 120] [Boss]"
     CFrameBoss = CFrame.new(-2848.59399, 7.4272871, 5342.44043, -0.928248107, -8.7248246e-08, 0.371961564, -7.61816636e-08, 1, 4.44474857e-08, -0.371961564, 1.29216433e-08, -0.928248107)
     --The Gorilla King [Lv. 25] [Boss]
  elseif SelectBoss == "Vice Admiral [Lv. 130] [Boss]" then
     MsBoss = "Vice Admiral [Lv. 130] [Boss]"
     NaemQuestBoss = "MarineQuest2"
     LevelQuestBoss = 2
     CFrameQuestBoss = CFrame.new(-5035.42285, 28.6520386, 4324.50293, -0.0611100644, -8.08395768e-08, 0.998130739, -1.57416586e-08, 1, 8.00271849e-08, -0.998130739, -1.08217701e-08, -0.0611100644)
     CFrameBoss = CFrame.new(-5078.45898, 99.6520691, 4402.1665, -0.555574954, -9.88630566e-11, 0.831466436, -6.35508286e-08, 1, -4.23449258e-08, -0.831466436, -7.63661632e-08, -0.555574954)
  elseif SelectBoss == "Warden [Lv. 175] [Boss]" then
     MsBoss = "Warden [Lv. 175] [Boss]"
     NaemQuestBoss = "ImpelQuest"
     LevelQuestBoss = 1
     CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
     CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
  elseif SelectBoss == "Chief Warden [Lv. 200] [Boss]" then
     MsBoss = "Chief Warden [Lv. 200] [Boss]"
     NaemQuestBoss = "ImpelQuest"
     LevelQuestBoss = 2
     CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
     CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
  elseif SelectBoss == "Flamingo [Lv. 225] [Boss]" then
     MsBoss = "Flamingo [Lv. 225] [Boss]"
     NaemQuestBoss = "ImpelQuest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
     CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
  elseif SelectBoss == "Magma Admiral [Lv. 350] [Boss]" then
     MsBoss = "Magma Admiral [Lv. 350] [Boss]"
     NaemQuestBoss = "MagmaQuest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(-5317.07666, 12.2721891, 8517.41699, 0.51175487, -2.65508806e-08, -0.859131515, -3.91131572e-08, 1, -5.42026761e-08, 0.859131515, 6.13418294e-08, 0.51175487)
     CFrameBoss = CFrame.new(-5530.12646, 22.8769703, 8859.91309, 0.857838571, 2.23414389e-08, 0.513919294, 1.53689133e-08, 1, -6.91265853e-08, -0.513919294, 6.71978384e-08, 0.857838571)
  elseif SelectBoss == "Fishman Lord [Lv. 425] [Boss]" then
     MsBoss = "Fishman Lord [Lv. 425] [Boss]"
     NaemQuestBoss = "FishmanQuest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(61123.0859, 18.5066795, 1570.18018, 0.927145958, 1.0624845e-07, 0.374700129, -6.98219367e-08, 1, -1.10790765e-07, -0.374700129, 7.65569368e-08, 0.927145958)
     CFrameBoss = CFrame.new(61351.7773, 31.0306778, 1113.31409, 0.999974668, 0, -0.00714713801, 0, 1.00000012, 0, 0.00714714266, 0, 0.999974549)
  elseif SelectBoss == "Wysper [Lv. 500] [Boss]" then
     MsBoss = "Wysper [Lv. 500] [Boss]"
     NaemQuestBoss = "SkyExp1Quest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(-7862.94629, 5545.52832, -379.833954, 0.462944925, 1.45838088e-08, -0.886386991, 1.0534996e-08, 1, 2.19553424e-08, 0.886386991, -1.95022007e-08, 0.462944925)
     CFrameBoss = CFrame.new(-7925.48389, 5550.76074, -636.178345, 0.716468513, -1.22915289e-09, 0.697619379, 3.37381434e-09, 1, -1.70304748e-09, -0.697619379, 3.57381835e-09, 0.716468513)
  elseif SelectBoss == "Thunder God [Lv. 575] [Boss]" then
     MsBoss = "Thunder God [Lv. 575] [Boss]"
     NaemQuestBoss = "SkyExp2Quest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(-7902.78613, 5635.99902, -1411.98706, -0.0361216255, -1.16895912e-07, 0.999347389, 1.44533963e-09, 1, 1.17024491e-07, -0.999347389, 5.6715117e-09, -0.0361216255)
     CFrameBoss = CFrame.new(-7917.53613, 5616.61377, -2277.78564, 0.965189934, 4.80563429e-08, -0.261550069, -6.73089886e-08, 1, -6.46515304e-08, 0.261550069, 8.00056768e-08, 0.965189934)
  elseif SelectBoss == "Cyborg [Lv. 675] [Boss]" then
     MsBoss = "Cyborg [Lv. 675] [Boss]"
     NaemQuestBoss = "FountainQuest"
     LevelQuestBoss = 3
     CFrameQuestBoss = CFrame.new(5253.54834, 38.5361786, 4050.45166, -0.0112687312, -9.93677887e-08, -0.999936521, 2.55291371e-10, 1, -9.93769547e-08, 0.999936521, -1.37512213e-09, -0.0112687312)
     CFrameBoss = CFrame.new(6041.82813, 52.7112198, 3907.45142, -0.563162148, 1.73805248e-09, -0.826346457, -5.94632716e-08, 1, 4.26280238e-08, 0.826346457, 7.31437524e-08, -0.563162148)
  elseif SelectBoss == "Stone [Lv. 1550] [Boss]" then
      MsBoss = "Stone [Lv. 1550] [Boss]"
      NaemQuestBoss = "PiratePortQuest"
      LevelQuestBoss = 3
      CFrameQuestBoss = CFrame.new(-290.074768, 45.4408989, 5581.59033, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
      CFrameBoss = CFrame.new(-628.062195, 33.3545532, 6783.93848, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
  elseif SelectBoss == "Captain Elephant [Lv. 1875] [Boss]" then
       MsBoss = "Captain Elephant [Lv. 1875] [Boss]"
       NaemQuestBoss = "DeepForestIsland"
       LevelQuestBoss = 3
       CFrameQuestBoss = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
       CFrameBoss = CFrame.new(-13406.6875, 306.187927, -8394.31641, -1.1920929e-07, 0, 1.00000012, 0, 1, 0, -1.00000012, 0, -1.1920929e-07)
  elseif SelectBoss == "Island Empress [Lv. 1675] [Boss]" then
       MsBoss = "Island Empress [Lv. 1675] [Boss]"
       NaemQuestBoss = "AmazonQuest2"
       LevelQuestBoss = 3
       CFrameQuestBoss = CFrame.new(5448.86133, 603.349365, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
       CFrameBoss = CFrame.new(5543.10498, 598.135254, 197.907257, 1, 0, 0, 0, 1, 0, 0, 0, 1)
   
  end
end
Don = false
SelectToolWeaponBoss = ""
function EquipWeaponBoss()
  if game.Players.LocalPlayer.Backpack:FindFirstChild(SelectToolWeaponBoss) then
     local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(SelectToolWeaponBoss)
     wait(.4)
     game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
  end
end
local VirtualUser = game:GetService('VirtualUser')
function AutoFramBoss()
CheckQuestBoss()
if SelectBoss == "Don Swan [Lv. 1000] [Boss]" or SelectBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" or SelectBoss == "Saber Expert [Lv. 200] [Boss]" or SelectBoss == "Mob Leader [Lv. 120] [Boss]" or SelectBoss == "Darkbeard [Lv. 1000] [Raid Boss]" then
      if game:GetService("Workspace").Enemies:FindFirstChild(SelectBoss) then
         for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
            if FramBoss and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == MsBoss then
               repeat
                  pcall(function() wait() 
                     if HideHitBlox then
                           v.HumanoidRootPart.Transparency = 1
                     else
                           v.HumanoidRootPart.Transparency = 0.75
                     end
                     v.HumanoidRootPart.CanCollide = false
                     v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
                     game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 17, 5)
                     game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                     VirtualUser:CaptureController()
                     VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
                  end)
               until not FramBoss or not v.Parent or v.Humanoid.Health <= 0
            end
         end
      else
         game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameBoss
      end
   elseif SelectBoss == "Order [Lv. 1250] [Raid Boss]" then
      if game:GetService("Workspace").Enemies:FindFirstChild(SelectBoss) then
         for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
            if FramBoss and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == MsBoss then
               repeat
                  pcall(function() wait() 
                     if HideHitBlox then
                        v.HumanoidRootPart.Transparency = 1
                     else
                        v.HumanoidRootPart.Transparency = 0.75
                     end
                     v.HumanoidRootPart.CanCollide = false
                     v.HumanoidRootPart.Size = Vector3.new(80, 80, 80)
                     game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 25, 25)
                     game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                     VirtualUser:CaptureController()
                     VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
                  end)
               until not FramBoss or not v.Parent or v.Humanoid.Health <= 0
            end
         end
      else
         game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameBoss
      end
   else
      if game:GetService("Workspace").Enemies:FindFirstChild(SelectBoss) or game:GetService("ReplicatedStorage"):FindFirstChild(SelectBoss) then
         if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
            print()
            CheckQuestBoss()
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuestBoss
            wait(1.5)
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NaemQuestBoss, LevelQuestBoss)
            wait(1)
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameBoss
         elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
            for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
                  if FramBoss and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == MsBoss then
                     repeat
                        pcall(function() wait() 
                              if HideHitBlox then
                                 v.HumanoidRootPart.Transparency = 1
                              else
                                 v.HumanoidRootPart.Transparency = 0.75
                              end
                              v.HumanoidRootPart.CanCollide = false
                              v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
                              game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 17, 5)
                              game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                              VirtualUser:CaptureController()
                              VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
                        end)
                     until not FramBoss or not v.Parent or v.Humanoid.Health <= 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
                  end
            end
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameBoss
         end
      end
end
end
local Boss = {}
for i, v in pairs(game.ReplicatedStorage:GetChildren()) do
  if string.find(v.Name, "Boss") then
     if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
     else
        table.insert(Boss, v.Name)
     end
  end
end
for i, v in pairs(game.workspace.Enemies:GetChildren()) do
  if string.find(v.Name, "Boss") then
     if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
     else
        table.insert(Boss, v.Name)
     end
  end
end
AutoFram:Toggle(
 "Auto Farm Boss","",
 false
 ,
 function(Value)
     wait(.1)
     local args = {
         [1] = "AbandonQuest"
     }
     game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
     FramBoss = Value
 end
)
local BossName =
  AutoFram:Dropdown(
  "Select Boss",
  Boss,
  function(Value)
     SelectBoss = Value
     Don = false
  end
)
Wapon = {}
for i, v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
  if v:IsA("Tool") then
     table.insert(Wapon, v.Name)
  end
end
for i, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
  if v:IsA("Tool") then
     table.insert(Wapon, v.Name)
  end
end
local SelectWeaponBoss =
 AutoFram:Dropdown(
 "Select Weapon Kill Boss",
 Wapon,
 function(Value)
    SelectToolWeaponBoss = Value
 end
)
AutoFram:Button(
 "Refresh Weapon Boss","",
 function()
    SelectWeaponBoss:Clear()
    Wapon = {}
    for i, v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
       if v:IsA("Tool") then
          SelectWeaponBoss:Add(v.Name)
       end
    end
    for i, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
       if v:IsA("Tool") then
          SelectWeaponBoss:Add(v.Name)
       end
    end
 end
)
AutoFram:Button(
 "Refresh Boss","",
 function()
    Boss = {}
    BossName:Clear()
    for i, v in pairs(game.ReplicatedStorage:GetChildren()) do
       if string.find(v.Name, "Boss") then
          if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
          else
             BossName:Add(v.Name)
          end
       end
    end
    for i, v in pairs(game.workspace.Enemies:GetChildren()) do
       if string.find(v.Name, "Boss") then
          if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
          else
             BossName:Add(v.Name)
          end
       end
    end
 end
)

spawn(function()
  while wait(.1) do
     if FramBoss then
        EquipWeaponBoss()
     end
  end
end)
spawn(function()
  while wait(.1) do
     if FramBoss then
        AutoFramBoss()
     end 
  end
end)
 -- Auto Quest Bartilo
 WeaponBartilo = ""
 local args = {
    [1] = "getInventoryWeapons"
 }
 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 game:GetService("RunService").Heartbeat:Connect(
    function()
       if AutoBartilo then
             game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
       end
    end
 )
 AutoFram:Line()
 AutoFram:Toggle("Auto Quest Bartilo","",_G.Save["AutoQuestbar"],function(v)
   Bool = v
   _G.Save["AutoQuestbar"] = v
   SaveSetting()
   if game.Players.LocalPlayer.Backpack:FindFirstChild("Warrior Helmet") then
      HaveWarriorHelmet = true
   elseif game.Players.LocalPlayer.Character:FindFirstChild("Warrior Helmet") then
      HaveWarriorHelmet = true
   end
   if HaveWarriorHelmet and Bool == true then
      Flux:Notification("Quest Bartilo Successfully","OK")
   elseif WeaponBartilo == "" and Bool == true then
      Flux:Notification("Selecte Weapon First","OK")
   elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 and Bool == true then
      Flux:Notification("Successfully","OK")
   else
      AutoBartilo = v
   end
    while AutoBartilo do wait()
      if AutoBartilo then
         if game.Players.LocalPlayer.Data.Level.Value >= 800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
            if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
               if game.Workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
                  Ms = "Swan Pirate [Lv. 775]"
                  for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                     if v.Name == Ms then
                        pcall(function()
                           repeat wait()
                              if HideHitBlox then
                                 v.HumanoidRootPart.Transparency = 1
                              else
                                 v.HumanoidRootPart.Transparency = 0.75
                              end
                              v.HumanoidRootPart.CanCollide = false
                              v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,15,0)
                              PosMonBarto =  v.HumanoidRootPart.CFrame
                              game:GetService'VirtualUser':CaptureController()
                              game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                              AutoBartiloBring = true                             
                           until not v.Parent or v.Humanoid.Health <= 0 or AutoBartilo == false or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
                           AutoBartiloBring = false
                        end)
                     end
                  end
               else
                  CFramMon = CFrame.new(1057.92761, 137.614319, 1242.08069)
                  game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFramMon
               end
            else
               game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-456.28952, 73.0200958, 299.895966)
               wait(1.1)
               local args = {
                  [1] = "StartQuest",
                  [2] = "BartiloQuest",
                  [3] = 1
               }
               game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end
         elseif game.Players.LocalPlayer.Data.Level.Value >= 800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
            if game.Workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
               Ms = "Jeremy [Lv. 850] [Boss]"
               for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                  if v.Name == Ms then
                     repeat wait()
                        if HideHitBlox then
                           v.HumanoidRootPart.Transparency = 1
                        else
                           v.HumanoidRootPart.Transparency = 0.75
                        end
                        v.HumanoidRootPart.CanCollide = false
                        v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,15,0)
                        game:GetService'VirtualUser':CaptureController()
                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                     until not v.Parent or v.Humanoid.Health <= 0 or AutoBartilo == false
                  end
               end
            elseif game.ReplicatedStorage:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
               game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-456.28952, 73.0200958, 299.895966)
               wait(1.1)
               local args = {
                     [1] = "BartiloQuestProgress",
                     [2] = "Bartilo"
               }
               game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
               wait(1)
               game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2099.88159, 448.931, 648.997375)
               wait(2)
            else
               game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2099.88159, 448.931, 648.997375)
            end
         elseif game.Players.LocalPlayer.Data.Level.Value >= 800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1850.49329, 13.1789551, 1750.89685)
            wait(1)
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.87305, 19.3777466, 1712.01807)
            wait(1)
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1803.94324, 16.5789185, 1750.89685)
            wait(1)
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.55835, 16.8604317, 1724.79541)
            wait(1)
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1869.54224, 15.987854, 1681.00659)
            wait(1)
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1800.0979, 16.4978027, 1684.52368)
            wait(1)
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1819.26343, 14.795166, 1717.90625)
            wait(1)
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1813.51843, 14.8604736, 1724.79541)
         end
      end
   end
end)
local BartiloWeapon = AutoFram:Dropdown("Select Weapon",Wapon,function(A)
   WeaponBartilo = A
   _G.Save["SelctToolbar"] = A
   SaveSetting()
end)
AutoFram:Button("Refresh Weapon","",function()
   BartiloWeapon:Clear()
   for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
      if v:IsA("Tool") then
         BartiloWeapon:Add(v.Name)
      end
   end
   for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
      if v:IsA("Tool") then
         BartiloWeapon:Add(v.Name)
      end
   end
end)
AutoFram:Line()
 -- Auto Fram Near Mods
 NearWeapon = ""
 AutoFram:Toggle("Auto Farm Near","",_G.Save["AutoNear"],function(v)
    if NearWeapon == "" and v then
              Flux:Notification("Select Wapon First","OK")
    else
        _G.Save["AutoNear"] = v
       AutoNear = v
       SaveSetting()
    end
    while AutoNear do wait()
       if AutoNear then
          for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
             if AutoNear and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= DistanceNear then
                repeat wait()
                      EquipWeapon(NearWeapon)
                      game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                      VirtualUser:CaptureController()
                      VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
                      game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame  * CFrame.new(0, 15, 0)
                      if HideHitBlox then
                         v.HumanoidRootPart.Transparency = 1
                         Statsar = true
                      else
                        Statsar = false
                         v.HumanoidRootPart.Transparency = 0.75
                      end
                      v.HumanoidRootPart.CanCollide = false
                      v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                      if Magnet then
                       
                        PosMonA = v.HumanoidRootPart.CFrame
                        game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = PosMonA * CFrame.new(0, 15, 0)
                        print(PosMonA)
                      end
                      
                      
                until AutoNear == false or not v.Parent or v.Humanoid.Health <= 0
             end
          end
       end
    end
 end)
   DistanceNear = 100
 AutoFram:Slider("Distance",1,1,10000,DistanceNear,function(A)
    DistanceNear = A
    _G.Save["DistanceNear"] = A
    SaveSetting()
 end)
 local WeaponNear = AutoFram:Dropdown("Select Weapon",Wapon,function(Value)
    NearWeapon = Value
    _G.Save["SelctToolNear"] = Value
    SaveSetting()
 end)
 AutoFram:Button("Refresh Weapon","",function()
    WeaponNear:Clear()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
       if v:IsA("Tool") then
          WeaponNear:Add(v.Name)
       end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
       if v:IsA("Tool") then
          WeaponNear:Add(v.Name)
       end
    end
 end)
  AutoFram:Line()
 -- Auto Rengoku
 RengokuWeapon = ""
 AutoFram:Toggle("Auto Rengoku","",_G.Save["AutoRengoku"],function(v)
    if OldWorld then
       Flux:Notification("Use in New World","OK")
    elseif RengokuWeapon == "" and v then
       Flux:Notification("Select Wapon First","OK")
    else
       _G.Save["AutoRengoku"] = v
       AutoRengoku = v
       SaveSetting()
    end
    while AutoRengoku do wait()
       if AutoRengoku then
          if game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or  game.Players.LocalPlayer.Character:FindFirstChild("Hidden Key") then
             EquipWeapon("Hidden Key")
             game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(6571.81885, 296.689758, -6966.76514, 0.825126112, 8.412257e-10, 0.564948559, -2.42370835e-08, 1, 3.39100339e-08, -0.564948559, -4.16727595e-08, 0.825126112)
          elseif game.Workspace.Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") then
             for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                if v.Name == "Snow Lurker [Lv. 1375]" and v.Humanoid.Health > 0 then
                   repeat wait()
                      if game.Workspace.Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") then
                         EquipWeapon(RengokuWeapon)
                         PosMonRengoku = v.HumanoidRootPart.CFrame
                         game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 15, 0)
                         game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                         VirtualUser:CaptureController()
                         VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
                         StatrMagnetRengoku = true
                      else
                         StatrMagnetRengoku = false
                         game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393)
                      end
                   until game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or AutoRengoku == false or not v.Parent or v.Humanoid.Health <= 0
                   StatrMagnetRengoku = false
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393)
                end
             end
          else
             StatrMagnetRengoku = false
             game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393)
          end
       end
    end
 end)
 local Rengoku = AutoFram:Dropdown("Select Weapon",Wapon,function(Value)
    RengokuWeapon = Value
    _G.Save["SelctToolRen"] = Value
    SaveSetting()
 end)
 AutoFram:Button("Refresh Weapon","",function()
    Rengoku:Clear()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
       if v:IsA("Tool") then
          Rengoku:Add(v.Name)
       end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
       if v:IsA("Tool") then
          Rengoku:Add(v.Name)
       end
    end
 end)
  AutoFram:Line()

 AutoFram:Toggle("Auto Sharkman Katate","",_G.Save["AutoSharkman"],function(v)
    if OldWorld then
       Flux:Notification("Use New World","OK")
    elseif SharkmanWeapon == "" and v then
       Flux:Notification("Select Wapon First","OK")
    else
       local args = {
          [1] = "BuyFishmanKarate"
       }
       game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
       AutoSharkman = v
       _G.Save["AutoSharkman"] = v
       SaveSetting()
    end
    while AutoSharkman do wait()
       if AutoSharkman then
          if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then
             if game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key") then
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365)
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
             elseif game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 then
             else
                Ms = "Tide Keeper [Lv. 1475] [Boss]"
                if game.Workspace.Enemies:FindFirstChild(Ms) then
                   for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                      if v.Name == Ms then
                         repeat wait()
                            EquipWeapon(SharkmanWeapon)
                            game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                            if HideHitBlox then
                               v.HumanoidRootPart.Transparency = 1
                            else
                               v.HumanoidRootPart.Transparency = 0.75
                            end
                            v.HumanoidRootPart.CanCollide = false
                            v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,15,0)
                            game:GetService'VirtualUser':CaptureController()
                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                         until not v.Parent or v.Humanoid.Health <= 0 or AutoSharkman == false or game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key")
                      end
                   end
                else
                   CFrameBoss = CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202)
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameBoss
                end
             end
          else
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buy SharkmanKarate")
          end
       end
    end
 end)
 local Sharkman = AutoFram:Dropdown("Select Weapon",Wapon,function(Value)
    SharkmanWeapon = Value
    _G.Save["SelctToolShark"] = Value
    SaveSetting()
 end)
 SharkmanWeapon =  _G.Save["SelctToolShark"]
 AutoFram:Button("Refresh Weapon","",function()
    Sharkman:Clear()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
       if v:IsA("Tool") then
          Sharkman:Add(v.Name)
       end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
       if v:IsA("Tool") then
          Sharkman:Add(v.Name)
       end
    end
 end)
 -- Auto Fram Ectoplasm
  AutoFram:Line()
 AutoFram:Label("Auto Farm Observation")
 local ObservationVirtualUser = game:GetService('VirtualUser')
 AutoFram:Toggle("Auto Farm Observation","",_G.Save["AutoObservation"],function(a)
    Observation = a
    _G.Save["AutoObservation"] = a
    SaveSetting()
    if Observation then
       ObservationVirtualUser:CaptureController()
       ObservationVirtualUser:SetKeyDown('0x65')
       wait(2)
       ObservationVirtualUser:SetKeyUp('0x65')
    end
    while Observation do wait()
       if NewWorld then
          if game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") then
             if game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
                repeat wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]").HumanoidRootPart.CFrame * CFrame.new(3,0,0)
                until Observation == false or not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
             else
                repeat wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]").HumanoidRootPart.CFrame * CFrame.new(10,15,0)
                until Observation == false or game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
             end
          else
             game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(918.558777, 40.0827065, 32766.498)
          end
       elseif OldWorld then
          if game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]") then
             if game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
                repeat wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame * CFrame.new(3,0,0)
                until Observation == false or not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
             else
                repeat wait()
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame * CFrame.new(10,15,0)
                until Observation == false or game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
             end
          else
             game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5533.29785, 88.1079102, 4852.3916)
          end
       end
    end
 end)
 spawn(function()
    while wait() do wait(40)
       pcall(function()
          if Observation and not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
             ObservationVirtualUser:CaptureController()
             ObservationVirtualUser:SetKeyDown('0x65')
             wait(2)
             ObservationVirtualUser:SetKeyUp('0x65')
          end
       end)
    end
 end)
 AutoFram:Button("Check Observation Haki level","",function()
    Flux:Notification("Observation Haki Level : "..game.Players.LocalPlayer.VisionRadius.Value,"OK")
 end)
 AutoFram:Line()
 AutoFram:Label("Ectoplasm")
 AutoFram:Toggle("Auto Fram Ectoplasm","",false,function(A)
  if NewWorld then
     AutoFramEctoplasm = A
  else
     Flux:Notification("Use in New World","OK")
  end
  while AutoFramEctoplasm do wait()
     if AutoFramEctoplasm then
        if game.Workspace.Enemies:FindFirstChild("Ship Deckhand [Lv. 1250]") or game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") or game.Workspace.Enemies:FindFirstChild("Ship Steward [Lv. 1300]") or game.Workspace.Enemies:FindFirstChild("Ship Officer [Lv. 1325]") then
           for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
              if string.find(v.Name, "Ship") then
                 repeat wait()
                    if string.find(v.Name, "Ship") then
                       if setsimulationradius then 
                          setsimulationradius(1e+1598, 1e+1599)
                       end
                       EquipWeapon(EctoplasmWeaponSelect)
                       game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                       VirtualUser:CaptureController()
                       VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
                       -- ÂµÃ•Ã ÃÂ§
                       PosMonEctoplasm = v.HumanoidRootPart.CFrame
                       game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 15, 0)
                       StatrMagnetEctoplasm = true
                    else
                       StatrMagnetEctoplasm = false
                       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(920.14447, 129.581833, 33442.168, -0.999913812, 0, -0.0131403487, 0, 1, 0, 0.0131403487, 0, -0.999913812)
                    end
                 until game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or AutoFramEctoplasm == false or not v.Parent or v.Humanoid.Health <= 0
                 StatrMagnetEctoplasm = false
                 game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(920.14447, 129.581833, 33442.168, -0.999913812, 0, -0.0131403487, 0, 1, 0, 0.0131403487, 0, -0.999913812)
              end
           end
        else
           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(902.059143, 124.752518, 33071.8125)
        end
     end
  end
end)
    AutoFram:Line()
 AutoFram:Label("Auto Farm Mastery Skill Setting")
AutoFram:Toggle("Skill Z","",_G.Save["SkillZ"],function(a)
    SkillZ = a
    _G.Save["SkillZ"] = a
    SaveSetting()
 end)
 AutoFram:Toggle("Skill X","",_G.Save["SkillX"],function(a)
    SkillX = a
    _G.Save["SkillX"] = a
    SaveSetting()
 end)
 AutoFram:Toggle("Skill C","", _G.Save["SkillC"],function(a)
    SkillC = a
     _G.Save["SkillC"] = a
     SaveSetting()
 end)
 AutoFram:Toggle("Skill V","", _G.Save["SkillV"],function(a)
    SkillV = a
     _G.Save["SkillV"] = a 
     SaveSetting()
 end)
 AutoFram:Line()
 AutoFram:Label("Other")
OldLevel = game.Players.LocalPlayer.Data.Beli.Value
AutoFram:Slider("Select Beli Lock","",1,100000000,100000000,function(value)
  CVB = value
  _G.Save["SelectBeliValue"] = value
  SaveSetting()
end)
CVB = _G.Save["SelectBeliValue"] 
AutoFram:Toggle("Lock Beli","",_G.Save["lockBeli"],function(value)
  bnn = value
  _G.Save["lockBeli"] = value
  SaveSetting()
end)
spawn(function()
  while wait(.1) do
     if bnn then
        if game.Players.LocalPlayer.Data.Beli.Value >= CVB then
           game.Players.localPlayer:Kick("\n Beli Complete")
        end
     end
  end
end)
 -- Magnet
 spawn(function()
    while wait() do
       if Mastery and StatrMagnetDevilFruitMastery and Magnet then
          for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
             CheckQuest()
             if v.Name == Ms and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                if v.Name == "Factory Staff [Lv. 800]" and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 200 then
                   wait()
                   v.HumanoidRootPart.CanCollide = false
                   if HideHitBlox then
                      v.HumanoidRootPart.Transparency = 1
                   else
                      v.HumanoidRootPart.Transparency = 0.75
                   end
                   sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                   if UseDF then
                      v.HumanoidRootPart.Size = Vector3.new(2, 2, 1)
                   elseif UseDF == false then
                      v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                   end
                   v.HumanoidRootPart.CFrame = PosMon
                elseif v.Name == Ms and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
                   wait()
                   v.HumanoidRootPart.CanCollide = false
                   if HideHitBlox then
                      v.HumanoidRootPart.Transparency = 1
                   else
                      v.HumanoidRootPart.Transparency = 0.75
                   end
                   if UseDF then
                      v.HumanoidRootPart.Size = Vector3.new(2, 2, 1)
                   elseif UseDF == false then
                      v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                   end
                   v.HumanoidRootPart.CFrame = PosMon
                   sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                end
             end
          end
       end
       if AutoBartilo and AutoBartiloBring and Magnet then
          for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
             if v.Name == "Swan Pirate [Lv. 775]" and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                if v.Name == "Swan Pirate [Lv. 775]" then
                   if HideHitBlox then
                      v.HumanoidRootPart.Transparency = 1
                   else
                      v.HumanoidRootPart.Transparency = 0.75
                   end
                   v.HumanoidRootPart.CanCollide = false
                   v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                   v.HumanoidRootPart.CFrame = PosMonBarto
                   sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                end
             end
          end
       end
       if AutoRengoku and StatrMagnetRengoku and Magnet then
          for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
             if v.Name ==  "Snow Lurker [Lv. 1375]" and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                if v.Name == "Snow Lurker [Lv. 1375]" then
                   if HideHitBlox then
                      v.HumanoidRootPart.Transparency = 1
                   else
                      v.HumanoidRootPart.Transparency = 0.75
                   end
                   v.HumanoidRootPart.CanCollide = false
                   v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                   v.HumanoidRootPart.CFrame = PosMonRengoku
                   sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                end
             end
          end
       end
       if AutoFramEctoplasm and StatrMagnetEctoplasm and Magnet then
          for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
             if string.find(v.Name, "Ship") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                if (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 500 then
                   if HideHitBlox then
                      v.HumanoidRootPart.Transparency = 1
                   else
                      v.HumanoidRootPart.Transparency = 0.75
                   end
                   v.HumanoidRootPart.CanCollide = false
                   v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                   v.HumanoidRootPart.CFrame = PosMonEctoplasm
                   
                   sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                end
             end
          end
       end
       if AFM and StatrMagnet and Magnet then
        CheckQuest()
        for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
           if v.Name == Ms and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
              if (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 600 then
                 if HideHitBlox then
                    v.HumanoidRootPart.Transparency = 1
                 else
                    v.HumanoidRootPart.Transparency = 0.75
                 end
                 v.HumanoidRootPart.CanCollide = false
                 v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
                 v.HumanoidRootPart.CFrame = PosMon
                 v.Head.CFrame = PosMon
                 sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
              end
           end
        end
       end
    if AutoNear and Statsar and Magnet then
     for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
        if v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
           if (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 400 then
              if HideHitBlox then
                 v.HumanoidRootPart.Transparency = 1
              else
                 v.HumanoidRootPart.Transparency = 0.75
              end
              v.HumanoidRootPart.CanCollide = false
              v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
              v.HumanoidRootPart.CFrame = PosMonA
              sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
           end
        end
     end
  end
    end
    if HakiV2 and Statsar and Magnet then
     for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
        if v.Name == "Forest Pirate [Lv. 1825]" then
           if (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 800 then
              if HideHitBlox then
                 v.HumanoidRootPart.Transparency = 1
              else
                 v.HumanoidRootPart.Transparency = 0.75
              end
              v.HumanoidRootPart.CanCollide = false
              v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
              v.HumanoidRootPart.CFrame = osPos
              sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
           end
        end
     end
  end
    if GunMastery and Statsar and Magnet then
     for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
        if v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
              if HideHitBlox then
                 v.HumanoidRootPart.Transparency = 1
              else
                 v.HumanoidRootPart.Transparency = 0.75
              end
              v.HumanoidRootPart.CanCollide = false
              v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
              v.HumanoidRootPart.CFrame = PosMonF
              sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
        end
     end
  end

 end)
  -----------------------------------------------------------------------------------------------------------------------------------------------
 local Stats = win:Tab("Stats","http://www.roblox.com/asset/?id=7100881079")

 Stats:Toggle("Melee","",_G.Save["Melee"],function(Value)
    melee = Value
    _G.Save["Melee"] = Value
    SaveSetting()
 end)
 Stats:Toggle("Defense","",_G.Save["Defense"],function(value)
    defense = value
    _G.Save["Defense"] = value
    SaveSetting()
    
 end)
 Stats:Toggle("Sword","",_G.Save["Sword"],function(value)
    sword = value
    _G.Save["Sword"]= value
    SaveSetting()
 end)
 Stats:Toggle("Gun","",_G.Save["Gun"],function(value)
    gun = value
    _G.Save["Gun"] = value
    SaveSetting()
 end)
 Stats:Toggle("Demon Fruit","",_G.Save["demonfruit"],function(value)
    demonfruit = value
    _G.Save["demonfruit"] = value
    SaveSetting()
 end)
 spawn(function()
    while wait() do
          if melee then
             local args = {
             [1] = "AddPoint",
             [2] = "Melee",
             [3] = PointStats
             }
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
          end
          if defense then
             local args = {
             [1] = "AddPoint",
             [2] = "Defense",
             [3] = PointStats
             }
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
          end
          if sword then
             local args = {
             [1] = "AddPoint",
             [2] = "Sword",
             [3] = PointStats
             }
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
          end
          if gun then
             local args = {
             [1] = "AddPoint",
             [2] = "Gun",
             [3] = PointStats
             }
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
          end
          if demonfruit then
             local args = {
             [1] = "AddPoint",
             [2] = "Demon Fruit",
             [3] = PointStats
             }
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
          end
       end
 end)
 -----------------------------------------------------------------------------------------------------------------------------------------------
 local Teleport = win:Tab("Teleport","http://www.roblox.com/asset/?id=7100840693")
 if NewWorld then
           Teleport:Button("Thrid World","",function()
         local args = {
   [1] = "TravelZou"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
       end)
    Teleport:Button("Old World","",function()
       local args = {
          [1] = "TravelMain" -- OLD WORLD to NEW WORLD
       }
       game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
       
    end)
 else
    Teleport:Button("NewWorld","",function()
       local args = {
          [1] = "TravelDressrosa" -- NEW WORLD to OLD WORLD
       }
       game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
 end
 Teleport:Button("Teleport to SeaBeasts","",function()
    for i,v in pairs(game.Workspace.SeaBeasts:GetChildren()) do
       if v:FindFirstChild("HumanoidRootPart") then
          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,100,0)
       end
    end
 end)
    Teleport:Line()
 Teleport:Label("Teleport Island")
 if NewWorld then
    Teleport:Button("First Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(82.9490662, 18.0710983, 2834.98779)
    end)
    Teleport:Button("Kingdom of Rose","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = game.Workspace["_WorldOrigin"].Locations["Kingdom of Rose"].CFrame
    end)
    Teleport:Button("Dark Ares","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = game.Workspace["_WorldOrigin"].Locations["Dark Arena"].CFrame
    end)
    Teleport:Button("Mansion","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-390.096313, 331.886475, 673.464966)
    end)
    Teleport:Button("Flamingo Room","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2302.19019, 15.1778421, 663.811035)
    end)
    Teleport:Button("Green bit","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2372.14697, 72.9919434, -3166.51416)
    end)
    Teleport:Button("Cafe","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-385.250916, 73.0458984, 297.388397)
    end)
    Teleport:Button("Factroy","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(430.42569, 210.019623, -432.504791)
    end)
    Teleport:Button("Colosseum","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1836.58191, 44.5890656, 1360.30652)
    end)
    Teleport:Button("Ghost Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5571.84424, 195.182297, -795.432922)
    end)
    Teleport:Button("Ghost Island 2nd","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5931.77979, 5.19706631, -1189.6908)
    end)
    Teleport:Button("Snow Mountain","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1384.68298, 453.569031, -4990.09766)
    end)
    Teleport:Button("Hot and Cold","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-6026.96484, 14.7461271, -5071.96338)
    end)
    Teleport:Button("Magma Side","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5478.39209, 15.9775667, -5246.9126)
    end)
    Teleport:Button("Cursed Ship","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(902.059143, 124.752518, 33071.8125)
    end)
    Teleport:Button("Frosted Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5400.40381, 28.21698, -6236.99219)
    end)
    Teleport:Button("Forgotten Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-3043.31543, 238.881271, -10191.5791)
    end)
    Teleport:Button("Usoapp Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(4748.78857, 8.35370827, 2849.57959)
    end)
    Teleport:Button("Raids Low","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5554.95313, 329.075623, -5930.31396)
    end)
    Teleport:Button("Minisky Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-260.358917, 49325.7031, -35259.3008)
    end)
 elseif OldWorld then
     
    Teleport:Button("Start Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1071.2832, 16.3085976, 1426.86792)
    end)
    Teleport:Button("Marine Start","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2573.3374, 6.88881969, 2046.99817)
    end)
    Teleport:Button("Middle Town","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-655.824158, 7.88708115, 1436.67908)
    end)
    Teleport:Button("Jungle","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1249.77222, 11.8870859, 341.356476)
    end)
    Teleport:Button("Pirate Village","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1122.34998, 4.78708982, 3855.91992)
    end)
    Teleport:Button("Desert","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1094.14587, 6.47350502, 4192.88721)
    end)
    Teleport:Button("Frozen Village","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1198.00928, 27.0074959, -1211.73376)
    end)
    Teleport:Button("Marine Ford","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-4505.375, 20.687294, 4260.55908)
    end)
    Teleport:Button("Colosseum","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1428.35474, 7.38933945, -3014.37305)
    end)
    Teleport:Button("Sky 1st","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-4970.21875, 717.707275, -2622.35449)
    end)
    Teleport:Button("Sky 2st ","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-4813.0249, 903.708557, -1912.69055)
    end)
    Teleport:Button("Sky 3st ","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-7952.31006, 5545.52832, -320.704956)
    end)
    Teleport:Button("Prison","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(4854.16455, 5.68742752, 740.194641)
    end)
    Teleport:Button("Magma Village","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5231.75879, 8.61593437, 8467.87695)
    end)
    Teleport:Button("UndeyWater City","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(61163.8516, 11.7796879, 1819.78418)
    end)
    Teleport:Button("Fountain City","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5132.7124, 4.53632832, 4037.8562)
    end)
    Teleport:Button("House Cyborg's","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(6262.72559, 71.3003616, 3998.23047)
    end)
    Teleport:Button("Shank's Room","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1442.16553, 29.8788261, -28.3547478)
    end)
    Teleport:Button("Mob Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2850.20068, 7.39224768, 5354.99268)
    end)
    else
   Teleport:Button("First Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-325.113464, 40.1279297, 5491.7583, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
   end)
    Teleport:Button("Boat Castle","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5419.64209, 310.163513, -2657.39526, 0.927179396, 0, 0.374617696, 0, 1, 0, -0.374617696, 0, 0.927179396)
    end)
         Teleport:Button("Marine Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5419.64209, 310.163513, -2657.39526, 0.927179396, 0, 0.374617696, 0, 1, 0, -0.374617696, 0, 0.927179396)
         end)
          Teleport:Button("Turtle Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12916.8906, 327.117188, -7647.22168, -1, 0, 0, 0, 1, 0, 0, 0, -1)
          end)
           Teleport:Button("Amazon Island","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5832.79688, 53.2015953, -1101.43604, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
    end)
    Teleport:Button("Mini Sky","",function()
       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-262.517487, 49321.5117, -35252.9375, -0.999392271, 0, 0.0348687991, 0, 1, 0, -0.0348687991, 0, -0.999392271)
    end)  
 end
 -----------------------------------------------------------------------------------------------------------------------------------------------
 local Raids = win:Tab("Esp-Raids","http://www.roblox.com/asset/?id=7100848432")
 function isnil(thing)
    return (thing == nil)
 end
 local function round(n)
    return math.floor(tonumber(n) + 0.5)
 end
 Number = math.random(1, 1000000)
 function UpdatePlayerChams()
    for i,v in pairs(game:GetService'Players':GetChildren()) do
       pcall(function()
             if not isnil(v.Character) then
                if ESPPlayer then
                   if not isnil(v.Character.Head) and not v.Character.Head:FindFirstChild('NameEsp'..Number) then
                   local bill = Instance.new('BillboardGui',v.Character.Head)
                   bill.Name = 'NameEsp'..Number
                   bill.ExtentsOffset = Vector3.new(0, 1, 0)
                   bill.Size = UDim2.new(1,200,1,30)
                   bill.Adornee = v.Character.Head
                   bill.AlwaysOnTop = true
                   local name = Instance.new('TextLabel',bill)
                   name.Font = "GothamBold"
                   name.FontSize = "Size14"
                   name.TextWrapped = true
                   name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
                   name.Size = UDim2.new(1,0,1,0)
                   name.TextYAlignment = 'Top'
                   name.BackgroundTransparency = 1
                   name.TextStrokeTransparency = 0.5
                   if v.Team == game.Players.LocalPlayer.Team then
                         name.TextColor3 = Color3.fromRGB(73, 255, 0)
                   else
                         name.TextColor3 = Color3.fromRGB(255,10, 0)
                   end
                   else
                         v.Character.Head['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
                   end
                else
                   if v.Character.Head:FindFirstChild('NameEsp'..Number) then
                   v.Character.Head:FindFirstChild('NameEsp'..Number):Destroy()
                   end
                end
             end
       end)
    end
 end
 function UpdateChestChams()
    for i,v in pairs(game.Workspace:GetChildren()) do
       pcall(function()
             if string.find(v.Name,"Chest") then
                if ChestESP then
                   if string.find(v.Name,"Chest") then
                         if not v:FindFirstChild('NameEsp'..Number) then
                            local bill = Instance.new('BillboardGui',v)
                            bill.Name = 'NameEsp'..Number
                            bill.ExtentsOffset = Vector3.new(0, 1, 0)
                            bill.Size = UDim2.new(1,200,1,30)
                            bill.Adornee = v
                            bill.AlwaysOnTop = true
                            local name = Instance.new('TextLabel',bill)
                            name.Font = "GothamBold"
                            name.FontSize = "Size14"
                            name.TextWrapped = true
                            name.Size = UDim2.new(1,0,1,0)
                            name.TextYAlignment = 'Top'
                            name.BackgroundTransparency = 1
                            name.TextStrokeTransparency = 0.5
                            if v.Name == "Chest1" then
                               name.TextColor3 = Color3.fromRGB(255, 10, 0)
                               name.Text = ("Chest 1" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                            end
                            if v.Name == "Chest2" then
                               name.TextColor3 = Color3.fromRGB(73, 255, 0)
                               name.Text = ("Chest 2" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                            end
                            if v.Name == "Chest3" then
                               name.TextColor3 = Color3.fromRGB(255,191, 0)
                               name.Text = ("Chest 3" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                            end
                         else
                            v['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                         end
                   end
                else
                   if v:FindFirstChild('NameEsp'..Number) then
                   v:FindFirstChild('NameEsp'..Number):Destroy()
                   end
                end
             end
       end)
    end
 end
 function UpdateDevilChams()
    for i,v in pairs(game.Workspace:GetChildren()) do
       pcall(function()
             if DevilFruitESP then
                if string.find(v.Name, "Fruit") then
                   if not v.Handle:FindFirstChild('NameEsp'..Number) then
                         local bill = Instance.new('BillboardGui',v.Handle)
                         bill.Name = 'NameEsp'..Number
                         bill.ExtentsOffset = Vector3.new(0, 1, 0)
                         bill.Size = UDim2.new(1,200,1,30)
                         bill.Adornee = v.Handle
                         bill.AlwaysOnTop = true
                         local name = Instance.new('TextLabel',bill)
                         name.Font = "GothamBold"
                         name.FontSize = "Size14"
                         name.TextWrapped = true
                         name.Size = UDim2.new(1,0,1,0)
                         name.TextYAlignment = 'Top'
                         name.BackgroundTransparency = 1
                         name.TextStrokeTransparency = 0.5
                         name.TextColor3 = Color3.fromRGB(73, 255, 0)
                         name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
                   else
                         v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
                   end
                end
             else
                if v.Handle:FindFirstChild('NameEsp'..Number) then
                   v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
                end
             end
       end)
    end
 end
 function UpdateFlowerChams()
    for i,v in pairs(game.Workspace:GetChildren()) do
       pcall(function()
             if v.Name == "Flower2" or v.Name == "Flower1" then
                if FlowerESP then
                   if not v:FindFirstChild('NameEsp'..Number) then
                         local bill = Instance.new('BillboardGui',v)
                         bill.Name = 'NameEsp'..Number
                         bill.ExtentsOffset = Vector3.new(0, 1, 0)
                         bill.Size = UDim2.new(1,200,1,30)
                         bill.Adornee = v
                         bill.AlwaysOnTop = true
                         local name = Instance.new('TextLabel',bill)
                         name.Font = "GothamBold"
                         name.FontSize = "Size14"
                         name.TextWrapped = true
                         name.Size = UDim2.new(1,0,1,0)
                         name.TextYAlignment = 'Top'
                         name.BackgroundTransparency = 1
                         name.TextStrokeTransparency = 0.5
                         name.TextColor3 = Color3.fromRGB(255, 0, 0)
                         if v.Name == "Flower1" then
                            name.Text = ("Blue Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                            name.TextColor3 = Color3.fromRGB(255,10,0)
                         end
                         if v.Name == "Flower2" then
                            name.Text = ("Red Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                            name.TextColor3 = Color3.fromRGB(0, 12, 255 )
                         end
                   else
                         v['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
                   end
                else
                   if v:FindFirstChild('NameEsp'..Number) then
                   v:FindFirstChild('NameEsp'..Number):Destroy()
                   end
                end
             end
       end)
    end
 end
 
 Raids:Toggle("ESP Player","",_G.Save["ESPPlayer"],function(a)
    ESPPlayer = a
    _G.Save["ESPPlayer"] = a 
    SaveSetting()
    while ESPPlayer do wait()
       UpdatePlayerChams()
    end
 end)
 Raids:Toggle("ESP Chest","",_G.Save["ESPChest"],function(a)
    ChestESP = a
    _G.Save["ESPChest"] = a
    SaveSetting()
    while ChestESP do wait()
       UpdateChestChams()
    end
 end)
 Raids:Toggle("ESP Devil Fruit","",_G.Save["ESPDevil"],function(a)
    DevilFruitESP = a
    _G.Save["ESPDevil"] = a
    SaveSetting()
    while DevilFruitESP do wait()
       UpdateDevilChams()
    end
 end)
 Raids:Toggle("ESP Flower","",_G.Save["ESPFlower"],function(a)
    FlowerESP = a
    _G.Save["ESPFlower"] = a 
    SaveSetting()
    while FlowerESP do wait()
       UpdateFlowerChams()
    end
 end)
 Distance = 1
Raids:Toggle("Auto Raid","",false,function(t)
                           _G.autoraid = t
                           end)
                           game:GetService("RunService").RenderStepped:Connect(function()
                           if _G.autoraid then
                               game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
                           end
                           end)
                           
                           spawn(function()
                           while wait(.1) do
                               if _G.autoraid then
                                   for i,v in pairs(game.Workspace:GetChildren()) do
                                       if string.find(v.Name, "Fruit") then
                                           v.Handle.CFrame = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame
                                       end
                                   end
                                   if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                                       if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1")  then
                                           game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", selectchip)
                                       end
                                       if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") and game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") or  game.Players.LocalPlayer.Character:FindFirstChild("Special Microchip")  then
                                           fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
                                       end
                                   end
                                   for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                       if _G.autoraid and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 500 then
                                           pcall(function()
                                               repeat wait(.1)
                                                   if sethiddenproperty then 
                                                       sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                                                   end
                                                   v.HumanoidRootPart.Transparency = 1
                                                   v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
                                                   v.HumanoidRootPart.CanCollide = false
                                                   if v.Humanoid.Health > 0 then
                                                       v.Humanoid.Health = 0
                                                   elseif v.Humanoid.Health == 0 then
                                                       v.Humanoid.Health = v.Humanoid.MaxHealth
                                                   else
                                                       v.Humanoid.Health = 50
                                                   end
                                               until not _G.autoraid or not v.Parent or v.Humanoid.Health <= 0
                                           end)
                                       end
                                   end
                                   spawn(function()
                                       while wait() do
                                           pcall(function()
                                               sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                                           end)
                                       end
                                   end)
                                   if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
                                       if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame*CFrame.new(0,10,0)
                                       elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame*CFrame.new(0,10,0)
                                       elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame*CFrame.new(0,10,0)
                                       elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame*CFrame.new(0,10,0)
                                       elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame*CFrame.new(0,10,0)
                                       end
                                   else
                                       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-6438.73535, 250.645355, -4501.50684)
                                   end
                                   local args = {
                                       [1] = "Awakener",
                                       [2] = "Check"
                                   }
                                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                   local args = {
                                       [1] = "Awakener",
                                       [2] = "Awaken"
                                   }
                                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                               end
                           end
                           end)
                           spawn(function()
                           while wait() do
                               if _G.autoraid then
                                   local args = {
                                       [1] = "Cousin",
                                       [2] = "Buy"
                                   }
                                   
                                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                               end
                           end
                           end)
                           Raids:Dropdown("Select Microchip To Auto Raid",{"Flame","Ice","Quake","Light","Dark","String","Rumble"},function(t)
                           selectchip = t
                           end)
                           Raids:Line()
                           Raids:Toggle("Kill Arua","",false,function(value)
                           RaidsArua = value
                           end)
                           Raids:Toggle("Auto Next Island","",false,function(value)
                           NextIsland = value
                           end)
                           Raids:Toggle("Auto Awakener","",false,function(value)
                           Awakener = value
                           end)
                           Raids:Button("Labbatle","",function()
                           game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-6438.73535, 250.645355, -4501.50684)
                           end)
                           Raids:Button("Awakening Room","", function()
                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(266.227783, 1.39509034, 1857.00732)
                           end)
                           
                           
                           spawn(function()
                           while wait(.1) do
                               if Awakener then
                                   local args = {
                                       [1] = "Awakener",
                                       [2] = "Check"
                                   }
                                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                   local args = {
                                       [1] = "Awakener",
                                       [2] = "Awaken"
                                   }
                                   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                               end
                           end
                           end)
                           spawn(function()
                           while wait(.1) do
                               if NextIsland then
                                   game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                                   if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
                                       if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame*CFrame.new(0,40,0)
                                       elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame*CFrame.new(0,40,0)
                                       elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame*CFrame.new(0,40,0)
                                       elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame*CFrame.new(0,40,0)
                                       elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
                                           game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame*CFrame.new(0,40,0)
                                       end
                                   else
                                       game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-6480.84473, 252.764435, -4532.41748, -0.807500541, -1.05677671e-08, 0.589866817, -2.50809293e-08, 1, -1.64191238e-08, -0.589866817, -2.80528596e-08, -0.807500541)
                                   end
                               end
                           end
                           end)
                           game:GetService("RunService").Heartbeat:Connect(
                           function()
                           if NextIsland then
                               game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                           end
                           end)
                           spawn(function()
                           while wait(.1) do
                               if RaidsArua then
                                   for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                       if RaidsArua and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 500 then
                                           pcall(function()
                                               repeat wait(.1)
                                                   if sethiddenproperty then
                                                       sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                                                   end
                                                   v.HumanoidRootPart.Transparency = 1
                                                   v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
                                                   v.HumanoidRootPart.CanCollide = false
                                                   v.Humanoid.Health = 0
                                               until not RaidsArua or not v.Parent or v.Humanoid.Health <= 0
                                           end)
                                       end
                                   end
                               end
                           end
                       end)
 -----------------------------------------------------------------------------------------------------------------------------------------------
 local Players = win:Tab("Players","http://www.roblox.com/asset/?id=7100894442")
 PlayerName = {}
 for i,v in pairs(game.Players:GetChildren()) do
    table.insert(PlayerName ,v.Name)
 end
 local SelectedPly = Players:Label("SelectPlayer :") 
 SelectedKillPlayer = ""
 local Player = Players:Dropdown("Selected Player",PlayerName,function(plys) --true/false, replaces the current title "Dropdown" with the option that t
    SelectedKillPlayer = plys
    SelectedPly:Refresh("Selected Player : "..SelectedKillPlayer)
 end)
 Players:Button("Refrsh Player","",function()
    PlayerName = {}
    Player:Clear()
    for i,v in pairs(game.Players:GetChildren()) do
       Player:Add(v.Name)
       SelectedPly:Refresh("SelectPlayer :")
    end
 end)
 game:GetService("RunService").Heartbeat:Connect(
    function()
       if KillPlayer then
          game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
       end
    end
 )
 Players:Toggle("Kill Player","",false,function(bool)
    KillPlayer = bool
    if KillPlayer == false then
       game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Size = Vector3.new(2, 2, 1)
    end
    while KillPlayer do wait()
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.CFrame * CFrame.new(0,-15,0)
       game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Size = Vector3.new(60,60,60)
       game:GetService'VirtualUser':CaptureController()
       game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
    end
 end)
 Players:Toggle("Spectate Player","",false,function(bool)
    Sp = bool
    local plr1 = game.Players.LocalPlayer.Character.Humanoid
    local plr2 = game.Players:FindFirstChild(SelectedKillPlayer)
    repeat wait(.1)
       game.Workspace.Camera.CameraSubject = plr2.Character.Humanoid
    until Sp == false
    game.Workspace.Camera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
 end)
 Players:Button("Teleport Player","",function()
    local plr1 = game.Players.LocalPlayer.Character
    local plr2 = game.Players:FindFirstChild(SelectedKillPlayer)
    plr1.HumanoidRootPart.CFrame = plr2.Character.HumanoidRootPart.CFrame
 end)
Players:Line()
 Players:Toggle("Aimbot Gun","",false,function(bool)
    if SelectedKillPlayer == "" and bool then
       VLib:Notification("Select Player to Aim")
    else
       Aimbot = bool
    end
 end)
 local lp = game:GetService('Players').LocalPlayer
 local mouse = lp:GetMouse()
 mouse.Button1Down:Connect(function()
    if Aimbot and game.Players.LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun) then
       local args = {
          [1] = game:GetService("Players"):FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Position,
          [2] = game:GetService("Players"):FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart
       }
       game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
    end
 end)
 Players:Toggle("Aimbot Skill","",false,function(bool)
    AimbotSkill = bool
    while AimbotSkill do wait()
       pcall(function()
          if game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool") and game.Players.LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name]:FindFirstChild("MousePos") then
             local args = {
             [1] = game:GetService("Players"):FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Position
             }
             game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
          end
       end)
    end
 end)
 Players:Line()
 Players:Slider("WalkSpeed","",16,200,200,function(a)
  Speedset = a
 end)
 Players:Slider("JumpPower","",16,200,200,function(a)
  game.Players.LocalPlayer.Character.Humanoid.JumpPower = a
 end)
 Players:Line()
 Players:Line()
 Players:Label("Safe Mode")
 Safe = 5206
 Players:Slider("Select Health","",1,7720,5206,function(a)
     Safe = a
 end)
Players:Toggle("Start Mode","",false,function(a)
    Safeonly = a
end)
Players:Line()
spawn(function()
   while wait() do
       if Kill then
           PlayersKill(true,false)
       end
   end
end)
Players:Line()
Players:Label("Stats Server")
Players:Line()
local Sta1 = Players:Label("Players : " )
local Sta2 = Players:Label("Chest : " )
spawn(function()
    while wait(.1) do
        if Safeonly then
            if game.Players.LocalPlayer.Character.Humanoid.Health <= Safe then
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(87.7890625, 9.12469482, 2800.5979, 0, 0, -1, 0, 1, 0, 1, 0, 0)
           end
       end
   end
end)
Players:Line()
local SelectedPlys = Players:Label("Grab Player [Kabucha Only]") 
Players:Line()
  VA = {}
 for i,v in pairs(game.Players:GetChildren()) do
    table.insert(VA ,v.Name)
 end
 local SelectedPlys = Players:Label("SelectPlayer :") 
 PlayerToGrab = ""
 local Playern = Players:Dropdown("Selected Player",VA,function(plys) --true/false, replaces the current title "Dropdown" with the option that t
    PlayerToGrab  = plys
    SelectedPlys:Refresh("Selected Player : "..PlayerToGrab)
 end)
 Players:Button("Refrsh Player","",function()
    VA = {}
    Playern:Clear()
    for i,v in pairs(game.Players:GetChildren()) do
       Playern:Add(v.Name)
       SelectedPlys:Refresh("SelectPlayer :")
    end
 end)
 Players:Toggle("Grab Player","",false,function(a)
     Graba = a
     while Graba do wait()
         print("heck")
        for i,v in pairs(game:GetService("workspace").Characters:GetChildren()) do
            if v.Name == PlayerToGrab then
                print("heck")
               repeat wait()
                   print("Shit")
                     
                   
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
               until Graba == false
           end
        end
     end
 end)
 -----------------------------------------------------------------------------------------------------------------------------------------------
 local Misc = win:Tab("Misc","http://www.roblox.com/asset/?id=7100794798")
 Misc:Label("Server Time")
      Time = Misc:Label("Server Time")
      local function UpdateTime()
      local GameTime = math.floor(workspace.DistributedGameTime+0.5)
      local Hour = math.floor(GameTime/(60^2))%24
      local Minute = math.floor(GameTime/(60^1))%60
      local Second = math.floor(GameTime/(60^0))%60
      Time:Refresh("Hour : "..Hour.." Minute : "..Minute.." Second : "..Second)
      end
      spawn(function()
            while true do
               UpdateTime()
               game:GetService("RunService").RenderStepped:Wait()
            end
      end)
 local LocalPlayer = game:GetService'Players'.LocalPlayer
 local originalstam = LocalPlayer.Character.Energy.Value
 function infinitestam()
    LocalPlayer.Character.Energy.Changed:connect(function()
       if InfinitsEnergy then
             LocalPlayer.Character.Energy.Value = originalstam
       end
    end)
 end
 spawn(function()
    while wait(.1) do
       if InfinitsEnergy then
             wait(0.3)
             originalstam = LocalPlayer.Character.Energy.Value
             infinitestam()
       end
    end
 end)
 nododgecool = false
 function NoDodgeCool()
    if nododgecool then
       for i,v in next, getgc() do
             if game.Players.LocalPlayer.Character.Dodge then
                if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Dodge then
                for i2,v2 in next, getupvalues(v) do
                   if tostring(v2) == "0.4" then
                         repeat wait(.1)
                            setupvalue(v,i2,0)
                         until not nododgecool
                   end
                end
                end
             end
       end
    end
 end


 Misc:Toggle("Fast Attack","",_G.Save["FastAttkMisc"],function(fat)
  shared.fat = fat
  _G.Save["FastAttkMisc"] = fat
  SaveSetting()
  end)
  spawn(function()
  while wait() do
  if shared.fat then
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(31, 123))
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(2347, 254))
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(523, 524))
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(52, 245))
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(5426, 2432))
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(86, 42))
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(37, 87))
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(534, 453))
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(28742, 272))
   
  game:GetService'VirtualUser':CaptureController()
  game:GetService'VirtualUser':Button1Down(Vector2.new(7865, 47))
  end
  end
  end)
  local Player   = game:GetService('Players').LocalPlayer

local function CheckRig()
   if Player.Character then
       local Humanoid = Player.Character:WaitForChild('Humanoid')
       if Humanoid.RigType == Enum.HumanoidRigType.R15 then
           return 'R15'
       else
           return 'R6'
       end
   end
end

local function InitiateInvis()
   local Character = Player.Character
   local StoredCF = Character.PrimaryPart.CFrame

   if CheckRig() == 'R6' then
       local Clone = Character.HumanoidRootPart:Clone()
       Character.HumanoidRootPart:Destroy()
       Clone.Parent = Character
   else
       local Clone = Character.LowerTorso.Root:Clone()
       Character.LowerTorso.Root:Destroy()
       Clone.Parent = Character.LowerTorso
   end

end
LockLevelValue = 2000
OldLevel = game.Players.LocalPlayer.Data.Level.Value
Misc:Slider("Select Level Lock","",1,LockLevelValue,LockLevelValue,function(value)
  LockLevelValue = value
   _G.Save["SelectLockLvl"] = fat
  SaveSetting()
end)
LockLevelValue =  _G.Save["SelectLockLvl"]
Misc:Toggle("Lock Level","", _G.Save["locklvl"],function(value)
  LockLevel = value
  _G.Save["locklvl"] = value
  SaveSetting()
end)
spawn(function()
  while wait(.1) do
     if LockLevel then
        if game.Players.LocalPlayer.Data.Level.Value >= LockLevelValue then
           game.Players.localPlayer:Kick("\n Auto Fram Completed Level : "..game.Players.LocalPlayer.Data.Level.Value.."\n Old Level : "..OldLevel)
        end
     end
  end
end)
spawn(function()
  while wait(.1) do
     if AuctoClick then
        Click()
     end
  end
end)
if OldWorld then
  Misc:Button("Invisible Your Self","",function()
     CheckRig()
       local cframeold = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1224.45764, 16.7431889, 1511.82288)
       wait(1)
       InitiateInvis()
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cframeold
   end)
elseif NewWorld then
  Misc:Button("Invisible Your Self","",function()
     CheckRig()
       local cframeold = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2327.33594, 273.886383, 1248.98682, 0.0878660157, 4.53410784e-08, 0.996132374, 7.19629512e-08, 1, -5.18647383e-08, -0.996132374, 7.62418111e-08, 0.0878660157)
       wait(1)
       InitiateInvis()
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cframeold
   end)
   else
      Misc:Button("Invisible Your Self","",function()
     CheckRig()
       local cframeold = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-262.517487, 49321.5117, -35252.9375, -0.999392271, 0, 0.0348687991, 0, 1, 0, -0.0348687991, 0, -0.999392271)
       wait(1)
       InitiateInvis()
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cframeold
   end)
end
 Misc:Button("Join Pirates Team","",function()
    local args = {
       [1] = "SetTeam",
       [2] = "Pirates"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    local args = {
       [1] = "BartiloQuestProgress"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    local args = {
       [1] = "Buso"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 Misc:Button("Join Marines Team","",function()
    local args = {
       [1] = "SetTeam",
       [2] = "Marines"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    local args = {
       [1] = "BartiloQuestProgress"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    local args = {
       [1] = "Buso"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 Misc:Button("Check Ectoplasm","",function()
    Flux:Notification("You have "..game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Ectoplasm","Check").." Ectoplasm","OK")
 end)
 Misc:Button("Open Devil Shop","",function()
    local args = {
       [1] = "GetFruits"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    game.Players.localPlayer.PlayerGui.Main.FruitShop.Visible = true
 end)
 Misc:Button("Open Inventory","",function()
    local args = {
       [1] = "getInventoryWeapons"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    game.Players.localPlayer.PlayerGui.Main.Inventory.Visible = true
 end)
 Misc:Button("Open Color Haki","",function()
    game.Players.localPlayer.PlayerGui.Main.Colors.Visible = true
 end)
 Misc:Button("Open Role Name","",function()
    local args = {
       [1] = "getTitles"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    game.Players.localPlayer.PlayerGui.Main.Titles.Visible = true
 end)
 Misc:Toggle("Dodge No Cooldown","",_G.Save["DashnNocool"],function(Value)
    nododgecool = Value
    _G.Save["DashnNocool"] = Value
    SaveSetting()
    NoDodgeCool()
 end)
 Misc:Toggle("Infinits Energy","",_G.Save["InfinitsEnergy"],function(value)
    InfinitsEnergy = value
    _G.Save["InfinitsEnergy"] = value
    SaveSetting()
    originalstam = LocalPlayer.Character.Energy.Value
 end)
 Misc:Toggle("Auto Click","",_G.Save["AuctoClick"],function(value)
    AuctoClick = value
    _G.Save["AuctoClick"] = value
    SaveSetting()
 end)
 Misc:Toggle("Collect Devil Fruit","",_G.Save["AutoCollectFruit"],function(value)
    TeleportDF = value
         _G.Save["AutoCollectFruit"] = value
    SaveSetting()
    pcall(function()
       while TeleportDF do wait()
          for i,v in pairs(game.Workspace:GetChildren()) do
             if string.find(v.Name, "Fruit") then
             v.Handle.CFrame = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame
             end
          end
       end
    end)
 end)
 Fly = false
 function activatefly()
    local mouse=game.Players.LocalPlayer:GetMouse''
    localplayer=game.Players.LocalPlayer
    game.Players.LocalPlayer.Character:WaitForChild("HumanoidRootPart")
    local torso = game.Players.LocalPlayer.Character.HumanoidRootPart
    
    local keys={a=false,d=false,w=false,s=false}
    local e1
    local e2
    local function start()
       local pos = Instance.new("BodyPosition",torso)
       local gyro = Instance.new("BodyGyro",torso)
       pos.Name="EPIXPOS"
       pos.maxForce = Vector3.new(math.huge, math.huge, math.huge)
       pos.position = torso.Position
       gyro.maxTorque = Vector3.new(9e9, 9e9, 9e9)
       gyro.cframe = torso.CFrame
       repeat
             wait()
             localplayer.Character.Humanoid.PlatformStand=true
             local new=gyro.cframe - gyro.cframe.p + pos.position
             if not keys.w and not keys.s and not keys.a and not keys.d then
                speed= speedSET
             end
             if keys.w then
                new = new + workspace.CurrentCamera.CoordinateFrame.lookVector * speed
                speed=speed+speedSET
             end
             if keys.s then
                new = new - workspace.CurrentCamera.CoordinateFrame.lookVector * speed
                speed=speed+speedSET
             end
             if keys.d then
                new = new * CFrame.new(speed,0,0)
                speed=speed+speedSET
             end
             if keys.a then
                new = new * CFrame.new(-speed,0,0)
                speed=speed+speedSET
             end
             if speed>speedSET then
                speed=speedSET
             end
                pos.position=new.p
             if keys.w then
                gyro.cframe = workspace.CurrentCamera.CoordinateFrame*CFrame.Angles(-math.rad(speed*15),0,0)
             elseif keys.s then
                gyro.cframe = workspace.CurrentCamera.CoordinateFrame*CFrame.Angles(math.rad(speed*15),0,0)
             else
                gyro.cframe = workspace.CurrentCamera.CoordinateFrame
             end
       until not Fly
       if gyro then
                gyro:Destroy()
       end
       if pos then
                pos:Destroy()
       end
       flying=false
       localplayer.Character.Humanoid.PlatformStand=false
       speed=0
    end
    e1=mouse.KeyDown:connect(function(key)
       if not torso or not torso.Parent then
             flying=false e1:disconnect() e2:disconnect() return
       end
       if key=="w" then
          keys.w=true
       elseif key=="s" then
          keys.s=true
       elseif key=="a" then
          keys.a=true
       elseif key=="d" then
          keys.d=true
       end
    end)
    e2=mouse.KeyUp:connect(function(key)
       if key=="w" then
          keys.w=false
       elseif key=="s" then
          keys.s=false
       elseif key=="a" then
          keys.a=false
       elseif key=="d" then
          keys.d=false
       end
    end)
    start()
 end
 speedSET = 100
 Misc:Slider("FlySpeed","",0,100,100,function(ds)
  speedSET = ds
  _G.Save["FlySpeed"] = ds
  SaveSetting()
 end)
 speedSET = _G.Save["FlySpeed"]
 Misc:Toggle("Fly","",_G.Save["FlyStart"],function(Value)
    Fly = Value
    _G.Save["FlyStart"]= Value
    SaveSetting()
    activatefly()
 end)
 Misc:Toggle("No Clip","",_G.Save["Noclip"],function(value)
    NoClip = value
    _G.Save["Noclip"] = value
    SaveSetting()
 end)
 game:GetService("RunService").Heartbeat:Connect(
    function()
       if NoClip or Observation then
             game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
       end
    end
 )
 Misc:Button("Remove Lave","",function()
    for i,v in pairs(game.Workspace:GetDescendants()) do
       if v.Name == "Lava" then
          v:Destroy()
       end
    end
    for i,v in pairs(game.ReplicatedStorage:GetDescendants()) do
       if v.Name == "Lava" then
          v:Destroy()
       end
    end
 end)
 Misc:Button("Redeem All Code","",function()
    function UseCode(Text)
       game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
    end
    UseCode("FUDD10")
    UseCode("SUB2GAMERROBOT_EXP1")
    UseCode("BIGNEWS")
    UseCode("THEGREATACE")
    UseCode("SUB2NOOBMASTER123")
    UseCode("Sub2Daigrock")
    UseCode("Axiore")
    UseCode("TantaiGaming")
    UseCode("STRAWHATMAINE")
    UseCode("Sub2OfficialNoobie")
 end)
 Misc:Button("FPS Boost","",function()
    local decalsyeeted = true -- Leaving this on makes games look shitty but the fps goes up by at least 20.
    local g = game
    local w = g.Workspace
    local l = g.Lighting
    local t = w.Terrain
    t.WaterWaveSize = 0
    t.WaterWaveSpeed = 0
    t.WaterReflectance = 0
    t.WaterTransparency = 0
    l.GlobalShadows = false
    l.FogEnd = 9e9
    l.Brightness = 0
    settings().Rendering.QualityLevel = "Level01"
    for i, v in pairs(g:GetDescendants()) do
       if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then
             v.Material = "Plastic"
             v.Reflectance = 0
       elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
             v.Transparency = 1
       elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
             v.Lifetime = NumberRange.new(0)
       elseif v:IsA("Explosion") then
             v.BlastPressure = 1
             v.BlastRadius = 1
       elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
             v.Enabled = false
       elseif v:IsA("MeshPart") then
             v.Material = "Plastic"
             v.Reflectance = 0
             v.TextureID = 10385902758728957
       end
    end
    for i, e in pairs(l:GetChildren()) do
       if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
             e.Enabled = false
       end
    end
 end)
 Misc:Line()
 Misc:Label("Trade Zone")
   TradeName = {}
 for i,v in pairs(game.Players:GetChildren()) do
    table.insert(TradeName ,v.Name)
 end
 local SelectedPly = Misc:Label("SelectPlayer :") 
 SelectedKillPlayer = ""
 local Player = Misc:Dropdown("Selected Player",TradeName,function(plys) --true/false, replaces the current title "Dropdown" with the option that t
    SelectedKillPlayer = plys
    SelectedPly:Refresh("Selected Player : "..SelectedKillPlayer)
 end)
 Misc:Button("Refrsh Player","",function()
    PlayerName = {}
    Player:Clear()
    for i,v in pairs(game.Players:GetChildren()) do
       Player:Add(v.Name)
       SelectedPly:Refresh("SelectPlayer :")
    end
 end)
 Misc:Button("Trade Fist Of Darkness (Selct Players)","",function()
     game.Players.LocalPlayer.Backpack["Fist of Darkness"].Parent = game.Players:FindFirstChild(Player).Backpack
 end)
   Misc:Line()
 Misc:Label("Race Zone")
 Misc:Toggle("Inf Race Fully All race","",_G.Save["InfRace"],function(a)
           _G.race = a
           _G.Save["InfRace"] = a 
           SaveSetting()
    if _G.race == true then
        game.ReplicatedStorage.FX.Agility.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
    elseif _G.race == false then
       game.Players.LocalPlayer.Character.HumanoidRootPart.Agility.Parent = game.ReplicatedStorage.FX
       end
 end)
 -----------------------------------------------------------------------------------------------------------------------------------------------
 local Fruit = win:Tab("Devil Fruit","http://www.roblox.com/asset/?id=7100923244")
 SelectDevil = ""
 Check = false
 Fruit:Dropdown(
    "Devil Fruit Sniper",
    {
       "Bomb-Bomb",
       "Spike-Spike",
       "Chop-Chop",
       "Spring-Spring",
       "Kilo-Kilo",
       "Smoke-Smoke",
       "Spin-Spin",
       "Flame-Flame",
       "Bird: Falcon",
       "Ice-Ice",
       "Sand-Sand",
       "Dark-Dark",
       "Diamond-Diamond",
       "Light-Light",
       "Love-Love",
       "Rubber-Rubber",
       "Barrier-Barrier",
       "Magma-Magma",
       "Door-Door",
       "Quake-Quake",
       "Human-Human: Buddha",
       "String-String",
       "Bird-Bird: Phoenix",
       "Rumble-Rumble",
       "Paw-Paw",
       "Gravity-Gravity",
       "Dough-Dough",
       "Venom-Venom",
       "Control-Control",
       "Dragon-Dragon"
    }
    ,function(ply)
       SelectDevil = ply
       _G.Save["DevilValue"] = ply
       SaveSetting()
    end
 )
 SelectDevil =  _G.Save["DevilValue"]
 Fruit:Toggle("Buy Devil Fruit Sinper","",_G.Save["BuyDevil"],function(value)
    if SelectDevil == "" and value then
       Flux:Notification("Select Devil Fruit Buy Sniper","OK")
    elseif value then
        _G.Save["BuyDevil"] = value
        SaveSetting()
       BuyFruitSinper = value
    end
 end)
 Fruit:Button("Open Inventory Fruit","",function()
local args = {
   [1] = "getInventoryFruits"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

    game.Players.localPlayer.PlayerGui.Main.FruitInventory.Visible = true
 end)
 Fruit:Toggle("Auto Collect FruitInventory","",false,function(R)
     _G.FruitInventoryHop = R
   end)
spawn(function()
   while wait(.1) do
       if _G.FruitInventoryHop then
           -- Script generated by SimpleSpy - credits to exx#9394

local args = {
   [1] = "SetTeam",
   [2] = "Pirates"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
           -- Script generated by SimpleSpy - credits to exx#9394
          for i,v in pairs(game.Workspace:GetChildren()) do
             if string.find(v.Name, "Fruit") then
             v.Handle.CFrame = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame
             end
          end
local args = {
   [1] = "getInventoryFruits"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))

-- Script generated by SimpleSpy - credits to exx#9394

local args = {
   [1] = "StoreFruit",
   [2] = _G.DevilFruitSelect1
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
local args = {
   [1] = "StoreFruit",
   [2] = _G.DevilFruitSelect2
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
local args = {
   [1] = "StoreFruit",
   [2] = _G.DevilFruitSelect3
}

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
wait(5)
Hop() 
       end
   end
end)
 spawn(function()
  while wait(.1) do
     if BuyFruitSinper then
        local args = {
           [1] = "GetFruits"
        }
        
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        local args = {
           [1] = "PurchaseRawFruit",
           [2] = SelectDevil
        }
        
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
     end 
  end
end)
 -----------------------------------------------------------------------------------------------------------------------------------------------
 local BuyItem = win:Tab("Buy item","http://www.roblox.com/asset/?id=7100906322")
 BuyItem:Label("Abilities")
 BuyItem:Button("Skyjump","",function()
    local args = {
       [1] = "BuyHaki",
       [2] = "Geppo"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Buso Haki","",function()
    local args = {
       [1] = "BuyHaki",
       [2] = "Buso"
    }

    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Observation haki","",function()
    local args = {
       [1] = "KenTalk",
       [2] = "Buy"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Soru","",function()
    local args = {
       [1] = "BuyHaki",
       [2] = "Soru"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Buy Random Devil Fruit","",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
 end)
 BuyItem:Toggle("Auto Buy Random Devil Fruit","",_G.Save["AutoRandomDevil"],function(v)
    DevilAutoBuy = v
    _G.Save["AutoRandomDevil"] = v 
    SaveSetting()
 end)
 spawn(function()
    while wait() do
       if DevilAutoBuy then wait()
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
       end
    end
 end)
 BuyItem:Label("Fighting Style")
 BuyItem:Button("Black Leg","",function()
    local args = {
       [1] = "BuyBlackLeg"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Electro","",function()
    local args = {
       [1] = "BuyElectro"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Fishman Karate","",function()
    local args = {
       [1] = "BuyFishmanKarate"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Dragon Claw","",function()
    local args = {
       [1] = "BlackbeardReward",
       [2] = "DragonClaw",
       [3] = "1"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    local args = {
       [1] = "BlackbeardReward",
       [2] = "DragonClaw",
       [3] = "2"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Superhuman","",function()
    local args = {
       [1] = "BuySuperhuman"
    }

    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Death Step","",function()
    local args = {
       [1] = "BuyDeathStep"
    }

    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Sharkman Karate","",function()
    local args = {
       [1] = "BuySharkmanKarate",
       [2] = true
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    local args = {
       [1] = "BuySharkmanKarate"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)

 BuyItem:Label("Race")
 BuyItem:Label(" Must have done this Race already ")
 BuyItem:Button("Race Ghoul","",function()
    local args = {
       [1] = "Ectoplasm",
       [2] = "BuyCheck",
       [3] = 4
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    local args = {
       [1] = "Ectoplasm",
       [2] = "Change",
       [3] = 4
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Race Cyborg","",function()
    local args = {
       [1] = "CyborgTrainer",
       [2] = "Buy"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Random Race","",function()
    local args = {
       [1] = "BlackbeardReward",
       [2] = "Reroll",
       [3] = "2"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 BuyItem:Button("Reset Stats","",function()
    local args = {
       [1] = "BlackbeardReward",
       [2] = "Refund",
       [3] = "2"
    }
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
 end)
 -----------------------------------------------------------------------------------------------------------------------------------------------
 local Setting = win:Tab("Setting","http://www.roblox.com/asset/?id=7100931539")
 Setting:Button("Rejoin","",function()
    local ts = game:GetService("TeleportService")
    local p = game:GetService("Players").LocalPlayer
    ts:Teleport(game.PlaceId, p)
 end)
 local function HttpGet(url)
    return game:GetService("HttpService"):JSONDecode(htgetf(url))
 end
 Setting:Button("Server Hop","",function()
    local PlaceID = game.PlaceId
    local AllIDs = {}
    local foundAnything = ""
    local actualHour = os.date("!*t").hour
    local Deleted = false
    function TPReturner()
       local Site;
       if foundAnything == "" then
          Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
       else
          Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
       end
       local ID = ""
       if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
          foundAnything = Site.nextPageCursor
       end
       local num = 0;
       for i,v in pairs(Site.data) do
          local Possible = true
          ID = tostring(v.id)
          if tonumber(v.maxPlayers) > tonumber(v.playing) then
             for _,Existing in pairs(AllIDs) do
                if num ~= 0 then
                      if ID == tostring(Existing) then
                         Possible = false
                      end
                else
                      if tonumber(actualHour) ~= tonumber(Existing) then
                         local delFile = pcall(function()
                            -- delfile("NotSameServers.json")
                            AllIDs = {}
                            table.insert(AllIDs, actualHour)
                         end)
                      end
                end
                num = num + 1
             end
             if Possible == true then
                table.insert(AllIDs, ID)
                wait()
                pcall(function()
                      -- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
                      wait()
                      game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
                end)
                wait(4)
             end
          end
       end
    end
    function Teleport()
       while wait() do
          pcall(function()
             TPReturner()
             if foundAnything ~= "" then
                TPReturner()
             end
          end)
       end
    end
    Teleport()
 end)
 Setting:Button("Destroy Gui","",function()
    FluxLib:Destroy()
 end)
 Setting:Label("Auto Farm Setting")
 Setting:Toggle("Hide HitBlox","",_G.Save["ShowHitbox"],function(Value)
    HideHitBlox = Value
    _G.Save["ShowHitbox"] = Value
    SaveSetting()
 end)
 AUTOHAKI = false
 Setting:Toggle("Auto Haki","",_G.Save["AUTOHAKI"],function(Value)
    AUTOHAKI = Value
         _G.Save["AUTOHAKI"] = Value
    SaveSetting()
 end)
 Setting:Toggle("Auto Observation haki","",_G.Save["AutoObservationHakib"],function(Value)
    AUTOHAKIObs = Value
              _G.Save["AutoObservationHakib"] = Value
    SaveSetting()
 end)
 local vu = game:GetService("VirtualUser")
 game:GetService("Players").LocalPlayer.Idled:connect(function()
    vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
    wait(1)
    vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
 end)
 Setting:Toggle("Anit AFK","",_G.Save["AntiAfk"],function(vu)
    local vu = game:GetService("VirtualUser")
    _G.Save["AntiAfk"] = Value
    SaveSetting()
    game:GetService("Players").LocalPlayer.Idled:connect(function()
       vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
       wait(1)
       vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
    end)
 end)
 Setting:Toggle("Magnet","if mon no bring pls off ",_G.Save["Magnet"],function(vu)
     if vu == true then
         _G.Save["Magnet"] = vu
         SaveSetting()
           Magnet = true
     else
         Magnet = false
                   _G.Save["Magnet"] = vu
         SaveSetting()
   end
 end)
 Setting:Line()
 Setting:Toggle("Fully Superhuman","",_G.Save["FullySuper"],function(A)
     _G.Save["FullySuper"] = A 
     SaveSetting()
     Fully = A
 end)
 Setting:Toggle("Fully Elecric v2","",_G.Save["FullyEl"],function(A)
     _G.Save["FullyEl"] = A 
     SaveSetting()
     FullyE = A
 end)
 function Fix()
     CheckQuest()
       pcall(function()
           for i,v in pairs(game:GetService("workspace").Enemies:GetChildren()) do
               if v.Name == Ms then
                   if string.gsub(v.HumanoidRootPart.CFrame,sethiddenproperty(v.HumanoidRootPart.CFrame, "SimulationRadius",1698)) then
                       if (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 800 then
                           v.HumanoidRootPart.CFrame = PosMon
                           v.Humanoid:ChangeState(14)
                           v.HumanoidRootPart.CanCollide = false
                       v.HumanoidRootPart.Size = Vector3.new(60,60,60)
                       sethiddenproperty(v.HumanoidRootPart.CFrame, "SimulationRadius",1699)
                       local gt = getrawmetatable(game)
                       local f = gt.__newindex
                       
                       setreadonly(gt,false)
                       gt.__newindex = newcclosure(function(Self,Key,Name)
                           if tostring(Self) == "HumanoidRootPart" and tostring(Key) == "magnitude" and string.find(tostring(Self:GetFullName()),v.HumanoidRootPart.CFrame) then
                               return f(Self,Key,200)
                           end
                           return f(Self,Key,Name)
                       end)
                           getgc(v.HumanoidRootPart.CFrame,sethiddenproperty(v.HumanoidRootPart.CFrame, "SimulationRadius",1698))
                           getgenv(gt)
                           getreg(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
                           getrenv(v.HumanoidRootPart.CFrame)
                           
                           
                       local ju
                           ju = hookfunction(gt,function(self,m)
                               if self == string.find(Ms) then
                                   if m == tostring(self,v.HumanoidRootPart.magnitude) then
                                       
                                       setupvalue(self,m,100)
                                   end
                               end
                           end)
                       end
                   end
               end
           end
       end)
    end
 function Fixb()
     CheckQuest()
       pcall(function()
           for i,v in pairs(game:GetService("workspace").Enemies:GetChildren()) do
               if v.Name == "HumanoidRootPart" or "Humanoid" then
                   if string.gsub(v.HumanoidRootPart.CFrame,sethiddenproperty(v.HumanoidRootPart.CFrame, "SimulationRadius",1698)) then
                       if (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 500 then
                           v.HumanoidRootPart.CFrame = PosMon
                           v.Humanoid:ChangeState(14)
                           v.HumanoidRootPart.CanCollide = false
                       v.HumanoidRootPart.Size = Vector3.new(60,60,60)
                       sethiddenproperty(v.HumanoidRootPart.CFrame, "SimulationRadius",1699)
                       local gt = getrawmetatable(game)
                       local f = gt.__newindex
                       
                       setreadonly(gt,false)
                       gt.__newindex = newcclosure(function(Self,Key,Name)
                           if tostring(Self) == "HumanoidRootPart" and tostring(Key) == "magnitude" and string.find(tostring(Self:GetFullName()),v.HumanoidRootPart.CFrame) then
                               return f(Self,Key,200)
                           end
                           return f(Self,Key,Name)
                       end)
                           getgenv(gt)
                           getreg(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
                           getrenv(v.CFrame)
                           while wait() do
                                v.CFrame = v.CFrame
                               
                           end
                       local ju
                           ju = hookfunction(gt,function(self,m)
                               if self == string.find(Ms) then
                                   if m == tostring(self,v.HumanoidRootPart.magnitude) then
                                       
                                       setupvalue(self,m,100)
                                   end
                               end
                           end)
                       end
                   end
               end
           end
       end)
    end
 
spawn(function()
  while wait() do
     if GunMastery then
        Fix()
     end
   end
end)
spawn(function()
   while wait() do
       if RaidsArua then
           Fixb()
       end
   end
end)
spawn(function()
  while wait() do
     if AutoNear then
        Fix()
     end
   end
end)
spawn(function()
  while wait() do
     if AFM then
        Fix()
     end
   end
end)
spawn(function()
  while wait() do
     if AutoFramEctoplasm then
        Fix()
     end
   end
end)
spawn(function()
  while wait() do
     if AutoRengoku then
        Fix()
     end
   end
end)
spawn(function()
  while wait() do
     if AutoBartilo then
        Fix()
     end
   end
end)
spawn(function()
  while wait() do
     if Mastery then
        Fix()
     end
   end
end)
 spawn(function()
    while wait(.1) do
       if AUTOHAKI then
          if game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then

          else
             local args = {
                [1] = "Buso"
             }
             game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
          end
       end
       if AUTOHAKIObs then
          if game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then

          else wait(1)
             local virtualUser = game:GetService('VirtualUser')
             virtualUser:CaptureController()

             virtualUser:SetKeyDown('0x65')
             wait(2)
             virtualUser:SetKeyUp('0x65')
          end
       end
    end
 end)
  while wait(.1) do
local count = 0

for i,v in pairs(game.Players:GetChildren()) do
   if  v:IsA("Player") then
       count = count + 1
       Sta1:Refresh("Players : " ..count)
   end
end
local List = 0

for i,v in pairs(game.Workspace:GetChildren()) do
   if  v:IsA("Part") then
       List = List + 1
       Sta2:Refresh("Chest : " ..List)
   end
end
end
end
if game.PlaceId == 7393403076 then
      local Flux = {RainbowColorValue = 0, HueSelectionPosition = 0}
  local PresetColor = Color3.fromRGB(66, 134, 255)
  local UserInputService = game:GetService("UserInputService")
  local TweenService = game:GetService("TweenService")
  local RunService = game:GetService("RunService")
  local LocalPlayer = game:GetService("Players").LocalPlayer
  local Mouse = LocalPlayer:GetMouse()
  local CloseBind = Enum.KeyCode.RightControl
  
  local FluxLib = Instance.new("ScreenGui")
  FluxLib.Name = "FluxLib"
  FluxLib.Parent = game.CoreGui
  FluxLib.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
  
  coroutine.wrap(
     function()
        while wait() do
           Flux.RainbowColorValue = Flux.RainbowColorValue + 1 / 255
           Flux.HueSelectionPosition = Flux.HueSelectionPosition + 1
  
           if Flux.RainbowColorValue >= 1 then
              Flux.RainbowColorValue = 0
           end
  
           if Flux.HueSelectionPosition == 80 then
              Flux.HueSelectionPosition = 0
           end
        end
     end
  )()
  
  local function MakeDraggable(topbarobject, object)
     local Dragging = nil
     local DragInput = nil
     local DragStart = nil
     local StartPosition = nil
  
     local function Update(input)
        local Delta = input.Position - DragStart
        local pos =
              UDim2.new(
              StartPosition.X.Scale,
              StartPosition.X.Offset + Delta.X,
              StartPosition.Y.Scale,
              StartPosition.Y.Offset + Delta.Y
        )
        local Tween = TweenService:Create(object, TweenInfo.new(0.2), {Position = pos})
        Tween:Play()
     end
  
     topbarobject.InputBegan:Connect(
        function(input)
              if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
                 Dragging = true
                 DragStart = input.Position
                 StartPosition = object.Position
  
                 input.Changed:Connect(
                    function()
                          if input.UserInputState == Enum.UserInputState.End then
                             Dragging = false
                          end
                    end
                 )
              end
        end
     )
  
     topbarobject.InputChanged:Connect(
        function(input)
              if
                 input.UserInputType == Enum.UserInputType.MouseMovement or
                    input.UserInputType == Enum.UserInputType.Touch
              then
                 DragInput = input
              end
        end
     )
  
     UserInputService.InputChanged:Connect(
        function(input)
              if input == DragInput and Dragging then
                 Update(input)
              end
        end
     )
  end
  
  
  
  function Flux:Window(text, bottom,mainclr,toclose)
     CloseBind = toclose or Enum.KeyCode.RightControl
     PresetColor = mainclr or Color3.fromRGB(255, 35, 45)
     local fs = false
     local MainFrame = Instance.new("Frame")
     local MainCorner = Instance.new("UICorner")
     local LeftFrame = Instance.new("Frame")
     local LeftCorner = Instance.new("UICorner")
     local GlowTabHolder = Instance.new("ImageLabel")
     local Title = Instance.new("TextLabel")
     local BottomText = Instance.new("TextLabel")
     local TabHold = Instance.new("Frame")
     local TabLayout = Instance.new("UIListLayout")
     local Drag = Instance.new("Frame")
     local ContainerFolder = Instance.new("Folder")
  
     MainFrame.Name = "MainFrame"
     MainFrame.Parent = FluxLib
     MainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
     MainFrame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
     MainFrame.ClipsDescendants = true
     MainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
     MainFrame.Size = UDim2.new(0, 0, 0, 0)
  
     MainCorner.CornerRadius = UDim.new(0, 5)
     MainCorner.Name = "MainCorner"
     MainCorner.Parent = MainFrame
  
     LeftFrame.Name = "LeftFrame"
     LeftFrame.Parent = MainFrame
     LeftFrame.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
     LeftFrame.Size = UDim2.new(0, 205, 0, 484)
  
     LeftCorner.CornerRadius = UDim.new(0, 5)
     LeftCorner.Name = "LeftCorner"
     LeftCorner.Parent = LeftFrame
  
     GlowTabHolder.Name = "GlowTabHolder"
     GlowTabHolder.Parent = LeftFrame
     GlowTabHolder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     GlowTabHolder.BackgroundTransparency = 1.000
     GlowTabHolder.BorderSizePixel = 0
     GlowTabHolder.Position = UDim2.new(0, -15, 0, -15)
     GlowTabHolder.Size = UDim2.new(1, 30, 1, 30)
     GlowTabHolder.ZIndex = 0
     GlowTabHolder.Image = "rbxassetid://4996891970"
     GlowTabHolder.ImageColor3 = Color3.fromRGB(15, 15, 15)
     GlowTabHolder.ScaleType = Enum.ScaleType.Slice
     GlowTabHolder.SliceCenter = Rect.new(20, 20, 280, 280)
  
     Title.Name = "Title"
     Title.Parent = LeftFrame
     Title.BackgroundColor3 = Color3.fromRGB(255, 0, 11)
     Title.BackgroundTransparency = 1.000
     Title.Position = UDim2.new(0.097560972, 0, 0.0475206636, 0)
     Title.Size = UDim2.new(0, 111, 0, 34)
     Title.Font = Enum.Font.GothamBold
     Title.Text = text
     Title.TextColor3 = Color3.fromRGB(209, 34, 34  )
     Title.TextSize = 25.000
     Title.TextXAlignment = Enum.TextXAlignment.Left
  
     BottomText.Name = "BottomText"
     BottomText.Parent = LeftFrame
     BottomText.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     BottomText.BackgroundTransparency = 1.000
     BottomText.Position = UDim2.new(0.097560972, 0, 0.0889999792, 0)
     BottomText.Size = UDim2.new(0, 113, 0, 28)
     BottomText.Font = Enum.Font.Gotham
     BottomText.Text = bottom
     BottomText.TextColor3 = Color3.fromRGB(255, 255, 255)
     BottomText.TextSize = 14.000
     BottomText.TextTransparency = 0.300
     BottomText.TextXAlignment = Enum.TextXAlignment.Left
  
     TabHold.Name = "TabHold"
     TabHold.Parent = LeftFrame
     TabHold.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     TabHold.BackgroundTransparency = 1.000
     TabHold.Position = UDim2.new(0, 0, 0.167355374, 0)
     TabHold.Size = UDim2.new(0, 205, 0, 403)
  
     TabLayout.Name = "TabLayout"
     TabLayout.Parent = TabHold
     TabLayout.SortOrder = Enum.SortOrder.LayoutOrder
     TabLayout.Padding = UDim.new(0, 3)
  
     Drag.Name = "Drag"
     Drag.Parent = MainFrame
     Drag.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
     Drag.BackgroundTransparency = 1.000
     Drag.Position = UDim2.new(0.290368259, 0, 0, 0)
     Drag.Size = UDim2.new(0, 501, 0, 23)
  
     ContainerFolder.Name = "ContainerFolder"
     ContainerFolder.Parent = MainFrame
     
     MakeDraggable(Drag,MainFrame)
     MakeDraggable(LeftFrame,MainFrame)
     MainFrame:TweenSize(UDim2.new(0, 706, 0, 484), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
     
     local uitoggled = false
     UserInputService.InputBegan:Connect(
        function(io, p)
           if io.KeyCode == CloseBind then
              if uitoggled == false then
                 MainFrame:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 uitoggled = true
                 wait(.5)
                 FluxLib.Enabled = false
              else
                 MainFrame:TweenSize(UDim2.new(0, 706, 0, 484), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 FluxLib.Enabled = true
                 uitoggled = false
              end
           end
        end
     )
     
     function Flux:Notification(desc,buttontitle)
        for i, v in next, MainFrame:GetChildren() do
           if v.Name == "NotificationBase" then
              v:Destroy()
           end
        end
        local NotificationBase = Instance.new("TextButton")
        local NotificationBaseCorner = Instance.new("UICorner")
        local NotificationFrame = Instance.new("Frame")
        local NotificationFrameCorner = Instance.new("UICorner")
        local NotificationFrameGlow = Instance.new("ImageLabel")
        local NotificationTitle = Instance.new("TextLabel")
        local CloseBtn = Instance.new("TextButton")
        local CloseBtnCorner = Instance.new("UICorner")
        local NotificationDesc = Instance.new("TextLabel")
  
        NotificationBase.Name = "NotificationBase"
        NotificationBase.Parent = MainFrame
        NotificationBase.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        NotificationBase.BackgroundTransparency = 1
        NotificationBase.Size = UDim2.new(0, 706, 0, 484)
        NotificationBase.AutoButtonColor = false
        NotificationBase.Font = Enum.Font.SourceSans
        NotificationBase.Text = ""
        NotificationBase.TextColor3 = Color3.fromRGB(0, 0, 0)
        NotificationBase.TextSize = 14.000
        NotificationBase.Visible = true
  
        NotificationBaseCorner.CornerRadius = UDim.new(0, 5)
        NotificationBaseCorner.Name = "NotificationBaseCorner"
        NotificationBaseCorner.Parent = NotificationBase
  
        NotificationFrame.Name = "NotificationFrame"
        NotificationFrame.Parent = NotificationBase
        NotificationFrame.AnchorPoint = Vector2.new(0.5, 0.5)
        NotificationFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        NotificationFrame.ClipsDescendants = true
        NotificationFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
        NotificationFrame.Size = UDim2.new(0, 0, 0, 0)
  
        NotificationFrameCorner.CornerRadius = UDim.new(0, 5)
        NotificationFrameCorner.Name = "NotificationFrameCorner"
        NotificationFrameCorner.Parent = NotificationFrame
  
        NotificationFrameGlow.Name = "NotificationFrameGlow"
        NotificationFrameGlow.Parent = NotificationFrame
        NotificationFrameGlow.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        NotificationFrameGlow.BackgroundTransparency = 1.000
        NotificationFrameGlow.BorderSizePixel = 0
        NotificationFrameGlow.Position = UDim2.new(0, -15, 0, -15)
        NotificationFrameGlow.Size = UDim2.new(1, 30, 1, 30)
        NotificationFrameGlow.ZIndex = 0
        NotificationFrameGlow.Image = "rbxassetid://4996891970"
        NotificationFrameGlow.ImageColor3 = Color3.fromRGB(15, 15, 15)
        NotificationFrameGlow.ScaleType = Enum.ScaleType.Slice
        NotificationFrameGlow.SliceCenter = Rect.new(20, 20, 280, 280)
  
        NotificationTitle.Name = "NotificationTitle"
        NotificationTitle.Parent = NotificationFrame
        NotificationTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        NotificationTitle.BackgroundTransparency = 1.000
        NotificationTitle.Position = UDim2.new(0.0400609747, 0, 0.0761325806, 0)
        NotificationTitle.Size = UDim2.new(0, 111, 0, 34)
        NotificationTitle.Font = Enum.Font.GothamBold
        NotificationTitle.Text = Title.Text .. " | NOTIFICATION"
        NotificationTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
        NotificationTitle.TextSize = 24.000
        NotificationTitle.TextXAlignment = Enum.TextXAlignment.Left
        NotificationTitle.TextTransparency = 1
  
        CloseBtn.Name = "CloseBtn"
        CloseBtn.Parent = NotificationFrame
        CloseBtn.BackgroundColor3 = Color3.fromRGB(21, 21, 21)
        CloseBtn.ClipsDescendants = true
        CloseBtn.Position = UDim2.new(0.0403124988, 0, 0.720855951, 0)
        CloseBtn.Size = UDim2.new(0, 366, 0, 43)
        CloseBtn.AutoButtonColor = false
        CloseBtn.Font = Enum.Font.Gotham
        CloseBtn.Text = buttontitle
        CloseBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
        CloseBtn.TextSize = 15.000
        CloseBtn.TextTransparency = 1
        CloseBtn.BackgroundTransparency = 1
  
        CloseBtnCorner.CornerRadius = UDim.new(0, 4)
        CloseBtnCorner.Name = "CloseBtnCorner"
        CloseBtnCorner.Parent = CloseBtn
  
        NotificationDesc.Name = "NotificationDesc"
        NotificationDesc.Parent = NotificationFrame
        NotificationDesc.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        NotificationDesc.BackgroundTransparency = 1.000
        NotificationDesc.Position = UDim2.new(0.112499997, 0, 0.266355127, 0)
        NotificationDesc.Size = UDim2.new(0, 309, 0, 82)
        NotificationDesc.Font = Enum.Font.Gotham
        NotificationDesc.Text = desc
        NotificationDesc.TextColor3 = Color3.fromRGB(255, 255, 255)
        NotificationDesc.TextSize = 15.000
        NotificationDesc.TextWrapped = true
        NotificationDesc.TextTransparency = 1
        
        CloseBtn.MouseEnter:Connect(function()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 0}
           ):Play()
        end)
  
        CloseBtn.MouseLeave:Connect(function()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 0.3}
           ):Play()
        end)
        
        CloseBtn.MouseButton1Click:Connect(function()
           
           TweenService:Create(
              NotificationDesc,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 1}
           ):Play()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 1}
           ):Play()
           TweenService:Create(
              NotificationTitle,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {TextTransparency = 1}
           ):Play()
           TweenService:Create(
              CloseBtn,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {BackgroundTransparency = 1}
           ):Play()
           
           wait(.4)
           CloseBtn.Visible = false
           NotificationFrame:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
  
           wait(.2)
           
           TweenService:Create(
              NotificationBase,
              TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
              {BackgroundTransparency = 1}
           ):Play()
           
           wait(.2)
           
           NotificationBase.Visible = false
        end)
  
        
        TweenService:Create(
           NotificationBase,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {BackgroundTransparency = 0.550}
        ):Play()
        
        wait(.1)
        
        NotificationFrame:TweenSize(UDim2.new(0, 400, 0, 214), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
        
        wait(.4)
        TweenService:Create(
           NotificationDesc,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {TextTransparency = .3}
        ):Play()
        TweenService:Create(
           CloseBtn,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {TextTransparency = .3}
        ):Play()
        TweenService:Create(
           NotificationTitle,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {TextTransparency = 0}
        ):Play()
        TweenService:Create(
           CloseBtn,
           TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
           {BackgroundTransparency = 0}
        ):Play()
     end
     local Tabs = {}
     function Tabs:Tab(text,ico)
        local Tab = Instance.new("TextButton")
        local TabIcon = Instance.new("ImageLabel")
        local TabTitle = Instance.new("TextLabel")
        

        Tab.Name = "Tab"
        Tab.Parent = TabHold
        Tab.BackgroundColor3 = PresetColor
        Tab.BorderSizePixel = 0
        Tab.Size = UDim2.new(0, 205, 0, 40)
        Tab.AutoButtonColor = false
        Tab.Font = Enum.Font.SourceSans
        Tab.Text = ""
        Tab.TextColor3 = Color3.fromRGB(0, 0, 0)
        Tab.TextSize = 14.000
        Tab.BackgroundTransparency = 1
  
        TabIcon.Name = "TabIcon"
        TabIcon.Parent = Tab
        TabIcon.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        TabIcon.BackgroundTransparency = 1.000
        TabIcon.Position = UDim2.new(0.0634146333, 0, 0.25, 0)
        TabIcon.Size = UDim2.new(0, 20, 0, 20)
        TabIcon.Image = ico
        TabIcon.ImageTransparency = .3
  
        TabTitle.Name = "TabTitle"
        TabTitle.Parent = Tab
        TabTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        TabTitle.BackgroundTransparency = 1.000
        TabTitle.Position = UDim2.new(0.1902439, 0, 0.25, 0)
        TabTitle.Size = UDim2.new(0, 113, 0, 19)
        TabTitle.Font = Enum.Font.Gotham
        TabTitle.Text = text
        TabTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
        TabTitle.TextSize = 15.000
        TabTitle.TextXAlignment = Enum.TextXAlignment.Left
        TabTitle.TextTransparency = .3
        
        local Container = Instance.new("ScrollingFrame")
        local ContainerLayout = Instance.new("UIListLayout")
  
  
        Container.Name = "Container"
        Container.Parent = ContainerFolder
        Container.Active = true
        Container.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        Container.BackgroundTransparency = 1.000
        Container.BorderSizePixel = 0
        Container.Position = UDim2.new(0.321529746, 0, 0.0475206599, 0)
        Container.Size = UDim2.new(0, 470, 0, 438)
        Container.CanvasSize = UDim2.new(0, 0, 0, 0)
        Container.ScrollBarThickness = 5
        Container.Visible = false
        Container.ScrollBarImageColor3 = Color3.fromRGB(71, 76, 84)
  
        ContainerLayout.Name = "ContainerLayout"
        ContainerLayout.Parent = Container
        ContainerLayout.SortOrder = Enum.SortOrder.LayoutOrder
        ContainerLayout.Padding = UDim.new(0, 15)
        if fs == false then
           fs = true
           TabTitle.TextTransparency = 0
           TabIcon.ImageTransparency = 0
           Tab.BackgroundTransparency = 0
           Container.Visible = true
        end
        
        Tab.MouseButton1Click:Connect(function()
           for i, v in next, ContainerFolder:GetChildren() do
              if v.Name == "Container" then
                 v.Visible = false
              end
              Container.Visible = true
           end
           for i, v in next, TabHold:GetChildren() do
              if v.Name == "Tab" then
                 TweenService:Create(
                    v,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    v.TabIcon,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    v.TabTitle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    Tab,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    TabIcon,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    TabTitle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
              end
           end
        end)
        local ContainerContent = {}
        function ContainerContent:Button(text, desc, callback)
           if desc == "" then
              desc = "There is no description for this button."
           end
           local BtnDescToggled = false
           local Button = Instance.new("TextButton")
           local ButtonCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
  
           Button.Name = "Button"
           Button.Parent = Container
           Button.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Button.ClipsDescendants = true
           Button.Position = UDim2.new(0.370312512, 0, 0.552631557, 0)
           Button.Size = UDim2.new(0, 457, 0, 43)
           Button.AutoButtonColor = false
           Button.Font = Enum.Font.SourceSans
           Button.Text = ""
           Button.TextColor3 = Color3.fromRGB(0, 0, 0)
           Button.TextSize = 14.000
  
           ButtonCorner.CornerRadius = UDim.new(0, 4)
           ButtonCorner.Name = "ButtonCorner"
           ButtonCorner.Parent = Button
  
           Title.Name = "Title"
           Title.Parent = Button
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(255,255,255)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.200942323, 0, 0.785714269, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 1
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Button
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           ArrowIco.ImageTransparency = .3
           
           Button.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
           
           Button.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
           
           Button.MouseButton1Click:Connect(function()
              pcall(callback)
           end)
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if BtnDescToggled == false then
                 Button:TweenSize(UDim2.new(0, 457, 0, 74), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Button:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              BtnDescToggled = not BtnDescToggled
           end)
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Toggle(text, desc,default, callback)
           local ToggleDescToggled = false
           local Toggled = false
           if desc == "" then
              desc = "There is no description for this toggle."
           end
           local Toggle = Instance.new("TextButton")
           local ToggleCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local ToggleFrame = Instance.new("Frame")
           local ToggleFrameCorner = Instance.new("UICorner")
           local ToggleCircle = Instance.new("Frame")
           local ToggleCircleCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
  
           Toggle.Name = "Toggle"
           Toggle.Parent = Container
           Toggle.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Toggle.ClipsDescendants = true
           Toggle.Position = UDim2.new(0.110937506, 0, 0.67653507, 0)
           Toggle.Size = UDim2.new(0, 457, 0, 43)
           Toggle.AutoButtonColor = false
           Toggle.Font = Enum.Font.SourceSans
           Toggle.Text = ""
           Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
           Toggle.TextSize = 14.000
  
           ToggleCorner.CornerRadius = UDim.new(0, 4)
           ToggleCorner.Name = "ToggleCorner"
           ToggleCorner.Parent = Toggle
  
           Title.Name = "Title"
           Title.Parent = Toggle
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           ToggleFrame.Name = "ToggleFrame"
           ToggleFrame.Parent = Circle
           ToggleFrame.BackgroundColor3 = Color3.fromRGB(226, 227, 227)
           ToggleFrame.Position = UDim2.new(33.0856934, 0, 0, 0)
           ToggleFrame.Size = UDim2.new(0, 27, 0, 11)
  
           ToggleFrameCorner.Name = "ToggleFrameCorner"
           ToggleFrameCorner.Parent = ToggleFrame
  
           ToggleCircle.Name = "ToggleCircle"
           ToggleCircle.Parent = ToggleFrame
           ToggleCircle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ToggleCircle.Position = UDim2.new(0, 0, -0.272727281, 0)
           ToggleCircle.Selectable = true
           ToggleCircle.Size = UDim2.new(0, 17, 0, 17)
  
           ToggleCircleCorner.CornerRadius = UDim.new(2, 8)
           ToggleCircleCorner.Name = "ToggleCircleCorner"
           ToggleCircleCorner.Parent = ToggleCircle
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.200942323, 0, 0.785714269, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 1
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Toggle
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(86, 86, 86)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           ArrowIco.ImageTransparency = .3
           
            Toggle.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           Toggle.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
  
           Toggle.MouseButton1Click:Connect(function()
              if Toggled == false then
                 ToggleCircle:TweenPosition(UDim2.new(0.37, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                 TweenService:Create(
                    ToggleCircle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 =PresetColor}
                 ):Play()
              else
                 ToggleCircle:TweenPosition(UDim2.new(0, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                 TweenService:Create(
                    ToggleCircle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
              end
              Toggled = not Toggled
              pcall(callback, Toggled)
           end)
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if ToggleDescToggled == false then
                 Toggle:TweenSize(UDim2.new(0, 457, 0, 74), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Toggle:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              ToggleDescToggled = not ToggleDescToggled
           end)
           if default == true then
              ToggleCircle:TweenPosition(UDim2.new(0.37, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
              TweenService:Create(
                 ToggleCircle,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {BackgroundColor3 =PresetColor}
              ):Play()
              Toggled = not Toggled
              pcall(callback, Toggled)
           end
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        
        function ContainerContent:Slider(text,desc,min,max,start,callback)
           local SliderFunc = {}
           local SliderDescToggled = false
                          local dragging = false
           if desc == "" then
              desc = "There is no description for this slider."
           end
           local Slider = Instance.new("TextButton")
           local SliderCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local SlideFrame = Instance.new("Frame")
           local CurrentValueFrame = Instance.new("Frame")
           local SlideCircle = Instance.new("ImageButton")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
           local Value = Instance.new("TextLabel")
  
           Slider.Name = "Slider"
           Slider.Parent = Container
           Slider.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Slider.ClipsDescendants = true
           Slider.Position = UDim2.new(0.189062506, 0, 0.648612201, 0)
           Slider.Size = UDim2.new(0, 457, 0, 60)
           Slider.AutoButtonColor = false
           Slider.Font = Enum.Font.SourceSans
           Slider.Text = ""
           Slider.TextColor3 = Color3.fromRGB(0, 0, 0)
           Slider.TextSize = 14.000
  
           SliderCorner.CornerRadius = UDim.new(0, 4)
           SliderCorner.Name = "SliderCorner"
           SliderCorner.Parent = Slider
  
           Title.Name = "Title"
           Title.Parent = Slider
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.201000005, 0, 1.38600004, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 0.300
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           SlideFrame.Name = "SlideFrame"
           SlideFrame.Parent = Title
           SlideFrame.BackgroundColor3 = Color3.fromRGB(235, 234, 235)
           SlideFrame.BorderSizePixel = 0
           SlideFrame.Position = UDim2.new(-0.197140202, 0, 0.986091495, 0)
           SlideFrame.Size = UDim2.new(0, 426, 0, 3)
  
           CurrentValueFrame.Name = "CurrentValueFrame"
           CurrentValueFrame.Parent = SlideFrame
           CurrentValueFrame.BackgroundColor3 = PresetColor
           CurrentValueFrame.BorderSizePixel = 0
           CurrentValueFrame.Size = UDim2.new((start or 0) / max, 0, 0, 3)
  
           SlideCircle.Name = "SlideCircle"
           SlideCircle.Parent = SlideFrame
           SlideCircle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           SlideCircle.BackgroundTransparency = 1.000
           SlideCircle.Position = UDim2.new((start or 0)/max, -6,-1.30499995, 0)
           SlideCircle.Size = UDim2.new(0, 11, 0, 11)
           SlideCircle.Image = "rbxassetid://3570695787"
           SlideCircle.ImageColor3 = PresetColor
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Slider
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(86, 86, 86)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           ArrowIco.ImageTransparency = .3
  
           Value.Name = "Value"
           Value.Parent = Title
           Value.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Value.BackgroundTransparency = 1.000
           Value.Position = UDim2.new(2.27693367, 0, 0, 0)
           Value.Size = UDim2.new(0, 113, 0, 41)
           Value.Font = Enum.Font.Gotham
           Value.Text = tostring(start and math.floor((start / max) * (max - min) + min) or 0)
           Value.TextColor3 = Color3.fromRGB(255, 255, 255)
           Value.TextSize = 15.000
           Value.TextTransparency = 0.300
           Value.TextXAlignment = Enum.TextXAlignment.Right
           
           ArrowBtn.MouseButton1Click:Connect(function()
              if SliderDescToggled == false then
                 Slider:TweenSize(UDim2.new(0, 457, 0, 101), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    Value,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 =PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Slider:TweenSize(UDim2.new(0, 457, 0, 60), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Value,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              SliderDescToggled = not SliderDescToggled
           end)
           
              local function move(input)
                 local pos =
                    UDim2.new(
                       math.clamp((input.Position.X - SlideFrame.AbsolutePosition.X) / SlideFrame.AbsoluteSize.X, 0, 1),
                       -6,
                    -1.30499995,
                       0
                    )
                 local pos1 =
                    UDim2.new(
                       math.clamp((input.Position.X - SlideFrame.AbsolutePosition.X) / SlideFrame.AbsoluteSize.X, 0, 1),
                       0,
                       0,
                       3
                    )
                 CurrentValueFrame:TweenSize(pos1, "Out", "Sine", 0.1, true)
                 SlideCircle:TweenPosition(pos, "Out", "Sine", 0.1, true)
                 local value = math.floor(((pos.X.Scale * max) / max) * (max - min) + min)
                 Value.Text = tostring(value)
                 pcall(callback, value)
              end
              SlideCircle.InputBegan:Connect(
                 function(input)
                    if input.UserInputType == Enum.UserInputType.MouseButton1 then
                       dragging = true
                    end
                 end
              )
              SlideCircle.InputEnded:Connect(
                 function(input)
                    if input.UserInputType == Enum.UserInputType.MouseButton1 then
                       dragging = false
                    end
                 end
              )
              game:GetService("UserInputService").InputChanged:Connect(
              function(input)
                 if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then
                    move(input)
                 end
              end
              )
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
           function SliderFunc:Change(tochange)
              CurrentValueFrame.Size = UDim2.new((tochange or 0) / max, 0, 0, 3)
              SlideCircle.Position = UDim2.new((tochange or 0)/max, -6,-1.30499995, 0)
              Value.Text = tostring(tochange and math.floor((tochange / max) * (max - min) + min) or 0)
              pcall(callback,tochange)
           end
           return SliderFunc
        end
        function ContainerContent:Dropdown(text,list,callback)
           local DropFunc = {}
           local Selected = text
           local FrameSize = 43
           local ItemCount = 0
           local DropToggled = false
           local Dropdown = Instance.new("TextButton")
           local DropdownCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local ArrowIco = Instance.new("ImageLabel")
           local DropItemHolder = Instance.new("ScrollingFrame")
           local DropLayout = Instance.new("UIListLayout")
  
           Dropdown.Name = "Dropdown"
           Dropdown.Parent = Container
           Dropdown.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Dropdown.ClipsDescendants = true
           Dropdown.Position = UDim2.new(0.110937499, 0, 0.67653507, 0)
           Dropdown.Size = UDim2.new(0, 457, 0, 43)
           Dropdown.AutoButtonColor = false
           Dropdown.Font = Enum.Font.SourceSans
           Dropdown.Text = ""
           Dropdown.TextColor3 = Color3.fromRGB(0, 0, 0)
           Dropdown.TextSize = 14.000
  
           DropdownCorner.CornerRadius = UDim.new(0, 4)
           DropdownCorner.Name = "DropdownCorner"
           DropdownCorner.Parent = Dropdown
  
           Title.Name = "Title"
           Title.Parent = Dropdown
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = Title
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(3.45979357, 0, 0.508096159, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6035047377"
           ArrowIco.ImageTransparency = .3
  
           DropItemHolder.Name = "DropItemHolder"
           DropItemHolder.Parent = Title
           DropItemHolder.Active = true
           DropItemHolder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           DropItemHolder.BackgroundTransparency = 1.000
           DropItemHolder.BorderSizePixel = 0
           DropItemHolder.Position = UDim2.new(-0.203539819, 0, 1.02380955, 0)
           DropItemHolder.Size = UDim2.new(0, 436, 0, 82)
           DropItemHolder.CanvasSize = UDim2.new(0, 0, 0, 0)
           DropItemHolder.ScrollBarThickness = 5
           DropItemHolder.ScrollBarImageColor3 = Color3.fromRGB(35, 35, 35)
  
           DropLayout.Name = "DropLayout"
           DropLayout.Parent = DropItemHolder
           DropLayout.SortOrder = Enum.SortOrder.LayoutOrder
           DropLayout.Padding = UDim.new(0, 2)
           
           Dropdown.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           Dropdown.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
  
           
           Dropdown.MouseButton1Click:Connect(function()
              if DropToggled == false then
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, FrameSize), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           DropToggled = not DropToggled
           end)
           
           for i,v in next, list do
              ItemCount = ItemCount + 1
              
              if ItemCount == 1 then
                 FrameSize = 78
              elseif ItemCount == 2 then
                 FrameSize = 107
              elseif ItemCount >= 3 then
                 FrameSize = 133
              end
              local Item = Instance.new("TextButton")
              local ItemCorner = Instance.new("UICorner")
              
           Item.Name = "Item"
           Item.Parent = DropItemHolder
           Item.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Item.ClipsDescendants = true
           Item.Size = UDim2.new(0, 427, 0, 25)
           Item.AutoButtonColor = false
           Item.Font = Enum.Font.Gotham
           Item.Text = v
           Item.TextColor3 = Color3.fromRGB(255, 255, 255)
           Item.TextSize = 15.000
           Item.TextTransparency = 0.300
  
           ItemCorner.CornerRadius = UDim.new(0, 4)
           ItemCorner.Name = "ItemCorner"
              ItemCorner.Parent = Item
              DropItemHolder.CanvasSize = UDim2.new(0, 0, 0, DropLayout.AbsoluteContentSize.Y)
              
              Item.MouseEnter:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
              end)
  
              Item.MouseLeave:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
              end)
              
              Item.MouseButton1Click:Connect(function()
                 pcall(callback, v)
                 Title.Text = text
                 Selected = v
                 DropToggled = not DropToggled
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
                 
              end)
           end
           function DropFunc:Add(addtext)
              ItemCount = ItemCount + 1
  
              if ItemCount == 1 then
                 FrameSize = 78
              elseif ItemCount == 2 then
                 FrameSize = 107
              elseif ItemCount >= 3 then
                 FrameSize = 133
              end
              local Item = Instance.new("TextButton")
              local ItemCorner = Instance.new("UICorner")
  
              Item.Name = "Item"
              Item.Parent = DropItemHolder
              Item.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
              Item.ClipsDescendants = true
              Item.Size = UDim2.new(0, 427, 0, 25)
              Item.AutoButtonColor = false
              Item.Font = Enum.Font.Gotham
              Item.Text = addtext
              Item.TextColor3 = Color3.fromRGB(255, 255, 255)
              Item.TextSize = 15.000
              Item.TextTransparency = 0.300
  
              ItemCorner.CornerRadius = UDim.new(0, 4)
              ItemCorner.Name = "ItemCorner"
              ItemCorner.Parent = Item
              DropItemHolder.CanvasSize = UDim2.new(0, 0, 0, DropLayout.AbsoluteContentSize.Y)
  
              Item.MouseEnter:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
              end)
  
              Item.MouseLeave:Connect(function()
                 TweenService:Create(
                    Item,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
              end)
  
              Item.MouseButton1Click:Connect(function()
                 pcall(callback, addtext)
                 Title.Text = text
                 Selected = addtext
                 DropToggled = not DropToggled
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end)
              if DropToggled == true then
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           end
           function DropFunc:Clear()
              Title.Text = text
              FrameSize = 0
              ItemCount = 0
              for i, v in next, DropItemHolder:GetChildren() do
                 if v.Name == "Item" then
                    v:Destroy()
                 end
              end
              if DropToggled == true then
                 Title.Text = Selected
                 Dropdown:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           end
           return DropFunc
        end
        function ContainerContent:Colorpicker(text,preset,callback)
           local ColorPickerToggled = false
           local OldToggleColor = Color3.fromRGB(0, 0, 0)
           local OldColor = Color3.fromRGB(0, 0, 0)
           local OldColorSelectionPosition = nil
           local OldHueSelectionPosition = nil
           local ColorH, ColorS, ColorV = 1, 1, 1
           local RainbowColorPicker = false
           local ColorPickerInput = nil
           local ColorInput = nil
           local HueInput = nil
           
           local Colorpicker = Instance.new("Frame")
           local ColorpickerCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Hue = Instance.new("ImageLabel")
           local HueCorner = Instance.new("UICorner")
           local HueGradient = Instance.new("UIGradient")
           local HueSelection = Instance.new("ImageLabel")
           local Color = Instance.new("ImageLabel")
           local ColorCorner = Instance.new("UICorner")
           local ColorSelection = Instance.new("ImageLabel")
           local Toggle = Instance.new("TextLabel")
           local ToggleFrame = Instance.new("Frame")
           local ToggleFrameCorner = Instance.new("UICorner")
           local ToggleCircle = Instance.new("Frame")
           local ToggleCircleCorner = Instance.new("UICorner")
           local Confirm = Instance.new("TextButton")
           local ConfirmCorner = Instance.new("UICorner")
           local ConfirmTitle = Instance.new("TextLabel")
           local BoxColor = Instance.new("Frame")
           local BoxColorCorner = Instance.new("UICorner")
           local ColorpickerBtn = Instance.new("TextButton")
           local ToggleBtn = Instance.new("TextButton")
  
  
           Colorpicker.Name = "Colorpicker"
           Colorpicker.Parent = Container
           Colorpicker.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
           Colorpicker.ClipsDescendants = true
           Colorpicker.Position = UDim2.new(0.110937499, 0, 0.67653507, 0)
           Colorpicker.Size = UDim2.new(0, 457, 0, 43)
  
           ColorpickerCorner.CornerRadius = UDim.new(0, 4)
           ColorpickerCorner.Name = "ColorpickerCorner"
           ColorpickerCorner.Parent = Colorpicker
  
           Title.Name = "Title"
           Title.Parent = Colorpicker
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = "UI Color Setting"
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
           
  
           ColorpickerBtn.Name = "ColorpickerBtn"
           ColorpickerBtn.Parent = Title
           ColorpickerBtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ColorpickerBtn.BackgroundTransparency = 1.000
           ColorpickerBtn.Position = UDim2.new(-0.336283177, 0, 0, 0)
           ColorpickerBtn.Size = UDim2.new(0, 457, 0, 42)
           ColorpickerBtn.Font = Enum.Font.SourceSans
           ColorpickerBtn.Text = ""
           ColorpickerBtn.TextColor3 = Color3.fromRGB(0, 0, 0)
           ColorpickerBtn.TextSize = 14.000
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Hue.Name = "Hue"
           Hue.Parent = Title
           Hue.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Hue.Position = UDim2.new(0, 229, 0, 46)
           Hue.Size = UDim2.new(0, 25, 0, 80)
  
           HueCorner.CornerRadius = UDim.new(0, 3)
           HueCorner.Name = "HueCorner"
           HueCorner.Parent = Hue
  
           HueGradient.Color = ColorSequence.new {
              ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 0, 4)),
              ColorSequenceKeypoint.new(0.20, Color3.fromRGB(234, 255, 0)),
              ColorSequenceKeypoint.new(0.40, Color3.fromRGB(21, 255, 0)),
              ColorSequenceKeypoint.new(0.60, Color3.fromRGB(0, 255, 255)),
              ColorSequenceKeypoint.new(0.80, Color3.fromRGB(0, 17, 255)),
              ColorSequenceKeypoint.new(0.90, Color3.fromRGB(255, 0, 251)),
              ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 0, 4))
           }			
           HueGradient.Rotation = 270
           HueGradient.Name = "HueGradient"
           HueGradient.Parent = Hue
  
           HueSelection.Name = "HueSelection"
           HueSelection.Parent = Hue
           HueSelection.AnchorPoint = Vector2.new(0.5, 0.5)
           HueSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           HueSelection.BackgroundTransparency = 1.000
           HueSelection.Position = UDim2.new(0.48, 0, 1 - select(1, Color3.toHSV(preset)))
           HueSelection.Size = UDim2.new(0, 18, 0, 18)
           HueSelection.Image = "http://www.roblox.com/asset/?id=4805639000"
           HueSelection.Visible = false
  
           Color.Name = "Color"
           Color.Parent = Title
           Color.BackgroundColor3 = Color3.fromRGB(255, 0, 4)
           Color.Position = UDim2.new(0, -23, 0, 46)
           Color.Size = UDim2.new(0, 246, 0, 80)
           Color.ZIndex = 10
           Color.Image = "rbxassetid://4155801252"
  
           ColorCorner.CornerRadius = UDim.new(0, 3)
           ColorCorner.Name = "ColorCorner"
           ColorCorner.Parent = Color
  
           ColorSelection.Name = "ColorSelection"
           ColorSelection.Parent = Color
           ColorSelection.AnchorPoint = Vector2.new(0.5, 0.5)
           ColorSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ColorSelection.BackgroundTransparency = 1.000
           ColorSelection.Position = UDim2.new(preset and select(3, Color3.toHSV(preset)))
           ColorSelection.Size = UDim2.new(0, 18, 0, 18)
           ColorSelection.Image = "http://www.roblox.com/asset/?id=4805639000"
           ColorSelection.ScaleType = Enum.ScaleType.Fit
           ColorSelection.Visible = false
  
           Toggle.Name = "Toggle"
           Toggle.Parent = Title
           Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Toggle.BackgroundTransparency = 1.000
           Toggle.Position = UDim2.new(2.37430048, 0, 1.07157099, 0)
           Toggle.Size = UDim2.new(0, 137, 0, 38)
           Toggle.Font = Enum.Font.Gotham
           Toggle.Text = "Rainbow"
           Toggle.TextColor3 = Color3.fromRGB(255, 255, 255)
           Toggle.TextSize = 15.000
           Toggle.TextTransparency = 0.300
           Toggle.TextXAlignment = Enum.TextXAlignment.Left
  
           ToggleFrame.Name = "ToggleFrame"
           ToggleFrame.Parent = Toggle
           ToggleFrame.BackgroundColor3 = Color3.fromRGB(226, 227, 227)
           ToggleFrame.Position = UDim2.new(0.778387249, 0, 0.357142866, 0)
           ToggleFrame.Size = UDim2.new(0, 27, 0, 11)
  
           ToggleFrameCorner.Name = "ToggleFrameCorner"
           ToggleFrameCorner.Parent = ToggleFrame
  
           ToggleCircle.Name = "ToggleCircle"
           ToggleCircle.Parent = ToggleFrame
           ToggleCircle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ToggleCircle.Position = UDim2.new(0, 0, -0.273000002, 0)
           ToggleCircle.Selectable = true
           ToggleCircle.Size = UDim2.new(0, 17, 0, 17)
  
           ToggleCircleCorner.CornerRadius = UDim.new(2, 8)
           ToggleCircleCorner.Name = "ToggleCircleCorner"
           ToggleCircleCorner.Parent = ToggleCircle
  
           Confirm.Name = "Confirm"
           Confirm.Parent = Title
           Confirm.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
           Confirm.ClipsDescendants = true
           Confirm.Position = UDim2.new(2.3791616, 0, 1.97633278, 0)
           Confirm.Size = UDim2.new(0, 144, 0, 42)
           Confirm.AutoButtonColor = false
           Confirm.Font = Enum.Font.SourceSans
           Confirm.Text = ""
           Confirm.TextColor3 = Color3.fromRGB(0, 0, 0)
           Confirm.TextSize = 14.000
  
           ConfirmCorner.CornerRadius = UDim.new(0, 4)
           ConfirmCorner.Name = "ConfirmCorner"
           ConfirmCorner.Parent = Confirm
  
           ConfirmTitle.Name = "ConfirmTitle"
           ConfirmTitle.Parent = Confirm
           ConfirmTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ConfirmTitle.BackgroundTransparency = 1.000
           ConfirmTitle.Size = UDim2.new(0, 116, 0, 40)
           ConfirmTitle.Font = Enum.Font.Gotham
           ConfirmTitle.Text = "Confirm"
           ConfirmTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
           ConfirmTitle.TextSize = 15.000
           ConfirmTitle.TextTransparency = 0.300
           ConfirmTitle.TextXAlignment = Enum.TextXAlignment.Left
  
           BoxColor.Name = "BoxColor"
           BoxColor.Parent = Title
           BoxColor.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           BoxColor.Position = UDim2.new(3.26915574, 0, 0.261904776, 0)
           BoxColor.Size = UDim2.new(0, 35, 0, 19)
  
           BoxColorCorner.CornerRadius = UDim.new(0, 4)
           BoxColorCorner.Name = "BoxColorCorner"
           BoxColorCorner.Parent = BoxColor
  
           ToggleBtn.Name = "ToggleBtn"
           ToggleBtn.Parent = Toggle
           ToggleBtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ToggleBtn.BackgroundTransparency = 1.000
           ToggleBtn.Size = UDim2.new(0, 137, 0, 38)
           ToggleBtn.Font = Enum.Font.SourceSans
           ToggleBtn.Text = ""
           ToggleBtn.TextColor3 = Color3.fromRGB(0, 0, 0)
           ToggleBtn.TextSize = 14.000
           
           ColorpickerBtn.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           ColorpickerBtn.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
            
           ColorpickerBtn.MouseButton1Click:Connect(function()
              if ColorPickerToggled == false then
                 ColorSelection.Visible = true
                 HueSelection.Visible = true
                 Colorpicker:TweenSize(UDim2.new(0, 457, 0, 138), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 ColorSelection.Visible = false
                 HueSelection.Visible = false
                 Colorpicker:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              ColorPickerToggled = not ColorPickerToggled
           end)
           
  
           local function UpdateColorPicker(nope)
              BoxColor.BackgroundColor3 = Color3.fromHSV(ColorH, ColorS, ColorV)
              Color.BackgroundColor3 = Color3.fromHSV(ColorH, 1, 1)
  
              pcall(callback, BoxColor.BackgroundColor3)
           end
  
           ColorH =
              1 -
              (math.clamp(HueSelection.AbsolutePosition.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) /
                 Hue.AbsoluteSize.Y)
           ColorS =
              (math.clamp(ColorSelection.AbsolutePosition.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) /
                 Color.AbsoluteSize.X)
           ColorV =
              1 -
              (math.clamp(ColorSelection.AbsolutePosition.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) /
                 Color.AbsoluteSize.Y)
  
           BoxColor.BackgroundColor3 = preset
           Color.BackgroundColor3 = preset
           pcall(callback, BoxColor.BackgroundColor3)
  
           Color.InputBegan:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if RainbowColorPicker then
                       return
                    end
  
                    if ColorInput then
                       ColorInput:Disconnect()
                    end
  
                    ColorInput =
                       RunService.RenderStepped:Connect(
                          function()
                          local ColorX =
                             (math.clamp(Mouse.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) /
                                Color.AbsoluteSize.X)
                          local ColorY =
                             (math.clamp(Mouse.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) /
                                Color.AbsoluteSize.Y)
  
                          ColorSelection.Position = UDim2.new(ColorX, 0, ColorY, 0)
                          ColorS = ColorX
                          ColorV = 1 - ColorY
  
                          UpdateColorPicker(true)
                       end
                       )
                 end
              end
           )
  
           Color.InputEnded:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if ColorInput then
                       ColorInput:Disconnect()
                    end
                 end
              end
           )
  
           Hue.InputBegan:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if RainbowColorPicker then
                       return
                    end
  
                    if HueInput then
                       HueInput:Disconnect()
                    end
  
                    HueInput =
                       RunService.RenderStepped:Connect(
                          function()
                          local HueY =
                             (math.clamp(Mouse.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) /
                                Hue.AbsoluteSize.Y)
  
                          HueSelection.Position = UDim2.new(0.48, 0, HueY, 0)
                          ColorH = 1 - HueY
  
                          UpdateColorPicker(true)
                       end
                       )
                 end
              end
           )
  
           Hue.InputEnded:Connect(
              function(input)
                 if input.UserInputType == Enum.UserInputType.MouseButton1 then
                    if HueInput then
                       HueInput:Disconnect()
                    end
                 end
              end
           )
  
           ToggleBtn.MouseButton1Down:Connect(
              function()
                 RainbowColorPicker = not RainbowColorPicker
  
                 if ColorInput then
                    ColorInput:Disconnect()
                 end
  
                 if HueInput then
                    HueInput:Disconnect()
                 end
  
                 if RainbowColorPicker then
                    ToggleCircle:TweenPosition(UDim2.new(0.37, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                    TweenService:Create(
                       ToggleCircle,
                       TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                       {BackgroundColor3 =PresetColor}
                    ):Play()
  
                    OldToggleColor = BoxColor.BackgroundColor3
                    OldColor = Color.BackgroundColor3
                    OldColorSelectionPosition = ColorSelection.Position
                    OldHueSelectionPosition = HueSelection.Position
  
                    while RainbowColorPicker do
                       BoxColor.BackgroundColor3 = Color3.fromHSV(Flux.RainbowColorValue, 1, 1)
                       Color.BackgroundColor3 = Color3.fromHSV(Flux.RainbowColorValue, 1, 1)
  
                       ColorSelection.Position = UDim2.new(1, 0, 0, 0)
                       HueSelection.Position = UDim2.new(0.48, 0, 0, Flux.HueSelectionPosition)
  
                       pcall(callback, BoxColor.BackgroundColor3)
                       wait()
                    end
                 elseif not RainbowColorPicker then
                    ToggleCircle:TweenPosition(UDim2.new(0, 0,-0.273, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                    TweenService:Create(
                       ToggleCircle,
                       TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                       {BackgroundColor3 = Color3.fromRGB(255,255,255)}
                    ):Play()
  
                    BoxColor.BackgroundColor3 = OldToggleColor
                    Color.BackgroundColor3 = OldColor
  
                    ColorSelection.Position = OldColorSelectionPosition
                    HueSelection.Position = OldHueSelectionPosition
  
                    pcall(callback, BoxColor.BackgroundColor3)
                 end
              end
           )
  
           Confirm.MouseButton1Click:Connect(
              function()
                 ColorPickerToggled = not ColorPickerToggled
                 Colorpicker:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
           )
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Line()
           local Line = Instance.new("TextButton")
           local LineCorner = Instance.new("UICorner")
  
           Line.Name = "Line"
           Line.Parent = Container
           Line.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           Line.ClipsDescendants = true
           Line.Position = UDim2.new(0, 0, 0.70091325, 0)
           Line.Size = UDim2.new(0, 457, 0, 4)
           Line.AutoButtonColor = false
           Line.Font = Enum.Font.SourceSans
           Line.Text = ""
           Line.TextColor3 = Color3.fromRGB(0, 0, 0)
           Line.TextSize = 14.000
  
           LineCorner.CornerRadius = UDim.new(0, 4)
           LineCorner.Name = "LineCorner"
           LineCorner.Parent = Line
           
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Label(text)
           local labelfunc = {}
           local Label = Instance.new("TextButton")
           local LabelCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
  
           Label.Name = "Label"
           Label.Parent = Container
           Label.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Label.ClipsDescendants = true
           Label.Position = UDim2.new(0.370312512, 0, 0.552631557, 0)
           Label.Size = UDim2.new(0, 457, 0, 43)
           Label.AutoButtonColor = false
           Label.Font = Enum.Font.SourceSans
           Label.Text = ""
           Label.TextColor3 = Color3.fromRGB(0, 0, 0)
           Label.TextSize = 14.000
  
           LabelCorner.CornerRadius = UDim.new(0, 4)
           LabelCorner.Name = "LabelCorner"
           LabelCorner.Parent = Label
  
           Title.Name = "Title"
           Title.Parent = Label
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.038480062, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
           
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
           function labelfunc:Refresh(tochange)
              Title.Text = tochange
           end
           return labelfunc
        end
        function ContainerContent:Textbox(text,desc,disapper,callback)
           if desc == "" then
              desc = "There is no description for this textbox."
           end
           local TextboxDescToggled = false
           local Textbox = Instance.new("TextButton")
           local TextboxCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local Description = Instance.new("TextLabel")
           local TextboxFrame = Instance.new("Frame")
           local TextboxFrameCorner = Instance.new("UICorner")
           local TextBox = Instance.new("TextBox")
           local ArrowBtn = Instance.new("ImageButton")
           local ArrowIco = Instance.new("ImageLabel")
  
           Textbox.Name = "Textbox"
           Textbox.Parent = Container
           Textbox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
           Textbox.ClipsDescendants = true
           Textbox.Position = UDim2.new(0.0459499061, 0, 0.734449744, 0)
           Textbox.Size = UDim2.new(0, 457, 0, 43)
           Textbox.AutoButtonColor = false
           Textbox.Font = Enum.Font.SourceSans
           Textbox.Text = ""
           Textbox.TextColor3 = Color3.fromRGB(0, 0, 0)
           Textbox.TextSize = 14.000
  
           TextboxCorner.CornerRadius = UDim.new(0, 4)
           TextboxCorner.Name = "TextboxCorner"
           TextboxCorner.Parent = Textbox
  
           Title.Name = "Title"
           Title.Parent = Textbox
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           Description.Name = "Description"
           Description.Parent = Title
           Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Description.BackgroundTransparency = 1.000
           Description.Position = UDim2.new(-0.200942323, 0, 0.985714269, 0)
           Description.Size = UDim2.new(0, 432, 0, 31)
           Description.Font = Enum.Font.Gotham
           Description.Text = desc
           Description.TextColor3 = Color3.fromRGB(255, 255, 255)
           Description.TextSize = 15.000
           Description.TextTransparency = 1
           Description.TextWrapped = true
           Description.TextXAlignment = Enum.TextXAlignment.Left
  
           TextboxFrame.Name = "TextboxFrame"
           TextboxFrame.Parent = Title
           TextboxFrame.BackgroundColor3 = Color3.fromRGB(50, 53, 59)
           TextboxFrame.Position = UDim2.new(1.82300889, 0, 0.202380955, 0)
           TextboxFrame.Size = UDim2.new(0, 161, 0, 26)
  
           TextboxFrameCorner.CornerRadius = UDim.new(0, 4)
           TextboxFrameCorner.Name = "TextboxFrameCorner"
           TextboxFrameCorner.Parent = TextboxFrame
  
           TextBox.Parent = TextboxFrame
           TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           TextBox.BackgroundTransparency = 1.000
           TextBox.Size = UDim2.new(0, 161, 0, 26)
           TextBox.Font = Enum.Font.Gotham
           TextBox.Text = ""
           TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
           TextBox.TextSize = 15.000
           TextBox.TextTransparency = 0.300
  
           ArrowBtn.Name = "ArrowBtn"
           ArrowBtn.Parent = Textbox
           ArrowBtn.BackgroundColor3 = Color3.fromRGB(86, 86, 86)
           ArrowBtn.BackgroundTransparency = 1.000
           ArrowBtn.Position = UDim2.new(0.903719902, 0, 0, 0)
           ArrowBtn.Size = UDim2.new(0, 33, 0, 37)
           ArrowBtn.SliceCenter = Rect.new(30, 30, 30, 30)
           ArrowBtn.SliceScale = 7.000
  
           ArrowIco.Name = "ArrowIco"
           ArrowIco.Parent = ArrowBtn
           ArrowIco.AnchorPoint = Vector2.new(0.5, 0.5)
           ArrowIco.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           ArrowIco.BackgroundTransparency = 1.000
           ArrowIco.Position = UDim2.new(0.495753437, 0, 0.554054081, 0)
           ArrowIco.Selectable = true
           ArrowIco.Size = UDim2.new(0, 28, 0, 24)
           ArrowIco.Image = "http://www.roblox.com/asset/?id=6034818372"
           
           TextBox.FocusLost:Connect(
              function(ep)
                 if ep then
                    if #TextBox.Text > 0 then
                       pcall(callback, TextBox.Text)
                       if disapper then
                          TextBox.Text = ""
                       end
                    end
                 end
              end
           )
           ArrowBtn.MouseButton1Click:Connect(function()
              if TextboxDescToggled == false then
                 Textbox:TweenSize(UDim2.new(0, 457, 0, 81), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 180}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              else
                 Textbox:TweenSize(UDim2.new(0, 457, 0, 43), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .6, true)
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {ImageTransparency = .3}
                 ):Play()
                 TweenService:Create(
                    ArrowIco,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {Rotation = 0}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    Description,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 1}
                 ):Play()
                 wait(.4)
                 Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
              end
              TextboxDescToggled = not TextboxDescToggled
           end)
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        function ContainerContent:Bind(text,presetbind,callback)
           local Key = presetbind.Name
           local Bind = Instance.new("TextButton")
           local BindCorner = Instance.new("UICorner")
           local Title = Instance.new("TextLabel")
           local Circle = Instance.new("Frame")
           local CircleCorner = Instance.new("UICorner")
           local CircleSmall = Instance.new("Frame")
           local CircleSmallCorner = Instance.new("UICorner")
           local BindLabel = Instance.new("TextLabel")
  
           Bind.Name = "Bind"
           Bind.Parent = Container
           Bind.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           Bind.ClipsDescendants = true
           Bind.Position = UDim2.new(0.40625, 0, 0.828947306, 0)
           Bind.Size = UDim2.new(0, 457, 0, 43)
           Bind.AutoButtonColor = false
           Bind.Font = Enum.Font.SourceSans
           Bind.Text = ""
           Bind.TextColor3 = Color3.fromRGB(0, 0, 0)
           Bind.TextSize = 14.000
  
           BindCorner.CornerRadius = UDim.new(0, 4)
           BindCorner.Name = "BindCorner"
           BindCorner.Parent = Bind
  
           Title.Name = "Title"
           Title.Parent = Bind
           Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           Title.BackgroundTransparency = 1.000
           Title.Position = UDim2.new(0.0822437406, 0, 0, 0)
           Title.Size = UDim2.new(0, 113, 0, 42)
           Title.Font = Enum.Font.Gotham
           Title.Text = text
           Title.TextColor3 = Color3.fromRGB(255, 255, 255)
           Title.TextSize = 15.000
           Title.TextTransparency = 0.300
           Title.TextXAlignment = Enum.TextXAlignment.Left
  
           Circle.Name = "Circle"
           Circle.Parent = Title
           Circle.Active = true
           Circle.AnchorPoint = Vector2.new(0.5, 0.5)
           Circle.BackgroundColor3 = Color3.fromRGB(211, 211, 211)
           Circle.Position = UDim2.new(-0.150690272, 0, 0.503000021, 0)
           Circle.Size = UDim2.new(0, 11, 0, 11)
  
           CircleCorner.CornerRadius = UDim.new(2, 6)
           CircleCorner.Name = "CircleCorner"
           CircleCorner.Parent = Circle
  
           CircleSmall.Name = "CircleSmall"
           CircleSmall.Parent = Circle
           CircleSmall.Active = true
           CircleSmall.AnchorPoint = Vector2.new(0.5, 0.5)
           CircleSmall.BackgroundColor3 = Color3.fromRGB(64, 68, 75)
           CircleSmall.BackgroundTransparency = 1.000
           CircleSmall.Position = UDim2.new(0.485673368, 0, 0.503000021, 0)
           CircleSmall.Size = UDim2.new(0, 9, 0, 9)
  
           CircleSmallCorner.CornerRadius = UDim.new(2, 6)
           CircleSmallCorner.Name = "CircleSmallCorner"
           CircleSmallCorner.Parent = CircleSmall
  
           BindLabel.Name = "BindLabel"
           BindLabel.Parent = Title
           BindLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
           BindLabel.BackgroundTransparency = 1.000
           BindLabel.Position = UDim2.new(2.56011987, 0, 0, 0)
           BindLabel.Size = UDim2.new(0, 113, 0, 42)
           BindLabel.Font = Enum.Font.Gotham
           BindLabel.Text = Key
           BindLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
           BindLabel.TextSize = 15.000
           BindLabel.TextTransparency = 0.300
           BindLabel.TextXAlignment = Enum.TextXAlignment.Right
           
           Bind.MouseEnter:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0}
              ):Play()
           end)
  
           Bind.MouseLeave:Connect(function()
              TweenService:Create(
                 Title,
                 TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                 {TextTransparency = 0.3}
              ):Play()
           end)
  
           Bind.MouseButton1Click:connect(
              function()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = PresetColor}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0}
                 ):Play()
                 BindLabel.Text = "..."
                 local inputwait = game:GetService("UserInputService").InputBegan:wait()
                 if inputwait.KeyCode.Name ~= "Unknown" then
                    BindLabel.Text = inputwait .KeyCode.Name
                    Key = inputwait .KeyCode.Name
                 end
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextColor3 = Color3.fromRGB(255,255,255)}
                 ):Play()
                 TweenService:Create(
                    Circle,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(211, 211, 211)}
                 ):Play()
                 TweenService:Create(
                    CircleSmall,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                 ):Play()
                 TweenService:Create(
                    Title,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
                 TweenService:Create(
                    BindLabel,
                    TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {TextTransparency = 0.3}
                 ):Play()
              end
           )
  
           game:GetService("UserInputService").InputBegan:connect(
           function(current, pressed)
              if not pressed then
                 if current.KeyCode.Name == Key then
                    pcall(callback)
                 end
              end
           end
           )
           
           Container.CanvasSize = UDim2.new(0, 0, 0, ContainerLayout.AbsoluteContentSize.Y)
        end
        return ContainerContent
     end
     return Tabs
  end
  local win = Flux:Window("JPEXHUB", "Anime Artifacts Simulator",getgenv().ColorUi,getgenv().OffOnUI)
  local tab = win:Tab("AutoFarm","")
  local Te = win:Tab("Teleport","")
  local Mi = win:Tab("Misc","")
  Magnet = true
  function AutoFramYedhee()
      if _G.AutoFramYedhee then
               for i,v in pairs(game:GetService("Workspace").NPCFolder:GetDescendants()) do
              if v.Name == "HumanoidRootPart" then
                  repeat wait()
                                        v.CanCollide = false
                                v.Size = Vector3.new(50,50,50)
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                 game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
                      game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame * CFrame.new(0,0,0)
                           v.CFrame = v.CFrame
                   until _G.AutoFramYedhee == false or not v.Parent.Parent
               end
           end
       end
   end
  tab:Toggle("AutoFarm","",false,function(A)
      _G.AutoFramYedhee = A
      while _G.AutoFramYedhee do wait()
          AutoFramYedhee()
       end
  end)
  tab:Toggle("Auto Summon","",false,function(a)
      _G.Summon = a
      while _G.Summon do wait()
game:GetService("ReplicatedStorage").PetEvents.LuckDrawBuyEvent:FireServer()
       end
  end)
  
  Te:Button("First Island","",function()
      game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(550.573242, -2.42432499, 246.488586, 0, 0, 1, 0, 1, -0, -1, 0, 0)
      
  end)
  Te:Button("Bleach Island","",function()
   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-753.3573, 0.500438988, 489.82135, 0.957712173, 0, 0.287727982, 0, 1, 0, -0.287727982, 0, 0.957712173)
  end)
  Te:Button("Demon Slayer Island","",function()
   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(203.539368, -6.49199247, 194.270706, 0, 0, 1, 0, 1, -0, -1, 0, 0)
  end)
  Te:Button("One Piece Island","",function()
   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1716.71472, 4.95337963, 1428.13965, 0, 0, 1, 0, 1, -0, -1, 0, 0)
  end)
  Mi:Slider("WalkSpeed","",0,100,16,function(a)
      game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = a
  end)
  Mi:Slider("JumpPower","",0,200,16,function(a)
      game.Players.LocalPlayer.Character.Humanoid.JumpPower = a
  end)
  local function CheckRig()
   if game.Players.LocalPlayer.Character then
       local Humanoid = game.Players.LocalPlayer.Character:WaitForChild('Humanoid')
       if Humanoid.RigType == Enum.HumanoidRigType.R15 then
           return 'R15'
       else
           return 'R6'
       end
   end
end

local function InitiateInvis()
   local Character = game.Players.LocalPlayer.Character
   local StoredCF = Character.PrimaryPart.CFrame

   if CheckRig() == 'R6' then
       local Clone = Character.HumanoidRootPart:Clone()
       Character.HumanoidRootPart:Destroy()
       Clone.Parent = Character
   else
       local Clone = Character.LowerTorso.Root:Clone()
       Character.LowerTorso.Root:Destroy()
       Clone.Parent = Character.LowerTorso
   end

end
  Mi:Button("Invisible Your Self","",function()
     CheckRig()
       local cframeold = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(550.573242, -2.42432499, 246.488586, 0, 0, 1, 0, 1, -0, -1, 0, 0)
       wait(1)
       InitiateInvis()
       game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cframeold
  end)

  local mt = getrawmetatable(game)
  local old = mt.__namecall
  local protect = newcclosure or protect_function

  if not protect then
     notify("Incompatible Exploit Warning", "Your exploit does not support protection against stack trace errors, resulting to fallback function")
     protect = function(f) return f end
  end

  setreadonly(mt, false)
  mt.__namecall = protect(function(self, ...)
     local method = getnamecallmethod()
     if method == "Kick" then
        wait(9e9)
        return
     end
     return old(self, ...)
  end)
  hookfunction(game.Players.LocalPlayer.Kick,protect(function() wait(9e9) end))
end   
