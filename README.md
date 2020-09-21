# gmod-messagepack
An edit of [lua-MessagePack](https://fperrad.frama.io/lua-MessagePack/) that works in Garry's Mod.
Using the library works almost exactly the same as the [original](https://fperrad.frama.io/lua-MessagePack/messagepack/#reference), except instead of requiring the library you create a localised copy of the object for your addon. This is so you can set addon specific configurations on the library without the worry of causing any interference.


## Example Usage
```lua
local msgPack = messagePack.new() --Create a copy of the messagepack object so we can use our own settings

local testData = {"one", 2, {3, 3.5}, false}
PrintTable(testData)

local packedData = msgPack.pack(testData) --Pack the test data
print(packedData)

PrintTable(msgPack.unpack(packedData)) --Unpack the test data, prints the same as the first PrintTable()
```
