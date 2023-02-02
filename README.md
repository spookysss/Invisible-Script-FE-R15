# Invisible-Script-FE-R15

simple script that i made, works in all games 🙂

```lua
--[[
READ THIS BEFORE USING THE SCRIPT

Universal Invisible For R15 - developed by ss.spooky.ss#0003

Go to a place that no one can find you (Example: high moutains, hidden places)

You can edit the variables
]]

-- Variables to edit

local destroy_almost_all_body = true
local remove_accessory = true

-- Script

local function InvisFunctionR15() -- invis function
	
	local function invisible()
		for i, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do -- destroy lowertorso motor6d
			if v.Name == "LowerTorso" then
				for i, vv in pairs(v:GetChildren()) do
					if vv:IsA("Motor6D") then
						vv:Destroy()
					end
				end
			end
		end
	end
	
	local function destroy_all()
		for i, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do -- destroy other motor6d
			if v.Name ~= "HumanoidRootPart" and v:IsA("MeshPart") then	
				for i, vv in v:GetChildren() do
					if vv:IsA("Motor6D") and v.Name ~= "Head" then
						vv:Destroy()
					end
				end

				if v.Name == "LowerTorso" then
					v:Destroy()
				end
			end
		end
	end
	
	local function remove_acessory()
		for i, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do -- destroy accesories
			if v:IsA("Accessory") then
				v:Destroy()
			end
		end
	end
	
	invisible()
	
	task.wait(1)
	
	if destroy_almost_all_body then
		destroy_all()
	end
	
	if remove_accessory then
		remove_accessory()
	end
end

InvisFunctionR15()
```
