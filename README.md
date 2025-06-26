# Secret-Spawner
local function GiveSeeds()
    local remotes = {"PlantSeed", "BuySeed", "GetSeed"}
    for _, remoteName in pairs(remotes) do
        local remote = game:GetService("ReplicatedStorage"):FindFirstChild(remoteName)
        if remote then
            while true do -- WARNING: Infinite loop
                remote:FireServer("BasicSeed") -- Replace with actual seed name
                task.wait(0.5) -- Delay to avoid crashing
            end
        end
    end
    warn("No seed remote found!")
end
GiveSeeds() -- Run immediately
