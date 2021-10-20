# Blazor Tabs Component
This is a **Tabs component** for [Blazor Web Assembly](https://www.puresourcecode.com/tag/blazor-webassembly/) and [Blazor Server](https://www.puresourcecode.com/tag/blazor-server/). The full explanation of the source code is on [PureSourceCode.com](https://www.puresourcecode.com/dotnet/blazor/segment-control-for-blazor/). Please leave your comment or question and use my [forum](https://www.puresourcecode.com/forum/). Please subscribe my [YouTube channel](https://www.youtube.com/channel/UC2jeteqpm3sUDqQpKGqpCLg?sub_confirmation=1).

## Anatomy of Tabs
![image](https://user-images.githubusercontent.com/9497415/137930261-13e42ca2-e2d2-49f9-a86a-c2bcf21972ba.png)

### Tabs container attributes
When you add the `Tabs` in your page, the first thing is the main container for `tabs` is `Tabs`. Tabs has 4 attributes:

| Attribute                   | Description                                                |
|-----------------------------|------------------------------------------------------------|
| TextFilling1                | This text is displayed on the left handside of the tabs    |
| TextFilling2                | This text is displayed on the right handside of the tabs   |

### Tabs container events
Also, `Tabs` has the following events that you can use.

| Event                       | Description                                                |
|-----------------------------|------------------------------------------------------------|
| OnTabChanged                | When the use click on a new tab, this event is raised. So, you can attach a function to read the new tab object |

### Tab attributes
| Attribute                   | Description                                                |
|-----------------------------|------------------------------------------------------------|
| Text                        | The text to display in the tab                             |
| Value                       | The value associate to a tab (useful if you have to filter your data) |
| Enabled                     | Is this tab enabled? If not the user can't click on it. By default is `True` |

## How to use
First, add the NuGet package in your project. The name of the package is [PSC.Blazor.Components.Tabs](https://www.nuget.org/packages/PSC.Blazor.Components.Tabs/) and the only dependency it has is [Microsoft.AspNetCore.Components.Web (>= 5.0.10)](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web/).

After that, in your wwwroot\index.html or in the hosts file, you have to add a theme (CSS) for your segment control. Obviously, you can create your own theme. So, use this code:

```
<link href="_content/PSC.Blazor.Components.Tabs/themes/{theme-name}.css" rel="stylesheet" />
```

### Example

```
@page "/test"

<Tabs TextFilling1="@text1" TextFilling2="@text2" OnTabChanged="OnTabChanged">
    <Tab Text="Tab 1" Value="Tab1">
        <h2>Content Tab 1</h2>
        <p>
            This is the content for the Tab 1. It is enabled.
        </p>
    </Tab>
    <Tab Text="Tab 2" Value="Tab2">
        <h2>Content Tab 2</h2>
        <p>
            This is the content for the Tab 2. It is enabled.
        </p>
    </Tab>
    <Tab Text="Tab 3" Value="Tab3">
        <h2>Content Tab 3</h2>
        <p>
            This is the content for the Tab 3. It is enabled.
        </p>
    </Tab>
    <Tab Text="Tab 4" Enabled="@IsEnabled" Value="Tab4">
        <h2>Content Tab 4</h2>
        <p>
            This is the content for the Tab 4. It is disabled if <i>IsEnabled = false</i>
        </p>
    </Tab>
</Tabs>

@code {
    public string text1 = "Text on the left";
    public string text2 = "Text on the right";

    public bool IsEnabled = false;

    public async Task OnTabChanged(Tab tab)
    {
        text1 = $"Tab value: {tab.Value}";
        text2 = $"Tab text: {tab.Text}";
    }
}
```

## Themes

### Blue
![tabs-blue](https://user-images.githubusercontent.com/9497415/137933873-1ea476b7-0adf-4ecd-813d-275c4cd56148.gif)

### Green
![tabs-green](https://user-images.githubusercontent.com/9497415/137933875-a1084d13-0bde-4d6a-ab8e-764feb21612b.gif)

### Red
![tabs-red](https://user-images.githubusercontent.com/9497415/137933878-6e3b8589-56a8-42b7-baa8-d392a8135b80.gif)

### Light colors
![tabs-lightcolors](https://user-images.githubusercontent.com/9497415/137934232-8412ede3-b125-4a43-b4f1-3d9d26e578c8.gif)

