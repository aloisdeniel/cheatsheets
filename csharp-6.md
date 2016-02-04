# C#6

## Favorite frameworks

* [MvvmLight](http://www.mvvmlight.net/doc) : `#mvvm`
* [Json.NET](http://www.newtonsoft.com/json) : `#parser`, `#json`
* [Xamarin](https://xamarin.com/) : `#crossplatform`, `#ios`, `#android`

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

### Storage (WinRT)

Tags : `#storage`, `#file`, `#folder`, `#winrt`

```csharp
-- Package folders
var installationFolder = Package.Current.InstalledLocation;

-- Local folders
var localFolder = Windows.Storage.ApplicationData.Current.LocalFolder;

-- Libraries
var picturesFolder = Windows.Storage.KnownFolders.PicturesLibrary;

-- Download folder
var f = await Windows.Storage.DownloadsFolder.CreateFileAsync("File", CreationCollisionOption.FailIfExists)

-- Embedded file
var assembly = this.GetType().GetTypeInfo().Assembly;
var stream = assembly.GetManifestResourceStream("Namespace.Sub.File.txt");

```

### Read & write text in files (WinRT)

Tags : `#storage`, `#file`, `#text`, `#folder`, `#write`, `#read`, `#winrt`

```csharp
var text = await Windows.Storage.FileIO.ReadTextAsync(storageFile); 
await Windows.Storage.FileIO.WriteTextAsync(storageFile,text); 

```

### Launcher (WinRT)

Tags : `#launch`, `#uri`, `#file`, `#scheme`, `#protocol`, `#winrt`

```csharp
succeed = await Windows.System.Launcher.LaunchFileAsync(storageFile);
succeed = await Windows.System.Launcher.LaunchUriAsync(uri);
```