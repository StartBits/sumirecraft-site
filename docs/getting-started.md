# Get started

## Packages

| Package | Description |
| --- | --- |
| `SumireCraft.Maui.Controls` | The widgets. This is the package you normally want. |
| `SumireCraft.Maui.Core` | Exception reporting and the safety net, the busy gate, badge counting and lifetime helpers. Useful on its own, without any of the widgets. |
| `SumireCraft.Core` | `DateTimeInput`, and nothing that depends on a UI framework: plain `net10.0`, for a view model's or a server's project as well. Controls brings it in. |

## Install

```
dotnet add package SumireCraft.Maui.Controls
```

If you only want the common building blocks:

```
dotnet add package SumireCraft.Maui.Core
```

## Initialize

Initialize in `MauiProgram.cs`.

```csharp
using SumireCraft.Maui.Controls;

public static MauiApp CreateMauiApp()
{
    var builder = MauiApp.CreateBuilder();
    builder
        .UseMauiApp<App>()
        .UseSumireCraft();

    return builder.Build();
}
```

`UseSumireCraft()` calls `UseSumireCraftCore()` internally, so there is no need to call both.
If you reference only `SumireCraft.Maui.Core`, use `UseSumireCraftCore()`.

In XAML, one `xmlns` reaches every widget:

```xml
xmlns:smr="https://github.com/startbits/SumireCraft.Maui"
```
