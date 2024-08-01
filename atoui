--[[
AS
	|----------------|
	|ROBLOX STUDIO UI|
	|----------------|
	__________________
	|		|		|
	|		|		|
	|		|		|
	|_______|_______	|
	|		|		|
	|_______|_______|
	I'm Bad
]]

local Core = game:FindFirstChild('CoreGui') or game:GetService('Players').LocalPlayer.PlayerGui
local LUser = game:WaitForChild('Players').LocalPlayer
local TweenService = game:GetService('TweenService')
local UserInputService = game:GetService('UserInputService')
local Mouse = LUser:GetMouse()

local RBS_UI = {
	ImageIcon = {
		Server = "rbxassetid://7734053426",
		Setting = "rbxassetid://5480743826",
		Users = "rbxassetid://7743876054",
		Client = "rbxassetid://7743875962",
		Shop = "rbxassetid://7734056747",
		Phone = "rbxassetid://7734058979",
		Tablet = "rbxassetid://7743872620",
		Sound = "rbxassetid://7743877250",
		Key = "rbxassetid://7733965118",
		Home = "rbxassetid://7733960981"
	},
	ToggleKey = Enum.KeyCode.RightControl,
	CanMove = true,
	Version = 3
}

local function CalculateDistance(pointA, pointB)
	return math.sqrt(((pointB.X - pointA.X) ^ 2) + ((pointB.Y - pointA.Y) ^ 2))
end

function Create_Ripple(Parent : Frame)
	Parent.ClipsDescendants = true

	local ripple = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local UIStroke = Instance.new('UIStroke',ripple)

	ripple.Name = "ripple"
	ripple.Parent = Parent
	ripple.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ripple.ZIndex = 2
	ripple.AnchorPoint = Vector2.new(0.5, 0.5)
	ripple.Size = UDim2.new(0,0,0,0)
	ripple.SizeConstraint = Enum.SizeConstraint.RelativeYY

	UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	UIStroke.Color = Color3.fromRGB(255,255,255)
	UIStroke.LineJoinMode = Enum.LineJoinMode.Round
	UIStroke.Thickness = 14
	UIStroke.Transparency = 0.3

	UICorner.CornerRadius = UDim.new(0.5, 0)
	UICorner.Parent = ripple

	local buttonAbsoluteSize = Parent.AbsoluteSize
	local buttonAbsolutePosition = Parent.AbsolutePosition

	local mouseAbsolutePosition = Vector2.new(Mouse.X, Mouse.Y)
	local mouseRelativePosition = (mouseAbsolutePosition - buttonAbsolutePosition)

	ripple.BackgroundTransparency = 0.84
	ripple.Position = UDim2.new(0, mouseRelativePosition.X, 0, mouseRelativePosition.Y)
	ripple.Parent = Parent

	local topLeft = CalculateDistance(mouseRelativePosition, Vector2.new(0, 0))
	local topRight = CalculateDistance(mouseRelativePosition, Vector2.new(buttonAbsoluteSize.X, 0))
	local bottomRight = CalculateDistance(mouseRelativePosition, buttonAbsoluteSize)
	local bottomLeft = CalculateDistance(mouseRelativePosition, Vector2.new(0, buttonAbsoluteSize.Y))

	local Size_UP = UDim2.new(50,0,50,0)
	TweenService:Create(ripple,TweenInfo.new(2),{Size = Size_UP,BackgroundTransparency = 1}):Play()
	game:GetService('Debris'):AddItem(ripple,2.2)
end

local function TweenClose(UIobj : Frame | GuiObject,tweeninfo,target,data,set_to)
	local Tween = TweenService:Create(UIobj,tweeninfo,{target = data})
	Tween:Play()
	Tween.Completed:Connect(function()
		wait(0.1)
		if UIobj[target] == data then
			UIobj.Visible = set_to or false
		end
	end)
end

local function Scrol(Scr:ScrollingFrame,UIL:UIListLayout)
	Scr.CanvasSize = UDim2.new(0,0,0,UIL.AbsoluteContentSize.Y+10)
	return UIL:GetPropertyChangedSignal('AbsoluteContentSize'):Connect(function()
		TweenService:Create(Scr,TweenInfo.new(0.2),{CanvasSize = UDim2.new(0,0,0,UIL.AbsoluteContentSize.Y+10)}):Play()
	end)
end

function RBS_UI:NewWindow(TitleStr : string,UserStats : string)
	_G.AssetsRBSUI = _G.AssetsRBSUI or {}
	local Togggleing = true
	local Toggle_LastPosition = nil
	local WindowAssets = {}
	local Tabs = {}

	local Roblox_Studio_UI = Instance.new("ScreenGui")
	local Frame = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local shadow = Instance.new("ImageLabel")
	local UICorner_2 = Instance.new("UICorner")
	local Title = Instance.new("TextLabel")
	local UserProfile = Instance.new("Frame")
	local UICorner_3 = Instance.new("UICorner")
	local shadow_2 = Instance.new("ImageLabel")
	local UICorner_4 = Instance.new("UICorner")
	local UserName = Instance.new("TextLabel")
	local UserImage = Instance.new("ImageLabel")
	local UICorner_5 = Instance.new("UICorner")
	local UserStatsCustom = Instance.new("TextLabel")
	local Section = Instance.new("ScrollingFrame")
	local UIGridLayout = Instance.new("UIGridLayout")
	local SectionBlackground = Instance.new("Frame")
	local UICorner_6 = Instance.new("UICorner")
	local UIGradient = Instance.new("UIGradient")
	local Toggle = Instance.new("TextButton")
	local UICorner_7 = Instance.new("UICorner")
	local UIStroke = Instance.new("UIStroke")
	local UIGradient_2 = Instance.new("UIGradient")
	local UIGradient_3 = Instance.new("UIGradient")

	Roblox_Studio_UI.Name = "{0x"..tostring(math.random(1,100))..tostring(math.random(1,100)).."x"..tostring(math.random(1,100)).."x6}"
	Roblox_Studio_UI.IgnoreGuiInset = true
	Roblox_Studio_UI.Parent = Core
	Roblox_Studio_UI.ResetOnSpawn = false

	Frame.Parent = Roblox_Studio_UI
	Frame.AnchorPoint = Vector2.new(0.5, 0.5)
	Frame.BackgroundColor3 = Color3.fromRGB(48, 48, 48)
	Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Frame.BorderSizePixel = 0
	Frame.Position = UDim2.new(0.49999997, 0, 0.499320686, 0)
	Frame.Size = UDim2.new(0.37, 0, 0.43, 0)
	Frame.ZIndex = -1
	Frame.ClipsDescendants = true
	Frame.Active = true

	UICorner.CornerRadius = UDim.new(0, 4)
	UICorner.Parent = Frame

	shadow.Name = "shadow"
	shadow.Parent = Frame
	shadow.AnchorPoint = Vector2.new(0.5, 0.5)
	shadow.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	shadow.BackgroundTransparency = 1.000
	shadow.Position = UDim2.new(0.494422138, 0, 0.5, 0)
	shadow.Size = UDim2.new(1.10000002, 0, 1.10000002, 0)
	shadow.ZIndex = -5
	shadow.Image = "rbxassetid://7912134082"
	shadow.ImageColor3 = Color3.fromRGB(0, 0, 0)
	shadow.ImageTransparency = 0.500
	shadow.ScaleType = Enum.ScaleType.Slice
	shadow.SliceCenter = Rect.new(95, 95, 205, 205)
	shadow.Rotation = 0.1

	UICorner_2.CornerRadius = UDim.new(0, 4)
	UICorner_2.Parent = shadow

	Title.Name = "Title"
	Title.Parent = Frame
	Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Title.BackgroundTransparency = 1.000
	Title.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Title.BorderSizePixel = 0
	Title.Position = UDim2.new(0.0225903615, 0, 0.025475543, 0)
	Title.Size = UDim2.new(0.699999988, 0, 0.100000001, 0)
	Title.Font = Enum.Font.GothamMedium
	Title.Text = TitleStr or "HOME"
	Title.TextColor3 = Color3.fromRGB(255, 255, 255)
	Title.TextScaled = true
	Title.TextSize = 14.000
	Title.TextWrapped = true
	Title.TextXAlignment = Enum.TextXAlignment.Left
	Title.RichText = true
	
	UserProfile.Name = "UserProfile"
	UserProfile.Parent = Frame
	UserProfile.BackgroundColor3 = Color3.fromRGB(18, 18, 18)
	UserProfile.BackgroundTransparency = 0.250
	UserProfile.BorderColor3 = Color3.fromRGB(0, 0, 0)
	UserProfile.BorderSizePixel = 0
	UserProfile.Position = UDim2.new(0.0225903615, 0, 0.810971439, 0)
	UserProfile.Size = UDim2.new(0.300000012, 0, 0.150000006, 0)

	UICorner_3.CornerRadius = UDim.new(0, 4)
	UICorner_3.Parent = UserProfile

	shadow_2.Name = "shadow"
	shadow_2.Parent = UserProfile
	shadow_2.AnchorPoint = Vector2.new(0.5, 0.5)
	shadow_2.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	shadow_2.BackgroundTransparency = 1.000
	shadow_2.Position = UDim2.new(0.5, 0, 0.5, 0)
	shadow_2.Size = UDim2.new(1.10000002, 0, 1.10000002, 0)
	shadow_2.ZIndex = -5
	shadow_2.Image = "rbxassetid://7912134082"
	shadow_2.ImageColor3 = Color3.fromRGB(0, 0, 0)
	shadow_2.ImageTransparency = 0.500
	shadow_2.ScaleType = Enum.ScaleType.Slice
	shadow_2.SliceCenter = Rect.new(95, 95, 205, 205)

	UICorner_4.CornerRadius = UDim.new(0, 4)
	UICorner_4.Parent = shadow_2

	UserName.Name = "UserName"
	UserName.Parent = UserProfile
	UserName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	UserName.BackgroundTransparency = 1.000
	UserName.BorderColor3 = Color3.fromRGB(0, 0, 0)
	UserName.BorderSizePixel = 0
	UserName.Position = UDim2.new(0.314219832, 0, 0.0880636051, 0)
	UserName.Size = UDim2.new(0.634071112, 0, 0.243000001, 0)
	UserName.Font = Enum.Font.GothamMedium
	UserName.Text = LUser.Name or "coptervdo"
	UserName.TextColor3 = Color3.fromRGB(255, 255, 255)
	UserName.TextScaled = true
	UserName.TextSize = 14.000
	UserName.TextWrapped = true
	UserName.TextXAlignment = Enum.TextXAlignment.Left

	UserImage.Name = "UserImage"
	UserImage.Parent = UserProfile
	UserImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	UserImage.BackgroundTransparency = 1.000
	UserImage.BorderColor3 = Color3.fromRGB(0, 0, 0)
	UserImage.BorderSizePixel = 0
	UserImage.Position = UDim2.new(0.026030045, 0, 0.0880636051, 0)
	UserImage.Size = UDim2.new(0.800000012, 0, 0.800000012, 0)
	UserImage.SizeConstraint = Enum.SizeConstraint.RelativeYY
	UserImage.Image = game:GetService"Players":GetUserThumbnailAsync(LUser.UserId,Enum.ThumbnailType.HeadShot,Enum.ThumbnailSize.Size150x150) or "rbxassetid://9828069191"

	UICorner_5.CornerRadius = UDim.new(0, 4)
	UICorner_5.Parent = UserImage

	UserStatsCustom.Name = "UserStatsCustom"
	UserStatsCustom.Parent = UserProfile
	UserStatsCustom.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	UserStatsCustom.BackgroundTransparency = 1.000
	UserStatsCustom.BorderColor3 = Color3.fromRGB(0, 0, 0)
	UserStatsCustom.BorderSizePixel = 0
	UserStatsCustom.Position = UDim2.new(0.314219832, 0, 0.465480596, 0)
	UserStatsCustom.Size = UDim2.new(0.634071112, 0, 0.422583789, 0)
	UserStatsCustom.Font = Enum.Font.GothamBold
	UserStatsCustom.Text = UserStats or "None"
	UserStatsCustom.TextColor3 = Color3.fromRGB(188, 255, 87)
	UserStatsCustom.TextScaled = true
	UserStatsCustom.TextSize = 14.000
	UserStatsCustom.TextWrapped = true
	UserStatsCustom.TextXAlignment = Enum.TextXAlignment.Left

	Section.Name = "Section"
	Section.Parent = Frame
	Section.AnchorPoint = Vector2.new(0.5, 0.5)
	Section.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	Section.BackgroundTransparency = 1.000
	Section.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Section.BorderSizePixel = 0
	Section.Position = UDim2.new(0.5, 0, 0.463202, 0)
	Section.Size = UDim2.new(0.774999976, 0, 0.637756586, 0)
	Section.ZIndex = 5
	Section.ScrollBarThickness = 2

	UIGridLayout.Parent = Section
	UIGridLayout.SortOrder = Enum.SortOrder.LayoutOrder
	UIGridLayout.CellPadding = UDim2.new(0.05, 0,0, 5)
	UIGridLayout.CellSize = UDim2.new(0.3, 0,0, 0)
	UIGridLayout.FillDirectionMaxCells = 5

	SectionBlackground.Name = "SectionBlackground"
	SectionBlackground.Parent = Frame
	SectionBlackground.AnchorPoint = Vector2.new(0.5, 0.5)
	SectionBlackground.BackgroundColor3 = Color3.fromRGB(39, 39, 39)
	SectionBlackground.BackgroundTransparency = 0.550
	SectionBlackground.BorderColor3 = Color3.fromRGB(0, 0, 0)
	SectionBlackground.BorderSizePixel = 0
	SectionBlackground.Position = UDim2.new(0.5, 0, 0.463, 0)
	SectionBlackground.Size = UDim2.new(0.774999976, 0, 0.638000011, 0)

	UICorner_6.CornerRadius = UDim.new(0, 9)
	UICorner_6.Parent = SectionBlackground

	UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 1.00), NumberSequenceKeypoint.new(0.11, 0.00), NumberSequenceKeypoint.new(0.94, 0.00), NumberSequenceKeypoint.new(1.00, 1.00)}
	UIGradient.Parent = SectionBlackground

	Toggle.Name = "Toggle"
	Toggle.Parent = Frame
	Toggle.BackgroundColor3 = Color3.fromRGB(39, 39, 39)
	Toggle.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Toggle.BorderSizePixel = 0
	Toggle.Position = UDim2.new(0.919557393, 0, 0.025475543, 0)
	Toggle.Size = UDim2.new(0.100000001, 0, 0.100000001, 0)
	Toggle.SizeConstraint = Enum.SizeConstraint.RelativeYY
	Toggle.Font = Enum.Font.GothamBold
	Toggle.Text = "X"
	Toggle.TextColor3 = Color3.fromRGB(255, 255, 255)
	Toggle.TextScaled = true
	Toggle.TextSize = 14.000
	Toggle.TextWrapped = true

	UICorner_7.CornerRadius = UDim.new(0, 4)
	UICorner_7.Parent = Toggle

	UIStroke.Thickness = 2.300
	UIStroke.Transparency = 0.750
	UIStroke.Color = Color3.fromRGB(255, 255, 255)
	UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	UIStroke.Parent = Toggle

	UIGradient_2.Rotation = -25
	UIGradient_2.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.42), NumberSequenceKeypoint.new(1.00, 0.00)}
	UIGradient_2.Parent = UIStroke

	UIGradient_3.Rotation = -25
	UIGradient_3.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.42), NumberSequenceKeypoint.new(1.00, 0.00)}
	UIGradient_3.Parent = Toggle

	UIGridLayout:GetPropertyChangedSignal('AbsoluteContentSize'):Connect(function()
		wait()
		TweenService:Create(Section,TweenInfo.new(0.3),{CanvasSize = UDim2.new(0,0,0,UIGridLayout.AbsoluteContentSize.Y * 2.1)}):Play()
	end)
	
	local LogLoad = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local LOAD = Instance.new("Frame")
	local UICorner_2 = Instance.new("UICorner")

	LogLoad.Name = "LogLoad"
	LogLoad.Parent = Frame
	LogLoad.BackgroundColor3 = Color3.fromRGB(29, 29, 29)
	LogLoad.BackgroundTransparency = 0.700
	LogLoad.BorderColor3 = Color3.fromRGB(0, 0, 0)
	LogLoad.BorderSizePixel = 0
	LogLoad.Position = UDim2.new(0.356644034, 0, 0.840692937, 0)
	LogLoad.Size = UDim2.new(0.60225457, 0, 0.100000009, 0)

	UICorner.CornerRadius = UDim.new(0, 4)
	UICorner.Parent = LogLoad

	LOAD.Name = "LOAD"
	LOAD.Parent = LogLoad
	LOAD.AnchorPoint = Vector2.new(0, 0.5)
	LOAD.BackgroundColor3 = Color3.fromRGB(0, 132, 255)
	LOAD.BackgroundTransparency = 1
	LOAD.BorderColor3 = Color3.fromRGB(0, 0, 0)
	LOAD.BorderSizePixel = 0
	LOAD.Position = UDim2.new(0, 0, 0.5, 0)
	LOAD.Size = UDim2.new(1, 0, 0.699999988, 0)

	UICorner_2.CornerRadius = UDim.new(0, 4)
	UICorner_2.Parent = LOAD

	local function MakeLoad(timeing)
		LOAD.Size = UDim2.new(0,0,1,0)
		LOAD.BackgroundTransparency = 0.800
		local tween = TweenService:Create(LOAD,TweenInfo.new(timeing,Enum.EasingStyle.Exponential),{Size = UDim2.new(1,0,1,0),BackgroundTransparency = 0.85})
		tween:Play()
		tween.Completed:Wait()
		TweenService:Create(LOAD,TweenInfo.new(0.45),{BackgroundTransparency = 1}):Play()
	end

	MakeLoad(0.1)


	function WindowAssets:NewSection(TitleJJ,Image,ImgColor)
		Image = Image or RBS_UI.ImageIcon.Server
		ImgColor = ImgColor or Color3.fromRGB(255,255,255)
		local SectionAssets = {}
		-- Create Tab --
		local Tab = Instance.new("Frame")
		local UICorner = Instance.new("UICorner")
		local ScrollingFrame = Instance.new("ScrollingFrame")
		local UIListLayout = Instance.new("UIListLayout")
		local Close = Instance.new("TextButton")
		local UIGradient = Instance.new("UIGradient")
		local UIStroke = Instance.new("UIStroke")
		local UIGradient_2 = Instance.new("UIGradient")
		local UICorner_2 = Instance.new("UICorner")

		Scrol(ScrollingFrame,UIListLayout)

		Tab.Name = "Tab"
		Tab.Parent = Frame
		Tab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Tab.BackgroundTransparency = 1.000
		Tab.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Tab.BorderSizePixel = 0
		Tab.ClipsDescendants = true
		Tab.Position = UDim2.new(1, 0,0.14, 0)
		Tab.Size = UDim2.new(0.774999976, 0, 0.638000011, 0)
		Tab.AnchorPoint = Vector2.new(0,0)
		Tab.Visible = false

		UICorner.CornerRadius = UDim.new(0, 9)
		UICorner.Parent = Tab

		ScrollingFrame.Parent = Tab
		ScrollingFrame.Active = true
		ScrollingFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ScrollingFrame.BackgroundTransparency = 1.000
		ScrollingFrame.BorderColor3 = Color3.fromRGB(0, 0, 0)
		ScrollingFrame.BorderSizePixel = 0
		ScrollingFrame.Position = UDim2.new(0.136027992, 0, 0.0465853699, 0)
		ScrollingFrame.Size = UDim2.new(0.833404601, 0, 0.930034816, 0)
		ScrollingFrame.CanvasSize = UDim2.new(0, 0, 0, 1000)
		ScrollingFrame.ScrollBarThickness = 2

		UIListLayout.Parent = ScrollingFrame
		UIListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
		UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		UIListLayout.Padding = UDim.new(0, 5)

		Close.Name = "Close"
		Close.Parent = Tab
		Close.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
		Close.BackgroundTransparency = 0.800
		Close.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Close.BorderSizePixel = 0
		Close.Position = UDim2.new(0.0356263816, 0, 0.0465853699, 0)
		Close.Size = UDim2.new(0.150000006, 0, 0.150000006, 0)
		Close.SizeConstraint = Enum.SizeConstraint.RelativeYY
		Close.Font = Enum.Font.GothamBold
		Close.Text = "<"
		Close.TextColor3 = Color3.fromRGB(255, 255, 255)
		Close.TextScaled = true
		Close.TextSize = 14.000
		Close.TextWrapped = true

		UIGradient.Rotation = -25
		UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.42), NumberSequenceKeypoint.new(1.00, 0.00)}
		UIGradient.Parent = Close

		UIStroke.Thickness = 2.300
		UIStroke.Transparency = 0.750
		UIStroke.Color = Color3.fromRGB(255, 255, 255)
		UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
		UIStroke.Parent = Close

		UIGradient_2.Rotation = -25
		UIGradient_2.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.42), NumberSequenceKeypoint.new(1.00, 0.00)}
		UIGradient_2.Parent = UIStroke

		UICorner_2.CornerRadius = UDim.new(0, 4)
		UICorner_2.Parent = Close
		-----------
		-- Crate Button --
		local TabButton = Instance.new("Frame")
		local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")
		local UICorner = Instance.new("UICorner")
		local Shaodw = Instance.new("Frame")
		local UIStroke = Instance.new("UIStroke")
		local UIGradient = Instance.new("UIGradient")
		local UICorner_2 = Instance.new("UICorner")
		local ImageG = Instance.new("ImageLabel")
		local UICorner_3 = Instance.new("UICorner")
		local UIGradient_2 = Instance.new("UIGradient")
		local Frame = Instance.new("Frame")
		local UICorner_4 = Instance.new("UICorner")
		local UIGradient_3 = Instance.new("UIGradient")
		local Title = Instance.new("TextLabel")
		local UIGradient_4 = Instance.new("UIGradient")
		local UIPadding = Instance.new("UIPadding")

		TabButton.Name = "TabButton"
		TabButton.Parent = Section
		TabButton.BackgroundColor3 = Color3.fromRGB(53, 53, 53)
		TabButton.BorderColor3 = Color3.fromRGB(0, 0, 0)
		TabButton.BorderSizePixel = 0
		TabButton.Size = UDim2.new(0, 100, 0, 100)

		UIAspectRatioConstraint.AspectRatio = 1
		UIAspectRatioConstraint.AspectType = Enum.AspectType.ScaleWithParentSize
		UIAspectRatioConstraint.DominantAxis= Enum.DominantAxis.Width
		UIAspectRatioConstraint.Parent = TabButton

		UICorner.CornerRadius = UDim.new(0, 4)
		UICorner.Parent = TabButton

		Shaodw.Name = "Shaodw"
		Shaodw.Parent = TabButton
		Shaodw.AnchorPoint = Vector2.new(0.5, 0.5)
		Shaodw.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Shaodw.BackgroundTransparency = 1.000
		Shaodw.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Shaodw.BorderSizePixel = 0
		Shaodw.Position = UDim2.new(0.5, 0, 0.5, 0)
		Shaodw.Size = UDim2.new(0.899999976, 0, 0.899999976, 0)

		UIStroke.Thickness = 2.000
		UIStroke.Transparency = 0.300
		UIStroke.Color = Color3.fromRGB(255, 255, 255)
		UIStroke.Parent = Shaodw

		UIGradient.Rotation = -45
		UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.26), NumberSequenceKeypoint.new(1.00, 0.00)}
		UIGradient.Parent = UIStroke

		UICorner_2.CornerRadius = UDim.new(0, 4)
		UICorner_2.Parent = Shaodw

		ImageG.Name = "Image"
		ImageG.Parent = TabButton
		ImageG.AnchorPoint = Vector2.new(0.5, 0.5)
		ImageG.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ImageG.BackgroundTransparency = 1.000
		ImageG.BorderColor3 = Color3.fromRGB(0, 0, 0)
		ImageG.BorderSizePixel = 0
		ImageG.Position = UDim2.new(0.5, 0, 0.414252877, 0)
		ImageG.Size = UDim2.new(0.600000024, 0, 0.600000024, 0)
		ImageG.ZIndex = 5
		ImageG.Image = Image or "rbxassetid://7734053426"
		ImageG.ImageTransparency = 0.200
		ImageG.ScaleType = Enum.ScaleType.Fit
		ImageG.ImageColor3 = ImgColor

		UICorner_3.CornerRadius = UDim.new(0, 4)
		UICorner_3.Parent = ImageG

		UIGradient_2.Rotation = -45
		UIGradient_2.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.67), NumberSequenceKeypoint.new(1.00, 0.00)}
		UIGradient_2.Parent = ImageG

		Frame.Parent = TabButton
		Frame.AnchorPoint = Vector2.new(0.5, 0)
		Frame.BackgroundColor3 = Color3.fromRGB(94, 94, 94)
		Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Frame.BorderSizePixel = 0
		Frame.Position = UDim2.new(0.5, 0, 0.757000029, 0)
		Frame.Size = UDim2.new(0.699999988, 0, 0.0399999991, 0)
		Frame.ZIndex = 2

		UICorner_4.CornerRadius = UDim.new(0, 15)
		UICorner_4.Parent = Frame

		UIGradient_3.Rotation = -45
		UIGradient_3.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
		UIGradient_3.Parent = Frame

		Title.Name = "Title"
		Title.Parent = TabButton
		Title.AnchorPoint = Vector2.new(0.5, 1)
		Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Title.BackgroundTransparency = 1.000
		Title.BorderColor3 = Color3.fromRGB(0, 0, 0)
		Title.BorderSizePixel = 0
		Title.Position = UDim2.new(0.5, 0, 0.911557317, 0)
		Title.Size = UDim2.new(0.699999988, 0, 0.1, 0)
		Title.ZIndex = 5
		Title.Font = Enum.Font.GothamBold
		Title.Text = TitleJJ or "Server"
		Title.TextColor3 = Color3.fromRGB(255, 255, 255)
		Title.TextScaled = true
		Title.TextSize = 14.000
		Title.TextWrapped = true
		Title.RichText = true
		UIGradient_4.Rotation = -45
		UIGradient_4.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
		UIGradient_4.Parent = Title

		UIPadding.Parent = TabButton
		UIPadding.PaddingBottom = UDim.new(0, 1)
		UIPadding.PaddingLeft = UDim.new(0, 1)
		UIPadding.PaddingRight = UDim.new(0, 1)
		UIPadding.PaddingTop = UDim.new(0, 1)

		local TsbButtonCllicked = Instance.new("TextButton")
		local CurrentSize = -3.5
		
		TsbButtonCllicked.Name = "TsbButtonCllicked"
		TsbButtonCllicked.Parent = TabButton
		TsbButtonCllicked.AnchorPoint = Vector2.new(0.5, 0.5)
		TsbButtonCllicked.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		TsbButtonCllicked.BackgroundTransparency = 1.000
		TsbButtonCllicked.BorderColor3 = Color3.fromRGB(0, 0, 0)
		TsbButtonCllicked.BorderSizePixel = 0
		TsbButtonCllicked.Position = UDim2.new(0.5, 0, 0.5, 0)
		TsbButtonCllicked.Size = UDim2.new(1, 0, 1, 0)
		TsbButtonCllicked.Font = Enum.Font.SourceSans
		TsbButtonCllicked.TextColor3 = Color3.fromRGB(0, 0, 0)
		TsbButtonCllicked.TextSize = 14.000
		TsbButtonCllicked.TextTransparency = 1.000

		table.insert(Tabs,Tab)
		
		TsbButtonCllicked.MouseEnter:Connect(function()
			
			TweenService:Create(UIPadding,TweenInfo.new(0.3,Enum.EasingStyle.Back,Enum.EasingDirection.Out),{
				PaddingBottom = UDim.new(0, CurrentSize),
				PaddingLeft = UDim.new(0, CurrentSize),
				PaddingRight = UDim.new(0, CurrentSize),
				PaddingTop = UDim.new(0, CurrentSize),
			}):Play()
			
		end)
		
		TsbButtonCllicked.MouseLeave:Connect(function()
			TweenService:Create(UIPadding,TweenInfo.new(0.3,Enum.EasingStyle.Back),{
				PaddingBottom = UDim.new(0, 1),
				PaddingLeft = UDim.new(0, 0),
				PaddingRight = UDim.new(0, 1),
				PaddingTop = UDim.new(0, 1),
			}):Play()
		end)
		
		local function OnToggleTo(value)
			local CurrentTime = 0.1
			coroutine.wrap(function()
				MakeLoad(CurrentTime * math.random(7,11) / 3)
			end)()
			if value then
				for i,v in ipairs(Tabs) do
					if v ~= Tab then
						local tw = TweenService:Create(v,TweenInfo.new(CurrentTime),{Position = UDim2.new(1, 0,0.14, 0)})
						tw:Play()
					else
						v.Visible = true
						TweenService:Create(v,TweenInfo.new(CurrentTime),{Position = UDim2.new(0.115, 0,0.14, 0)}):Play()
					end
				end
				TweenService:Create(Section,TweenInfo.new(CurrentTime),{Position = UDim2.new(-0.4, 0,0.463, 0)}):Play()
			else
				Section.Visible = true
				TweenService:Create(Section,TweenInfo.new(CurrentTime),{Position = UDim2.new(0.5, 0,0.463, 0)}):Play()
				for i,v in ipairs(Tabs) do
					local tw = TweenService:Create(v,TweenInfo.new(CurrentTime),{Position = UDim2.new(1, 0,0.14, 0)})
					tw:Play()
				end
			end
		end

		TabButton.Active = true
		TsbButtonCllicked.Active = true
		TsbButtonCllicked.ZIndex = 5
		TsbButtonCllicked.Visible = true
		TsbButtonCllicked.MouseButton1Click:Connect(function(Input)
			Create_Ripple(TabButton)
			OnToggleTo(true)
		end)

		Close.MouseButton1Click:Connect(function()
			Create_Ripple(Close)
			OnToggleTo(false)
		end)

		function SectionAssets:NewButton(LabelStr:string,callback:FunctionalTest)
			local ButtonAsset = {}
			callback = callback or function() end
			local Button = Instance.new("Frame")
			local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")
			local UICorner = Instance.new("UICorner")
			local UIPadding = Instance.new("UIPadding")
			local UIGradient = Instance.new("UIGradient")
			local Label = Instance.new("TextLabel")
			local UICorner_2 = Instance.new("UICorner")
			local UIGradient_2 = Instance.new("UIGradient")
			local Image = Instance.new("ImageLabel")
			local UICorner_3 = Instance.new("UICorner")
			local UIGradient_3 = Instance.new("UIGradient")
			local Button_Clicked = Instance.new("TextButton")

			Button.Name = "Button"
			Button.Parent = ScrollingFrame
			Button.BackgroundColor3 = Color3.fromRGB(53, 53, 53)
			Button.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Button.BorderSizePixel = 0
			Button.Size = UDim2.new(0.899999976, 0, 0.5, 0)

			UIAspectRatioConstraint.Parent = Button
			UIAspectRatioConstraint.AspectRatio = 5.000

			UICorner.CornerRadius = UDim.new(0, 4)
			UICorner.Parent = Button

			UIPadding.Parent = Button
			UIPadding.PaddingBottom = UDim.new(0, 1)
			UIPadding.PaddingLeft = UDim.new(0, 1)
			UIPadding.PaddingRight = UDim.new(0, 1)
			UIPadding.PaddingTop = UDim.new(0, 1)

			UIGradient.Rotation = -45
			UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient.Parent = Button

			Label.Name = "Label"
			Label.Parent = Button
			Label.AnchorPoint = Vector2.new(0, 0.5)
			Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label.BackgroundTransparency = 1.000
			Label.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Label.BorderSizePixel = 0
			Label.Position = UDim2.new(0.0240000002, 0, 0.5, 0)
			Label.Size = UDim2.new(0.799999952, 0, 0.508580387, 0)
			Label.Font = Enum.Font.GothamBold
			Label.Text = LabelStr or "Button"
			Label.TextColor3 = Color3.fromRGB(255, 255, 255)
			Label.TextScaled = true
			Label.TextSize = 14.000
			Label.TextWrapped = true
			Label.TextXAlignment = Enum.TextXAlignment.Left

			UICorner_2.CornerRadius = UDim.new(0, 4)
			UICorner_2.Parent = Label

			UIGradient_2.Rotation = -45
			UIGradient_2.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.01)}
			UIGradient_2.Parent = Label

			Image.Name = "Image"
			Image.Parent = Button
			Image.AnchorPoint = Vector2.new(0.5, 0.5)
			Image.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Image.BackgroundTransparency = 1.000
			Image.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Image.BorderSizePixel = 0
			Image.Position = UDim2.new(0.898999989, 0, 0.5, 0)
			Image.Size = UDim2.new(0.600000024, 0, 0.600000024, 0)
			Image.SizeConstraint = Enum.SizeConstraint.RelativeYY
			Image.ZIndex = 5
			Image.Image = "rbxassetid://7734010488"
			Image.ImageTransparency = 0.200
			Image.ScaleType = Enum.ScaleType.Fit

			UICorner_3.CornerRadius = UDim.new(0, 4)
			UICorner_3.Parent = Image

			UIGradient_3.Rotation = -45
			UIGradient_3.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.67), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_3.Parent = Image

			Button_Clicked.Name = "Button_Clicked"
			Button_Clicked.Parent = Button
			Button_Clicked.AnchorPoint = Vector2.new(0.5, 0.5)
			Button_Clicked.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Button_Clicked.BackgroundTransparency = 1.000
			Button_Clicked.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Button_Clicked.BorderSizePixel = 0
			Button_Clicked.Position = UDim2.new(0.5, 0, 0.5, 0)
			Button_Clicked.Size = UDim2.new(0.899999976, 0, 0.899999976, 0)
			Button_Clicked.ZIndex = 5
			Button_Clicked.Font = Enum.Font.SourceSans
			Button_Clicked.TextColor3 = Color3.fromRGB(0, 0, 0)
			Button_Clicked.TextSize = 14.000
			Button_Clicked.TextTransparency = 1.000

			Button_Clicked.MouseButton1Click:Connect(function()
				Create_Ripple(Button)
				callback()
			end)

			function ButtonAsset:Set(NewLabelStr)
				Label.Text = NewLabelStr
			end

			return ButtonAsset;
		end

		function SectionAssets:NewToggle(LabelStr:string,info:boolean,callback:FunctionalTest)
			local ToggleAsset = {}
			callback = callback or function() end
			local ToggleValue = info or false
			local Toggle = Instance.new("Frame")
			local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")
			local UICorner = Instance.new("UICorner")
			local UIPadding = Instance.new("UIPadding")
			local UIGradient = Instance.new("UIGradient")
			local Label = Instance.new("TextLabel")
			local UICorner_2 = Instance.new("UICorner")
			local UIGradient_2 = Instance.new("UIGradient")
			local ToggleImage = Instance.new("ImageLabel")
			local UICorner_3 = Instance.new("UICorner")
			local UIGradient_3 = Instance.new("UIGradient")
			local ToggleEffect = Instance.new("UIStroke")
			local Button_Clicked = Instance.new("TextButton")

			Toggle.Name = "Toggle"
			Toggle.Parent = ScrollingFrame
			Toggle.BackgroundColor3 = Color3.fromRGB(53, 53, 53)
			Toggle.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Toggle.BorderSizePixel = 0
			Toggle.Size = UDim2.new(0.899999976, 0, 0.5, 0)

			UIAspectRatioConstraint.Parent = Toggle
			UIAspectRatioConstraint.AspectRatio = 5.000

			UICorner.CornerRadius = UDim.new(0, 4)
			UICorner.Parent = Toggle

			UIPadding.Parent = Toggle
			UIPadding.PaddingBottom = UDim.new(0, 1)
			UIPadding.PaddingLeft = UDim.new(0, 1)
			UIPadding.PaddingRight = UDim.new(0, 1)
			UIPadding.PaddingTop = UDim.new(0, 1)

			UIGradient.Rotation = -45
			UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient.Parent = Toggle

			Label.Name = "Label"
			Label.Parent = Toggle
			Label.AnchorPoint = Vector2.new(0, 0.5)
			Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label.BackgroundTransparency = 1.000
			Label.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Label.BorderSizePixel = 0
			Label.Position = UDim2.new(0.0240000002, 0, 0.5, 0)
			Label.Size = UDim2.new(0.799999952, 0, 0.508580387, 0)
			Label.Font = Enum.Font.GothamBold
			Label.Text = LabelStr or "Toggle"
			Label.TextColor3 = Color3.fromRGB(255, 255, 255)
			Label.TextScaled = true
			Label.TextSize = 14.000
			Label.TextWrapped = true
			Label.TextXAlignment = Enum.TextXAlignment.Left

			UICorner_2.CornerRadius = UDim.new(0, 4)
			UICorner_2.Parent = Label

			UIGradient_2.Rotation = -45
			UIGradient_2.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.01)}
			UIGradient_2.Parent = Label

			ToggleImage.Name = "ToggleImage"
			ToggleImage.Parent = Toggle
			ToggleImage.AnchorPoint = Vector2.new(0.5, 0.5)
			ToggleImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			ToggleImage.BackgroundTransparency = 1.000
			ToggleImage.BorderColor3 = Color3.fromRGB(0, 0, 0)
			ToggleImage.BorderSizePixel = 0
			ToggleImage.Position = UDim2.new(0.898999989, 0, 0.5, 0)
			ToggleImage.Size = UDim2.new(0.600000024, 0, 0.600000024, 0)
			ToggleImage.SizeConstraint = Enum.SizeConstraint.RelativeYY
			ToggleImage.ZIndex = 5
			ToggleImage.Image = "rbxassetid://10002398990"
			ToggleImage.ScaleType = Enum.ScaleType.Fit

			UICorner_3.CornerRadius = UDim.new(0, 4)
			UICorner_3.Parent = ToggleImage

			UIGradient_3.Rotation = -45
			UIGradient_3.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.67), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_3.Parent = ToggleImage

			ToggleEffect.Thickness = 3.300
			ToggleEffect.Transparency = 1.000
			ToggleEffect.Color = Color3.fromRGB(255, 255, 255)
			ToggleEffect.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
			ToggleEffect.Parent = ToggleImage

			Button_Clicked.Name = "Button_Clicked"
			Button_Clicked.Parent = Toggle
			Button_Clicked.AnchorPoint = Vector2.new(0.5, 0.5)
			Button_Clicked.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Button_Clicked.BackgroundTransparency = 1.000
			Button_Clicked.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Button_Clicked.BorderSizePixel = 0
			Button_Clicked.Position = UDim2.new(0.5, 0, 0.5, 0)
			Button_Clicked.Size = UDim2.new(0.899999976, 0, 0.899999976, 0)
			Button_Clicked.ZIndex = 5
			Button_Clicked.Font = Enum.Font.SourceSans
			Button_Clicked.TextColor3 = Color3.fromRGB(0, 0, 0)
			Button_Clicked.TextSize = 14.000
			Button_Clicked.TextTransparency = 1.000

			local function ToggleTo(value)
				if value then
					ToggleImage.Size = UDim2.new(0.4,0,0.4,0)
					ToggleEffect.Transparency = 0
					ToggleImage.Image = "rbxassetid://10002398990"
					TweenService:Create(ToggleImage,TweenInfo.new(0.2,Enum.EasingStyle.Back),{Size = UDim2.new(0.6,0,0.6,0)}):Play()
					TweenService:Create(ToggleEffect,TweenInfo.new(0.5),{Transparency = 1}):Play()
				else
					ToggleImage.Size = UDim2.new(0.4,0,0.4,0)
					ToggleEffect.Transparency = 0
					ToggleImage.Image = "rbxassetid://3944680095"
					TweenService:Create(ToggleImage,TweenInfo.new(0.2,Enum.EasingStyle.Back),{Size = UDim2.new(0.6,0,0.6,0)}):Play()
					TweenService:Create(ToggleEffect,TweenInfo.new(0.5),{Transparency = 1}):Play()
				end
			end

			Button_Clicked.MouseButton1Click:Connect(function()
				Create_Ripple(Toggle)
				if ToggleValue then
					ToggleValue = false
				else
					ToggleValue = true
				end

				ToggleTo(not ToggleValue)
				callback(ToggleValue)
			end)

			function ToggleAsset:Set(Value)
				ToggleValue = Value
				ToggleTo(not ToggleValue)
				callback(ToggleValue)
			end

			ToggleTo( not ToggleValue)

			return ToggleAsset
		end

		function SectionAssets:NewLabel(LabelStr:string)
			local LabelAsset = {}
			local Label = Instance.new("Frame")
			local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")
			local UICorner = Instance.new("UICorner")
			local Frame = Instance.new("Frame")
			local UICorner_2 = Instance.new("UICorner")
			local UIGradient = Instance.new("UIGradient")
			local UIPadding = Instance.new("UIPadding")
			local UIGradient_2 = Instance.new("UIGradient")
			local Label_2 = Instance.new("TextLabel")
			local UICorner_3 = Instance.new("UICorner")
			local UIGradient_3 = Instance.new("UIGradient")
			local Image = Instance.new("ImageLabel")
			local UICorner_4 = Instance.new("UICorner")
			local UIGradient_4 = Instance.new("UIGradient")

			Label.Name = "Label"
			Label.Parent = ScrollingFrame
			Label.BackgroundColor3 = Color3.fromRGB(72, 72, 72)
			Label.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Label.BorderSizePixel = 0
			Label.Size = UDim2.new(0.899999976, 0, 0.5, 0)

			UIAspectRatioConstraint.Parent = Label
			UIAspectRatioConstraint.AspectRatio = 5.000

			UICorner.CornerRadius = UDim.new(0, 4)
			UICorner.Parent = Label

			Frame.Parent = Label
			Frame.AnchorPoint = Vector2.new(0.5, 0)
			Frame.BackgroundColor3 = Color3.fromRGB(94, 94, 94)
			Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Frame.BorderSizePixel = 0
			Frame.Position = UDim2.new(0.5, 0, 0.757000029, 0)
			Frame.Size = UDim2.new(0.949999988, 0, 0.0399999991, 0)
			Frame.ZIndex = 2

			UICorner_2.CornerRadius = UDim.new(0, 15)
			UICorner_2.Parent = Frame

			UIGradient.Rotation = -45
			UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient.Parent = Frame

			UIPadding.Parent = Label
			UIPadding.PaddingBottom = UDim.new(0, 1)
			UIPadding.PaddingLeft = UDim.new(0, 1)
			UIPadding.PaddingRight = UDim.new(0, 1)
			UIPadding.PaddingTop = UDim.new(0, 1)

			UIGradient_2.Rotation = -45
			UIGradient_2.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_2.Parent = Label

			Label_2.Name = "Label"
			Label_2.Parent = Label
			Label_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label_2.BackgroundTransparency = 1.000
			Label_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Label_2.BorderSizePixel = 0
			Label_2.Position = UDim2.new(0.023720637, 0, 0.137377262, 0)
			Label_2.Size = UDim2.new(0.799999952, 0, 0.508580387, 0)
			Label_2.Font = Enum.Font.GothamMedium
			Label_2.Text = LabelStr or "?Label?"
			Label_2.TextColor3 = Color3.fromRGB(255, 255, 255)
			Label_2.TextScaled = true
			Label_2.TextSize = 14.000
			Label_2.TextWrapped = true
			Label_2.TextXAlignment = Enum.TextXAlignment.Left

			UICorner_3.CornerRadius = UDim.new(0, 4)
			UICorner_3.Parent = Label_2

			UIGradient_3.Rotation = -45
			UIGradient_3.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.01)}
			UIGradient_3.Parent = Label_2

			Image.Name = "Image"
			Image.Parent = Label
			Image.AnchorPoint = Vector2.new(0.5, 0.5)
			Image.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Image.BackgroundTransparency = 1.000
			Image.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Image.BorderSizePixel = 0
			Image.Position = UDim2.new(0.898976922, 0, 0.381153405, 0)
			Image.Size = UDim2.new(0.600000024, 0, 0.600000024, 0)
			Image.SizeConstraint = Enum.SizeConstraint.RelativeYY
			Image.ZIndex = 5
			Image.Image = "rbxassetid://7733914390"
			Image.ImageTransparency = 0.200
			Image.ScaleType = Enum.ScaleType.Fit

			UICorner_4.CornerRadius = UDim.new(0, 4)
			UICorner_4.Parent = Image

			UIGradient_4.Rotation = -45
			UIGradient_4.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.67), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_4.Parent = Image

			function LabelAsset:Set(NewLabel)
				Label_2.Text = NewLabel or "?Label?"
			end

			return LabelAsset;
		end

		function SectionAssets:NewDropdown(LabelStr:string,info:{string},callback:FunctionalTest)
			local DropdownAssets = {}
			local InfoList = info or {}
			callback = callback or function() end
			local DROPDOWN_TOGGLE = false
			local Dropdown = Instance.new("Frame")
			local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")
			local UICorner = Instance.new("UICorner")
			local UIPadding = Instance.new("UIPadding")
			local UIGradient = Instance.new("UIGradient")
			local UI = Instance.new("Frame")
			local UIGradient_2 = Instance.new("UIGradient")
			local UIPadding_2 = Instance.new("UIPadding")
			local UICorner_2 = Instance.new("UICorner")
			local Button_Clicked = Instance.new("TextButton")
			local Image = Instance.new("ImageLabel")
			local UICorner_3 = Instance.new("UICorner")
			local UIGradient_3 = Instance.new("UIGradient")
			local Label = Instance.new("TextLabel")
			local UICorner_4 = Instance.new("UICorner")
			local UIGradient_4 = Instance.new("UIGradient")
			local UIAspectRatioConstraint_2 = Instance.new("UIAspectRatioConstraint")
			local UIListLayout = Instance.new("UIListLayout")
			local Droplist = Instance.new("Frame")
			local UIGradient_5 = Instance.new("UIGradient")
			local UICorner_5 = Instance.new("UICorner")
			local UIStroke = Instance.new("UIStroke")
			local UIAspectRatioConstraint_3 = Instance.new("UIAspectRatioConstraint")
			local ScrollingFrameCSGO = Instance.new("ScrollingFrame")
			local UIListLayout_2 = Instance.new("UIListLayout")

			Scrol(ScrollingFrameCSGO,UIListLayout_2)

			Dropdown.Name = "Dropdown"
			Dropdown.Parent = ScrollingFrame
			Dropdown.BackgroundColor3 = Color3.fromRGB(53, 53, 53)
			Dropdown.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Dropdown.BorderSizePixel = 0
			Dropdown.Size = UDim2.new(0.899999976, 0, 0.5, 0)

			UIAspectRatioConstraint.Parent = Dropdown
			UIAspectRatioConstraint.AspectRatio = 1.500
			UIAspectRatioConstraint.AspectType = Enum.AspectType.ScaleWithParentSize

			UICorner.CornerRadius = UDim.new(0, 4)
			UICorner.Parent = Dropdown

			UIPadding.Parent = Dropdown
			UIPadding.PaddingBottom = UDim.new(0, 1)
			UIPadding.PaddingLeft = UDim.new(0, 1)
			UIPadding.PaddingRight = UDim.new(0, 1)
			UIPadding.PaddingTop = UDim.new(0, 1)

			UIGradient.Rotation = -45
			UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient.Parent = Dropdown

			UI.Name = "UI"
			UI.Parent = Dropdown
			UI.AnchorPoint = Vector2.new(0.5, 0.5)
			UI.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			UI.BackgroundTransparency = 1.000
			UI.BorderColor3 = Color3.fromRGB(0, 0, 0)
			UI.BorderSizePixel = 0
			UI.Position = UDim2.new(0.5, 0, 0.199000001, 0)
			UI.Size = UDim2.new(0.980000019, 0, 1, 0)

			UIGradient_2.Rotation = -45
			UIGradient_2.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_2.Parent = UI

			UIPadding_2.Parent = UI
			UIPadding_2.PaddingBottom = UDim.new(0, 1)
			UIPadding_2.PaddingLeft = UDim.new(0, 1)
			UIPadding_2.PaddingRight = UDim.new(0, 1)
			UIPadding_2.PaddingTop = UDim.new(0, 1)

			UICorner_2.CornerRadius = UDim.new(0, 4)
			UICorner_2.Parent = UI

			Button_Clicked.Name = "Button_Clicked"
			Button_Clicked.Parent = UI
			Button_Clicked.AnchorPoint = Vector2.new(0.5, 0.5)
			Button_Clicked.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Button_Clicked.BackgroundTransparency = 1.000
			Button_Clicked.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Button_Clicked.BorderSizePixel = 0
			Button_Clicked.Position = UDim2.new(0.5, 0, 0.5, 0)
			Button_Clicked.Size = UDim2.new(0.899999976, 0, 0.899999976, 0)
			Button_Clicked.ZIndex = 5
			Button_Clicked.Font = Enum.Font.SourceSans
			Button_Clicked.TextColor3 = Color3.fromRGB(0, 0, 0)
			Button_Clicked.TextSize = 14.000
			Button_Clicked.TextTransparency = 1.000

			Image.Name = "Image"
			Image.Parent = UI
			Image.AnchorPoint = Vector2.new(0.5, 0.5)
			Image.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Image.BackgroundTransparency = 1.000
			Image.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Image.BorderSizePixel = 0
			Image.Position = UDim2.new(0.898999989, 0, 0.5, 0)
			Image.Size = UDim2.new(0.600000024, 0, 0.600000024, 0)
			Image.SizeConstraint = Enum.SizeConstraint.RelativeYY
			Image.ZIndex = 5
			Image.Image = "rbxassetid://7733720604"
			Image.ImageTransparency = 0.200
			Image.ScaleType = Enum.ScaleType.Fit

			UICorner_3.CornerRadius = UDim.new(0, 4)
			UICorner_3.Parent = Image

			UIGradient_3.Rotation = -45
			UIGradient_3.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.67), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_3.Parent = Image

			Label.Name = "Label"
			Label.Parent = UI
			Label.AnchorPoint = Vector2.new(0, 0.5)
			Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label.BackgroundTransparency = 1.000
			Label.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Label.BorderSizePixel = 0
			Label.Position = UDim2.new(0.0240000002, 0, 0.5, 0)
			Label.Size = UDim2.new(0.799999952, 0, 0.508580387, 0)
			Label.Font = Enum.Font.GothamBold
			Label.Text = LabelStr or "?Dropdown?"
			Label.TextColor3 = Color3.fromRGB(255, 255, 255)
			Label.TextScaled = true
			Label.TextSize = 14.000
			Label.TextWrapped = true
			Label.TextXAlignment = Enum.TextXAlignment.Left

			UICorner_4.CornerRadius = UDim.new(0, 4)
			UICorner_4.Parent = Label

			UIGradient_4.Rotation = -45
			UIGradient_4.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.01)}
			UIGradient_4.Parent = Label

			UIAspectRatioConstraint_2.Parent = UI
			UIAspectRatioConstraint_2.AspectRatio = 5.500

			UIListLayout.Parent = Dropdown
			UIListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
			UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
			UIListLayout.Padding = UDim.new(0, 5)

			Droplist.Name = "Droplist"
			Droplist.Parent = Dropdown
			Droplist.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Droplist.BackgroundTransparency = 1.000
			Droplist.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Droplist.BorderSizePixel = 0
			Droplist.Position = UDim2.new(0.0394970365, 0, 0.285549611, 0)
			Droplist.Size = UDim2.new(0.925000072, 0, 0.658412158, 0)

			UIGradient_5.Rotation = -45
			UIGradient_5.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_5.Parent = Droplist

			UICorner_5.CornerRadius = UDim.new(0, 4)
			UICorner_5.Parent = Droplist

			UIStroke.Thickness = 5.600
			UIStroke.Transparency = 0.800
			UIStroke.Color = Color3.fromRGB(255, 255, 255)
			UIStroke.Parent = Droplist

			UIAspectRatioConstraint_3.Parent = Droplist
			UIAspectRatioConstraint_3.AspectRatio = 2.000

			ScrollingFrameCSGO.Parent = Droplist
			ScrollingFrameCSGO.Active = true
			ScrollingFrameCSGO.AnchorPoint = Vector2.new(0.5, 0.5)
			ScrollingFrameCSGO.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			ScrollingFrameCSGO.BackgroundTransparency = 1.000
			ScrollingFrameCSGO.BorderColor3 = Color3.fromRGB(0, 0, 0)
			ScrollingFrameCSGO.BorderSizePixel = 0
			ScrollingFrameCSGO.Position = UDim2.new(0.5, 0, 0.5, 0)
			ScrollingFrameCSGO.Size = UDim2.new(0.949999988, 0, 0.949999988, 0)
			ScrollingFrameCSGO.ScrollBarThickness = 3

			UIListLayout_2.Parent = ScrollingFrameCSGO
			UIListLayout_2.HorizontalAlignment = Enum.HorizontalAlignment.Center
			UIListLayout_2.SortOrder = Enum.SortOrder.LayoutOrder
			UIListLayout_2.Padding = UDim.new(0,5)

			local function DropdownSet(value)
				local Current = 0.15
				if value then
					TweenService:Create(UIAspectRatioConstraint,TweenInfo.new(Current),{AspectRatio = 1.5}):Play()
					TweenService:Create(Droplist,TweenInfo.new(Current),{Size = UDim2.new(0.925,0,0.658,0)}):Play()
					Droplist.Visible = true
				else
					TweenService:Create(UIAspectRatioConstraint,TweenInfo.new(Current),{AspectRatio = 5}):Play()
					TweenService:Create(Droplist,TweenInfo.new(Current),{Size = UDim2.new(0,0,0,0)}):Play()
					Droplist.Visible = false
				end
			end

			local function Show()
				for i,v:TextButton in ipairs(ScrollingFrameCSGO:GetChildren()) do
					if v:isA('TextButton') then
						v:Destroy()
					end
				end
				local Date = {}
				for i,v in ipairs(InfoList) do
					local Button = Instance.new("TextButton")
					local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")
					local UICorner = Instance.new("UICorner")
					local UIGradient = Instance.new("UIGradient")

					Button.Name = "Button"
					Button.Parent = ScrollingFrameCSGO
					Button.BackgroundColor3 = Color3.fromRGB(18, 18, 18)
					Button.BackgroundTransparency = 0.600
					Button.BorderColor3 = Color3.fromRGB(0, 0, 0)
					Button.BorderSizePixel = 0
					Button.Size = UDim2.new(0.899999976, 0, 0.5, 0)
					Button.Font = Enum.Font.GothamMedium
					Button.Text = v or "Dropdown List Button"
					Button.TextColor3 = Color3.fromRGB(255, 255, 255)
					Button.TextScaled = true
					Button.TextSize = 14.000
					Button.TextWrapped = true

					UIAspectRatioConstraint.Parent = Button
					UIAspectRatioConstraint.AspectRatio = 7.000

					UICorner.CornerRadius = UDim.new(0, 4)
					UICorner.Parent = Button

					UIGradient.Rotation = -45
					UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
					UIGradient.Parent = Button

					local UIStroke = Instance.new("UIStroke")
					UIStroke.Thickness = 1.300
					UIStroke.Transparency = 0.900
					UIStroke.Color = Color3.fromRGB(255, 255, 255)
					UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
					UIStroke.Parent = Button
					table.insert(Date,Button)
					Button.MouseButton1Click:Connect(function()
						Create_Ripple(Button)
						for i,vs in ipairs(Date) do
							local UIStrokeEE = vs:FindFirstChild("UIStroke")
							if vs==Button then
								TweenService:Create(UIStrokeEE,TweenInfo.new(0.1),{Transparency = 0.3}):Play()
							else
								TweenService:Create(UIStrokeEE,TweenInfo.new(0.1),{Transparency = 0.9}):Play()
							end
						end
						callback(v)
					end)
				end
			end

			Button_Clicked.MouseButton1Click:Connect(function()
				Create_Ripple(UI)
				if DROPDOWN_TOGGLE then
					DROPDOWN_TOGGLE = false
				else
					DROPDOWN_TOGGLE = true
				end
				DropdownSet(DROPDOWN_TOGGLE)
			end)

			DropdownSet(false)
			Show()

			function DropdownAssets:Set(List_New)
				InfoList = List_New
			end

			function DropdownAssets:Refresh()
				Show()
			end

			return DropdownAssets
		end

		function SectionAssets:NewSlider(Min:number,Max:number,callback:FunctionalTest)
			local SliderAssets = {}
			Min = Min or 1
			Max = Max or 500
			callback = callback or function() end
			local Slider = Instance.new("Frame")
			local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")
			local UICorner = Instance.new("UICorner")
			local UIPadding = Instance.new("UIPadding")
			local Front = Instance.new("Frame")
			local UICorner_2 = Instance.new("UICorner")
			local UIGradient = Instance.new("UIGradient")
			local NumberShowed = Instance.new("TextLabel")
			local Move = Instance.new("Frame")
			local UICorner_3 = Instance.new("UICorner")
			local UIGradient_2 = Instance.new("UIGradient")
			local Frame = Instance.new("Frame")
			local UICorner_4 = Instance.new("UICorner")
			local UIGradient_3 = Instance.new("UIGradient")

			Slider.Name = "Slider"
			Slider.Parent = ScrollingFrame
			Slider.BackgroundColor3 = Color3.fromRGB(53, 53, 53)
			Slider.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Slider.BorderSizePixel = 0
			Slider.Size = UDim2.new(0.899999976, 0, 0.5, 0)
			Slider.Active = true

			UIAspectRatioConstraint.Parent = Slider
			UIAspectRatioConstraint.AspectRatio = 5.000

			UICorner.CornerRadius = UDim.new(0, 4)
			UICorner.Parent = Slider

			UIPadding.Parent = Slider
			UIPadding.PaddingBottom = UDim.new(0, 1)
			UIPadding.PaddingLeft = UDim.new(0, 1)
			UIPadding.PaddingRight = UDim.new(0, 1)
			UIPadding.PaddingTop = UDim.new(0, 1)

			Front.Name = "Front"
			Front.Parent = Slider
			Front.AnchorPoint = Vector2.new(0.5, 0.5)
			Front.BackgroundColor3 = Color3.fromRGB(75, 75, 75)
			Front.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Front.BorderSizePixel = 0
			Front.Position = UDim2.new(0.5, 0, 0.5, 0)
			Front.Size = UDim2.new(0.975000024, 0, 0.550000012, 0)
			Front.Active = true

			UICorner_2.CornerRadius = UDim.new(0, 4)
			UICorner_2.Parent = Front

			UIGradient.Rotation = -45
			UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient.Parent = Front

			NumberShowed.Name = "NumberShowed"
			NumberShowed.Parent = Front
			NumberShowed.AnchorPoint = Vector2.new(0.5, 0.5)
			NumberShowed.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			NumberShowed.BackgroundTransparency = 1.000
			NumberShowed.BorderColor3 = Color3.fromRGB(0, 0, 0)
			NumberShowed.BorderSizePixel = 0
			NumberShowed.Position = UDim2.new(0.5, 0, 0.5, 0)
			NumberShowed.Size = UDim2.new(0.99000001, 0, 0.75, 0)
			NumberShowed.ZIndex = 5
			NumberShowed.Font = Enum.Font.GothamMedium
			NumberShowed.Text = tostring(Min) or "100"
			NumberShowed.TextColor3 = Color3.fromRGB(255, 255, 255)
			NumberShowed.TextScaled = true
			NumberShowed.TextSize = 14.000
			NumberShowed.TextWrapped = true

			Move.Name = "Move"
			Move.Parent = Front
			Move.AnchorPoint = Vector2.new(0, 0.5)
			Move.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
			Move.BackgroundTransparency = 0.600
			Move.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Move.BorderSizePixel = 0
			Move.Position = UDim2.new(0.00999999978, 0, 0.5, 0)
			Move.Size = UDim2.new(0.01, 0, 0.8, 0)
			Move.Active = true

			UICorner_3.CornerRadius = UDim.new(0, 4)
			UICorner_3.Parent = Move

			UIGradient_2.Rotation = -45
			UIGradient_2.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_2.Parent = Slider

			Frame.Parent = Slider
			Frame.AnchorPoint = Vector2.new(0.5, 0)
			Frame.BackgroundColor3 = Color3.fromRGB(94, 94, 94)
			Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Frame.BorderSizePixel = 0
			Frame.Position = UDim2.new(0.5, 0, 0.850000024, 0)
			Frame.Size = UDim2.new(0.949999988, 0, 0.0399999991, 0)
			Frame.ZIndex = 2

			UICorner_4.CornerRadius = UDim.new(0, 15)
			UICorner_4.Parent = Frame

			UIGradient_3.Rotation = -45
			UIGradient_3.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_3.Parent = Frame

			local Touching = false
			Front.InputBegan:Connect(function(Input)
				if Input.UserInputType == Enum.UserInputType.MouseButton1 or Input.UserInputType == Enum.UserInputType.Touch then
					Touching = true
					RBS_UI.CanMove = false
				end
			end)
			Front.InputEnded:Connect(function(Input)
				if Input.UserInputType == Enum.UserInputType.MouseButton1 or Input.UserInputType == Enum.UserInputType.Touch  then
					Touching = false
					RBS_UI.CanMove = true
				end
			end)
			UserInputService.InputChanged:Connect(function(Input)
				if Touching  and (Input.UserInputType == Enum.UserInputType.MouseMovement or Input.UserInputType == Enum.UserInputType.Touch) then 
					local SizeScale = math.clamp(((Input.Position.X - Front.AbsolutePosition.X) / Front.AbsoluteSize.X), 0, 1)
					local Value = math.floor(((Max - Min) * SizeScale) + Min)
					local SizeScaleDataSize = math.clamp(((Input.Position.X - Front.AbsolutePosition.X) / Front.AbsoluteSize.X), 0, 0.98)
					local Size = UDim2.fromScale(SizeScaleDataSize,0.8)
					NumberShowed.Text = Value
					TweenService:Create(Move,TweenInfo.new(0.1),{Size = Size}):Play()
					callback(Value)
				end
			end)

			function SliderAssets:Set(value)
				NumberShowed.Text = tostring(value)
				local SizeScale = math.clamp(value / Max,0,0.98)
				local Size = UDim2.fromScale(SizeScale,0.8)
				TweenService:Create(Move,TweenInfo.new(0.1),{Size = Size}):Play()
				callback(value)
			end

			return SliderAssets;
		end

		function SectionAssets:NewKeybinds(LabelStr:string,Info,callback)
			Info = Info or Enum.KeyCode.X
			callback = callback or function() end
			local IsWait = false
			local KeybindAssets = {}
			local KeyBind = Info
			local Keybinds = Instance.new("Frame")
			local UIAspectRatioConstraint = Instance.new("UIAspectRatioConstraint")
			local UICorner = Instance.new("UICorner")
			local UIPadding = Instance.new("UIPadding")
			local UIGradient = Instance.new("UIGradient")
			local Label = Instance.new("TextLabel")
			local UICorner_2 = Instance.new("UICorner")
			local UIGradient_2 = Instance.new("UIGradient")
			local Image = Instance.new("ImageLabel")
			local UICorner_3 = Instance.new("UICorner")
			local UIGradient_3 = Instance.new("UIGradient")
			local Button_Clicked = Instance.new("TextButton")
			local KEY = Instance.new("TextLabel")
			local UICorner_4 = Instance.new("UICorner")
			local UIGradient_4 = Instance.new("UIGradient")
			local UIStroke = Instance.new("UIStroke")

			Keybinds.Name = "Keybinds"
			Keybinds.Parent = ScrollingFrame
			Keybinds.BackgroundColor3 = Color3.fromRGB(53, 53, 53)
			Keybinds.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Keybinds.BorderSizePixel = 0
			Keybinds.Size = UDim2.new(0.899999976, 0, 0.5, 0)

			UIAspectRatioConstraint.Parent = Keybinds
			UIAspectRatioConstraint.AspectRatio = 5.000

			UICorner.CornerRadius = UDim.new(0, 4)
			UICorner.Parent = Keybinds

			UIPadding.Parent = Keybinds
			UIPadding.PaddingBottom = UDim.new(0, 1)
			UIPadding.PaddingLeft = UDim.new(0, 1)
			UIPadding.PaddingRight = UDim.new(0, 1)
			UIPadding.PaddingTop = UDim.new(0, 1)

			UIGradient.Rotation = -45
			UIGradient.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient.Parent = Keybinds

			Label.Name = "Label"
			Label.Parent = Keybinds
			Label.AnchorPoint = Vector2.new(0, 0.5)
			Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label.BackgroundTransparency = 1.000
			Label.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Label.BorderSizePixel = 0
			Label.Position = UDim2.new(0.032120917, 0, 0.50000006, 0)
			Label.Size = UDim2.new(0.624601603, 0, 0.508580387, 0)
			Label.Font = Enum.Font.GothamBold
			Label.Text = LabelStr or "Keybinds"
			Label.TextColor3 = Color3.fromRGB(255, 255, 255)
			Label.TextScaled = true
			Label.TextSize = 14.000
			Label.TextWrapped = true
			Label.TextXAlignment = Enum.TextXAlignment.Left

			UICorner_2.CornerRadius = UDim.new(0, 4)
			UICorner_2.Parent = Label

			UIGradient_2.Rotation = -45
			UIGradient_2.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.01)}
			UIGradient_2.Parent = Label

			Image.Name = "Image"
			Image.Parent = Keybinds
			Image.AnchorPoint = Vector2.new(0.5, 0.5)
			Image.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Image.BackgroundTransparency = 1.000
			Image.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Image.BorderSizePixel = 0
			Image.Position = UDim2.new(0.898999989, 0, 0.5, 0)
			Image.Size = UDim2.new(0.600000024, 0, 0.600000024, 0)
			Image.SizeConstraint = Enum.SizeConstraint.RelativeYY
			Image.ZIndex = 5
			Image.Image = "rbxassetid://7734010488"
			Image.ImageTransparency = 0.200
			Image.ScaleType = Enum.ScaleType.Fit

			UICorner_3.CornerRadius = UDim.new(0, 4)
			UICorner_3.Parent = Image

			UIGradient_3.Rotation = -45
			UIGradient_3.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.67), NumberSequenceKeypoint.new(1.00, 0.00)}
			UIGradient_3.Parent = Image

			Button_Clicked.Name = "Button_Clicked"
			Button_Clicked.Parent = Keybinds
			Button_Clicked.AnchorPoint = Vector2.new(0.5, 0.5)
			Button_Clicked.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Button_Clicked.BackgroundTransparency = 1.000
			Button_Clicked.BorderColor3 = Color3.fromRGB(0, 0, 0)
			Button_Clicked.BorderSizePixel = 0
			Button_Clicked.Position = UDim2.new(0.5, 0, 0.5, 0)
			Button_Clicked.Size = UDim2.new(0.899999976, 0, 0.899999976, 0)
			Button_Clicked.ZIndex = 5
			Button_Clicked.Font = Enum.Font.SourceSans
			Button_Clicked.TextColor3 = Color3.fromRGB(0, 0, 0)
			Button_Clicked.TextSize = 14.000
			Button_Clicked.TextTransparency = 1.000

			KEY.Name = "KEY"
			KEY.Parent = Keybinds
			KEY.AnchorPoint = Vector2.new(0, 0.5)
			KEY.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			KEY.BackgroundTransparency = 1.000
			KEY.BorderColor3 = Color3.fromRGB(0, 0, 0)
			KEY.BorderSizePixel = 0
			KEY.Position = UDim2.new(0.652679443, 0, 0.5, 0)
			KEY.Size = UDim2.new(0.800000012, 0, 0.800000012, 0)
			KEY.SizeConstraint = Enum.SizeConstraint.RelativeYY
			KEY.ZIndex = 7
			KEY.Font = Enum.Font.ArialBold
			KEY.Text = tostring(Info.Name) or "E"
			KEY.TextColor3 = Color3.fromRGB(147, 147, 147)
			KEY.TextScaled = true
			KEY.TextSize = 14.000
			KEY.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
			KEY.TextStrokeTransparency = 0.850
			KEY.TextWrapped = true

			UICorner_4.CornerRadius = UDim.new(0, 4)
			UICorner_4.Parent = KEY

			UIGradient_4.Rotation = -45
			UIGradient_4.Transparency = NumberSequence.new{NumberSequenceKeypoint.new(0.00, 0.07), NumberSequenceKeypoint.new(1.00, 0.01)}
			UIGradient_4.Parent = KEY

			UIStroke.Thickness = 1.800
			UIStroke.Transparency = 0.850
			UIStroke.Color = Color3.fromRGB(255, 255, 255)
			UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
			UIStroke.Parent = KEY

			Button_Clicked.MouseButton1Click:Connect(function()
				if IsWait then
					return
				end
				IsWait = true
				local KEYS = nil
				local FunctionRXB = UserInputService.InputBegan:Connect(function(Key)
					if Key.KeyCode ~= Enum.KeyCode.Unknown then
						if Key.KeyCode ~= Enum.KeyCode.Power then
							KEYS = Key.KeyCode
						end
					end
				end)
				Create_Ripple(Keybinds)
				repeat wait() KEY.Text = "-" until KEYS 
				IsWait = false
				if KEYS then
					if FunctionRXB then
						FunctionRXB:Disconnect()
					end
					KeyBind = KEYS
					KEY.Text = tostring(KeyBind.Name) or "E"
					callback(KeyBind)
				end
			end)

			function KeybindAssets:Set(KeyData:Enum.KeyCode)
				if KeyData and KeyData~=Enum.KeyCode.Unknown then
					KeyBind = KeyData
					KEY.Text = tostring(KeyBind.Name) or "E"
					callback(KeyBind)
				else
					print('this is a unknow key code - [1550]')
				end
			end
			
			return KeybindAssets;
		end

		return SectionAssets;
	end

	function WindowAssets:Destroy()
		Roblox_Studio_UI:Destroy()
		return
	end
	
	local Corrent = 0.1
	UserInputService.InputBegan:Connect(function(Input)
		if Input.KeyCode == RBS_UI.ToggleKey then
			if Togggleing then
				TweenService:Create(Frame,TweenInfo.new(Corrent),{Size = UDim2.new(0,0,0,0),Position = UDim2.new(0.5, 0,1.3, 0)}):Play()
				Togggleing = false
			else
				Togggleing = true
				TweenService:Create(Frame,TweenInfo.new(Corrent),{Size = UDim2.new(0.37, 0, 0.43, 0),Position = Toggle_LastPosition or UDim2.new(0.49999997, 0, 0.499320686, 0)}):Play()
			end
		end
	end)

	Toggle.MouseButton1Click:Connect(function()
		Create_Ripple(Toggle)
		if Togggleing then
			TweenService:Create(Frame,TweenInfo.new(Corrent),{Size = UDim2.new(0,0,0,0),Position = UDim2.new(0.5, 0,1.3, 0)}):Play()
			Togggleing = false
		else
			Togggleing = true
			TweenService:Create(Frame,TweenInfo.new(Corrent),{Size = UDim2.new(0.37, 0, 0.43, 0),Position = Toggle_LastPosition or UDim2.new(0.49999997, 0, 0.499320686, 0)}):Play()
		end
	end)

	local dragToggle = nil
	local dragSpeed = 0.05
	local dragStart = nil
	local startPos = nil

	local function updateInput(input)
		if not RBS_UI.CanMove then
			return
		end
		local delta = input.Position - dragStart
		local position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X,
			startPos.Y.Scale, startPos.Y.Offset + delta.Y)
		Toggle_LastPosition = position
		game:GetService('TweenService'):Create(Frame, TweenInfo.new(dragSpeed), {Position = position}):Play()
	end

	Frame.InputBegan:Connect(function(input)
		if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) then 
			dragToggle = true
			dragStart = input.Position
			startPos = Frame.Position
			input.Changed:Connect(function()
				if input.UserInputState == Enum.UserInputState.End then
					dragToggle = false
				end
			end)
		end
	end)

	UserInputService.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
			if dragToggle then
				updateInput(input)
			end
		end
	end)

	table.insert(_G.AssetsRBSUI,Roblox_Studio_UI)
	return WindowAssets,Roblox_Studio_UI;
end

return RBS_UI;
