local repo = "https://github.com/theuxxs02/afsdupe.lua"
local function LoadScript(ScriptName)
	pcall(function()
		t = 0
		repeat
			local s, r = pcall(function()
				loadstring(game:HttpGet(repo .. ScriptName))()
			end)
			if not s then
				spawn(function()
					error(r)
				end)
			end
			t = t + 1
			wait(60)
		until getgenv().Executed or t >= 30
	end)
end
local Id = game.PlaceId
local GameId = game.GameId
local PlaceIds = {
        ["AFS"] = {6299805723, 9141645420}
}
elseif table.find(PlaceIds["AFS"], Id) then -- Afs
	LoadScript("afsdupe.lua")
end
