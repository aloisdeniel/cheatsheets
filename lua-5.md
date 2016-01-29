# Lua

## Code snippets

### Object declaration

Tags : `#oop`, `#object`, `#class`

```lua
local class = require("middleclass")
local User = class('User')

function User:initialize(name)
	self.name = name
	self.gender = Gender.UNSPECIFIED
end

function User:getIntroduction(other)
	return string.format("Hello, I'm %s.",self.name)
end
```

### Object subclassing

Tags : `#oop`, `#object`, `#class`, `#subclass`

```lua
local class = require("middleclass")
local Parent = User
local PoliteUser = class('PoliteUser',Parent)

function PoliteUser:initialize(name)
	User.initialize(self, name)
	self.name = self.name .. "(Polite)"
end

function PoliteUser:getIntroduction(other)
	return Parent.getIntroduction(self) .. string.format("Nice to meet you %s !",other.name)
end

```
### Object instanciation

Tags : `#oop`, `#object`, `#class`

```lua
var user = User:new("John");
var n = user.Name;
```