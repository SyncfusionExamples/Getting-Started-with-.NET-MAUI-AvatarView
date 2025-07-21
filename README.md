# Getting Started with .NET MAUI AvatarView (SfAvatarView)

This section provides a quick overview for working with the SfAvatarView for .NET MAUI. Walk through the entire process of creating a real world of this control.

## Creating an application using the .NET MAUI Avatar View
 1. Create a new .NET MAUI application in Visual Studio.
 2. Syncfusion .NET MAUI components are available on [nuget.org](https://www.nuget.org/). To add SfAvatarView to your project, open the NuGet package manager in Visual Studio, search for Syncfusion.Maui.Core and then install it.

## Register the handler

To use this control inside an application, you must register the handler for Syncfusion® core.

```C#

using Microsoft.Extensions.Logging;
using Syncfusion.Maui.Core.Hosting;

namespace AvatarViewGettingStarted
{
    public static class MauiProgram
    {
        public static MauiApp CreateMauiApp()
        {
            var builder = MauiApp.CreateBuilder();
            builder
                .UseMauiApp<App>()
                .ConfigureSyncfusionCore()
                .ConfigureFonts(fonts =>
                {
                    fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
                    fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
                });

#if DEBUG
    		builder.Logging.AddDebug();
#endif

            return builder.Build();
        }
    }
}

```

## Add a basic Avatar View
1. Import the control namespace `Syncfusion.Maui.Core` in XAML or C# code.
2. Initialize the [SfAvatarView](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Core.SfAvatarView.html) control.

```xml
<ContentPage   
    . . .
    xmlns:sfavatar="clr-namespace:Syncfusion.Maui.Core;assembly=Syncfusion.Maui.Core">

    <syncfusion:SfAvatarView />
</ContentPage>
```



```C#
using Syncfusion.Maui.Core;
. . .

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        SfAvatarView avatarView = new SfAvatarView();
        this.Content = avatarView;
    }
}
```

## Adding an image in .NET MAUI Avatar View

```
    <ContentPage.Content>
        <Grid>
            <sfavatar:SfAvatarView ContentType="Custom"
                           ImageSource="alex.png"
                           VerticalOptions="Center"
                           HorizontalOptions="Center"   
                           HeightRequest="100"
                           CornerRadius="50"
                           WidthRequest="100" 
                           Stroke="Black"
                           StrokeThickness="2"/>
        </Grid>
    </ContentPage.Content>
```

Run the application to render the following output:

![Getting started with .NET MAUI Avatar View](maui-avatar-view.png)
