# Lua

## Favorite frameworks

* [middleclass](https://github.com/kikito/middleclass) : `#oop`
* [stateful](https://github.com/kikito/stateful.lua) : `#oop`, `#state`
* [inspect](https://github.com/kikito/inspect.lua) : `#debug`,`#format`
* [LÖVE](https://love2d.org/) : `#2d`, `#game`
	* [EditGrid](https://github.com/bakpakin/Editgrid) : `#2d`, `#debug`	 
	* [bump](https://github.com/kikito/bump.lua) : `#2d`, `#physics`
	* [anim8](https://github.com/kikito/anim8) : `#2d`, `#sprite`, `#animations`
	* [tween](https://github.com/kikito/tween.lua) : `#tweening`, `#animations`
	* [gamera](https://github.com/kikito/gamera/blob/master/gamera.luas) : `#2d`, `#camera`
	* [cargo](https://github.com/bjornbytes/cargo) : `#resources`

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