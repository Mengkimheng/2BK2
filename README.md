local HENG = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()


local MainWindow = HENG:CreateWindow({
	Name = "2BK2_RUN",
	LoadingTitle = "welcome TO 2BK2",
	LoadingSubtitle = "BK",
	ConfigurationSaving = {
	   Enabled = true,
	   FolderName = nil, -- Create a custom folder for your hub/game
	   FileName = "BK Hub"
	},
	Discord = {
	   Enabled = false,
	   Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD.
	   RememberJoins = true -- Set this to false to make them join the discord every time they load it up
	},
	KeySystem = false, -- Set this to true to use our key system
	KeySettings = {
	   Title = "BK Hub",
	   Subtitle = "Key System",
	   Note = "Key: BK",
	   FileName = "SiriusKey",
	   SaveKey = true,
	   GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
	   Key = "BK"
	}
 })


 local MainTab = MainWindow:CreateTab("MainRUN", "home") -- Title, Image



 local Toggle = MainTab:CreateToggle({
	Name = "SUPER JUMP",
	CurrentValue = false,
	Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
	Callback = function(InfiniteJumpEnabled)
        local InfiniteJumpEnabled = true
        game:GetService("UserInputService").JumpRequest:connect(function()
            if InfiniteJumpEnabled then
                game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
            end
        end)
	end,
 })


 local Slider = MainTab:CreateSlider({
	Name = "SUPER JUMP",
	Range = {50, 500},
	Increment = 1,
	Suffix = "JumpPower",
	CurrentValue = 1,
	Flag = "Slider8", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
	Callback = function(v)
		game.Players.LocalPlayer.Character.Humanoid.JumpPower = v
	end,
 })
 
 local Slider = MainTab:CreateSlider({
    Name = "RUN SPEED",
    Range = {1, 100},
    Increment = 1,
    Suffix = "Speed",
    CurrentValue = 1,
    Flag = "Slider9", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
     game.Players.LocalPlayer.Character:SetAttribute("SpeedMultiplier", Value)
    end,
 })

 local Slider = MainTab:CreateSlider({
    Name = "SUPER DASH ",
    Range = {50, 500},
    Increment = 1,
    Suffix = "PowerDash",
    CurrentValue = 1,
    Flag = "Slider5", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
     game.Players.LocalPlayer.Character:SetAttribute("DashLength", Value)
    end,
 })
