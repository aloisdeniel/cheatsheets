# C#6

## Code snippets

### Object declaration

Tags : `#oop`, `#object`, `#class`

```csharp
public class User
{
	public User(string name)
	{
		this.Name = name;
		this.Gender = Gender.Unspecified;
	}
	
	public string Name { get; set;}
		
	public Gender Gender { get; set;}
	
	public virtual string GetIntroduction(User other)
	{
		return $"Hello, I'm {this.Name}.";
	}
}
```

### Object subclassing

Tags : `#oop`, `#object`, `#class`, `#subclass`

```csharp
public class PoliteUser : User
{
	public User(string name) : base(name)
	{
    this.Name += "(Polite)";
	}
		
	public override string GetIntroduction(User other)
	{
		return base.GetIntroduction(other) + $" Nice to meet you {other.Name} !";
	}
}
```
### Object instanciation

Tags : `#oop`, `#object`, `#class`

```csharp
var user = new User("John");
var n = user.Name;
```