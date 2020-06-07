+++
title = "C#"
date = 2020-06-06T19:56:06+02:00
draft = true
+++

## Dependency Injection (DI)

Dependency injection is a software development technique where one object supplies the dependecies of another object. A dependecy is an object that can be used as a service. Usually the dependecy is injected through the contructor of the object. These technique helps to decouple the code base and make it loosely connected in case services need to be replaced. The opposite of dependecy injection would be to *new* up the service.

### Useful Articles

* [Dependency Inversion Principle](https://deviq.com/dependency-inversion-principle/)
* [New is Glue](https://ardalis.com/new-is-glue)
* [Dependency Injection (Wikipedia)](https://en.wikipedia.org/wiki/Dependency_injection)
* [DI into controllers in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/mvc/controllers/dependency-injection?view=aspnetcore-2.2)


### Dependency Injection in ASP.NET Core

ASP.NET Core framework has built in functionalities for dependency injection.

In `startup.cs`, `ConfigureServices` method, add service to `services`.

There are two common ways to add a service.

* `AddSingleton<>();`
* `AddTransient<>();`

`AddSingleton` means there is always one instance of a service and when that service is used it is that instance. `AddTransient` means when the service is used it creates and instance, does the action and is destroyed. After wards if that service is needed again, a new instance of the service is created. This can be checked by checking the `GetHashCode` of the services and seeing if it is the same (Singleton) or different (transient) everytime the service is invoked.

#### LinqPad Example

```C#
void Main()
{
	
	// ServiceCollection
	var sc = new ServiceCollection();
	sc.AddSingleton<IFoo, Foo>();
	sc.AddTransient<IDateTime, SystemDateTime>();
	var sp = sc.BuildServiceProvider();
	
	// Framework does this automatically
	var foo = sp.GetRequiredService<IFoo>();
	
	foo.Dump();
	foo.GetHashCode().Dump();
	// Same instance, same hashcode


	foo = sp.GetRequiredService<IFoo>();

	foo.Dump();
	
	foo.Hello();
	
	foo.GetHashCode().Dump();
	
	var time = sp.GetRequiredService<IDateTime>();
	Console.WriteLine(time.Now);
	time.Dump();
	
}

// Define other methods and classes here
public interface IFoo{
	
	void Hello();
	
}
public class Foo : IFoo
{
	public void Hello()
	{
		Console.WriteLine("Hello");
	}
}

public interface IDateTime{
	
	DateTime Now { get; }
}

public class SystemDateTime : IDateTime
{
	public DateTime Now
	{
		get { return DateTime.Now; }
	}
}

```

![Inverted Dependency Graph](https://docs.microsoft.com/en-us/dotnet/standard/modern-web-apps-azure-architecture/media/image4-2.png)


## Keywords in C#

### The `static` keyword

[“relating to the type itself, rather than an instance of the type”](https://theburningmonk.com/2010/07/static-vs-non-static-method-in-csharp/)


## LinqPad

Amazing tool for running C# snippets.

### Linq Language

Two types of syntax
* Query
* Method (Better)

`.Dump()` -> method to dump results on the screen

### Sources

[Linq Query Operators](http://www.tutorialsteacher.com/linq/linq-standard-query-operators)

[Linq Tutorial](http://www.tutorialsteacher.com/linq/linq-tutorials)



## ASP.NET

[ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/?view=aspnetcore-2.2)