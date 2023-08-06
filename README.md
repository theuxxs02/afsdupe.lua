local Material = loadstring(game:HttpGet("https://raw.githubusercontent.com/Kinlei/MaterialLua/master/Module.lua"))()

local X = Material.Load({
    Title = "AFS - Theus-Hub",
    Style = 3,
    SizeX = 500,
    SizeY = 350,
    Theme = "Dark",
    ColorOverrides = {
        MainFrame = Color3.fromRGB(35,35,35)
    }
})

local Y = X.New({
    Title = "Main"
})

local A = Y.Button({
    Text = "You have not selected any Dataloss Type",
    Callback = function()
        if Type == "Start Dataloss" then
                   local args = {
                            [1] = "\0" .. string.rep("B", 4200000)game.ReplicatedStorage.Remote.SetTutorialDone:FireServer(unpack(args))
                            },
                        [2] = "AFS_Is_Dogshit",
                        [3] = 3
                    }

                    game:GetService("ReplicatedStorage").Remote.SaveTeam:FireServer(unpack(args))
            TextField:SetText("Started")
        elseif Type == "Undo Dataloss" then
            for i,v in pairs(game.Players.LocalPlayer.PlayerGui.MainGui.Pets.TeamsList.Main.Scroll:GetDescendants()) do
                if v.Name == "TeamName" and v.Text == "AFS_Is_Dogshit" then
                    local args = {
                        [1] = v.Parent.LayoutOrder
                    }

                    game:GetService("ReplicatedStorage").Remote.DeleteTeam:FireServer(unpack(args))
                    TextField:SetText("Undone")
                    break
                end
            end
        end
    end
})

local D = Y.Dropdown({
    Text = "Dataloss Type",
    Callback = function(Value)
        getgenv().Type = Value
    end,
    Options = {
        "Start Dataloss",
        "Undo Dataloss"
    }
})

local AE = Y.Button({
    Text = "https://discord.gg/VzfJJw2VSw)",
    Callback = function()
        print("https://discord.gg/VzfJJw2VSw")
    end
})

local AE2 = Y.Button({
    Text = "Copy Discord Invite",
    Callback = function()
        setclipboard("https://discord.gg/VzfJJw2VSw")
    end
})

getgenv().TextField = Y.TextField({
    Text = "Status",
    Type = "Default"
})

while task.wait() do
    if Type then
        A:SetText(Type)
    end
end
