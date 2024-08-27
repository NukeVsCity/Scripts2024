if not game:IsLoaded() then
game.Loaded:Wait()
end
local petNet = {}
local network = require(game:GetService("ReplicatedStorage"):WaitForChild("Framework",10):WaitForChild("Library",10));
assert(network,"now what the hell")
function petNet:getPath(...)--print(petNet:getPath("Variables","LoadingWorld"))
    local path = {...}
    local oldPath = network
    for i,v in ipairs(path) do
        oldPath = rawget(oldPath,v)--this is the path 1 table down ok dont judge me
    end
    return oldPath
end
function petNet:waitForLoad()--this code is fucking abhorrent
    local currentlyLoading
        repeat wait() --dont judge me this is how preston's HasLoaded function works internally, I just know directly calling functions is a bad idea
            currentlyLoading = ((petNet:getPath("Variables","LoadingWorld")==false) and workspace:FindFirstChild("__MAP") and workspace["__MAP"]:FindFirstChild("PlayerSpawns")) and true or false
        until currentlyLoading
    return currentlyLoading
end
return petNet
