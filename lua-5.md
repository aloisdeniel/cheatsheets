# Lua

## Favorite frameworks

* [middleclass](https://github.com/kikito/middleclass) : *OOP* - Adds object orientation programming helpers
* [stateful](https://github.com/kikito/stateful.lua) : *States* - Adds states for objects
* [inspect](https://github.com/kikito/inspect.lua) : *Debugging* - Formating fo console
* [LÖVE](https://love2d.org/) : *2D Engine* - A simple 2D game engine
	* [EditGrid](https://github.com/bakpakin/Editgrid) : *Debugging grid*	 
	* [bump](https://github.com/kikito/bump.lua) : *Simple physics*
	* [anim8](https://github.com/kikito/anim8) : *Sprite animations*
	* [tween](https://github.com/kikito/tween.lua) : *Tweening functions*
	* [gamera](https://github.com/kikito/gamera/blob/master/gamera.luas) : *Camera*
	* [cargo](https://github.com/bjornbytes/cargo) : *Resource loader*

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