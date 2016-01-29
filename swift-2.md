# Swift 2

## Favorite frameworks

*TBD*

## Code snippets

### Object declaration

Tags : `#oop`, `#object`, `#class`

```swift
class User {
    var name: String
	init(name: String) {
        self.name = name
		self.gender = Gender.Unspecified
    }
	func getIntroduction(other: User) : String {
		return "Hello, I'm \(self.name).";
	}
	
}
```

### Object subclassing

Tags : `#oop`, `#object`, `#class`, `#subclass`

```swift
class PoliteUser : User
{
	init(name: String) {
        super.init(name)
		self.name += "(Polite)"
    }
		
	override funcgetIntroduction(other: User) : String {
		return super.getIntroduction(other) + " Nice to meet you \(other.Name) !";
	}
}
```

### Object instanciation

Tags : `#oop`, `#object`, `#class`

```swift
let user = User(name: "John")
```