# Xamarin.Forms Shell 控制返回按钮

在 ContentPage 中, 增加 Shell.BackButtonBehavior

```xaml
<ContentPage
    x:Class="App1.Views.ItemDetailPage"
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    Title="{Binding Title}">
    
    <Shell.BackButtonBehavior>
        <BackButtonBehavior Command="{Binding GoBackCommand}">
            <BackButtonBehavior.TextOverride>
                <OnPlatform x:TypeArguments="x:String">
                    <OnPlatform.Platforms>
                        <On
                            Platform="iOS"
                            Value="Go Back" />
                    </OnPlatform.Platforms>
                </OnPlatform>
            </BackButtonBehavior.TextOverride>
        </BackButtonBehavior>
    </Shell.BackButtonBehavior>

    <StackLayout>
        ...
    </StackLayout>
</ContentPage>
```


~~~C#
public partial class ItemDetailPage : ContentPage
{
    public ItemDetailPage()
    {
        InitializeComponent();
        BindingContext = new ItemDetailViewModel();
		
        // 注册事件
        Shell.Current.Navigating += Current_Navigating;
    }

    protected override bool OnBackButtonPressed()
    {
        Device.BeginInvokeOnMainThread(async () =>
                                       {
                                           await GoBack();
                                       });

        return true;
    }

    private async void Current_Navigating(object sender, ShellNavigatingEventArgs e)
    {
        if (e.CanCancel)
        {
            e.Cancel();
            await GoBack();
        }
    }

    private async Task GoBack()
    {
        bool r = await Acr.UserDialogs.UserDialogs.Instance.ConfirmAsync(new Acr.UserDialogs.ConfirmConfig()
                                                                         {
                                                                             Title = "提示",
                                                                             Message = "确认退出?",
                                                                             OkText = "确认",
                                                                             CancelText = "取消"
                                                                         });

        if (r)
        {
            Shell.Current.Navigating -= Current_Navigating;
            await Shell.Current.GoToAsync("..", true);
        }
    }
}
~~~



待测试在 Xamarin.Forms 4.8 中能否控制软返回键 和 硬件返回键

编写附加属性, 在XAML中进行相关事件的注册