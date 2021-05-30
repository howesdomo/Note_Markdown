# Xamarin.Forms全局设置指定字体



## 一、在 Xamarin.Android 项目中进行以下设置

### 1.字体文件保存到 Assets 目录内

本次测试将方正仿宋简体字符文件 ( FZFSJW.ttf ) 存放到 Assets/Fonts/FZFSJW.ttf

属性(Properties)的Build Action设置为 AndroidAsset



### 2.styles.xml 设置 typeface 为 monospace 

在 Resources/values/styles.xml 的主程序主题中设置 android:typeface 值为 monospace

~~~xml
<style name="MainTheme" parent="MainTheme.Base">
    ...
	<!-- 安卓typeface设置为monospace -->
	<item name="android:typeface">monospace</item>
    ...
</style>      
~~~



### 3. 在 new App() 之前执行 setDefaultFont

~~~c#
// Xamarin.Android
public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
{
    protected override void OnCreate(Bundle savedInstanceState)
    {
        ...

        // 设置全局字体
		setDefaultFont("fonts/FZFSJW.ttf");

        ... 
        // 在 new App() 前进行全局字体的设置
        Xamarin.Essentials.Platform.Init(this, savedInstanceState);
        global::Xamarin.Forms.Forms.Init(this, savedInstanceState);
        LoadApplication(new App());            
    }
}

/// <summary>
/// <para>设置默认字体</para>
/// <para>缺点: 未能对 DisplayAlert 的内容信息有效</para>
/// </summary>
/// <param name="fontNameInAssets">在 Assets 目录内的字体文件名, 如若在子目录 Fonts 中, 传入 Fonts/Xxx.ttf</param>
void setDefaultFont(string fontNameInAssets)
{
    try
    {
        // 从 Assets 中加载字体文件
        var customFont = Android.Graphics.Typeface.CreateFromAsset(Application.Context.Assets, fontNameInAssets);

        Java.Lang.Class typeof_Typeface = Java.Lang.Class.FromType(typeof(Android.Graphics.Typeface));

        // string s_Typeface_FieldName = "MONOSPACE"; // android 10 测试部分内容成功替换
        Java.Lang.Reflect.Field field = typeof_Typeface.GetDeclaredField("MONOSPACE"); // MONO Space 解释:等宽字体
        field.Accessible = true;
        field.Set(null, customFont);
    }
    catch (Exception e)
    {
        System.Diagnostics.Debug.WriteLine(e.Message);
        System.Diagnostics.Debugger.Break();
    }
}

~~~



## 二、在Xamarin.Forms项目中进行以下设置

### 1. 字体文件

可以在任意位置保存字体文件, 本次测试将方正仿宋简体字符文件 ( FZFSJW.ttf ) 存放到Fonts文件夹内

属性(Properties)的Build Action设置为 (嵌入的资源) Embedded resource



### 2.声明嵌入字体资源的导入

在 AssemblyInfo.cs 文件中导入字体, 并昵称其为 __方正仿宋_简__

~~~c#
using Xamarin.Forms;
using Xamarin.Forms.Xaml;

[assembly: XamlCompilation(XamlCompilationOptions.Compile)]

// 导入字体
[assembly: ExportFont("Font Awesome 5 Pro-Regular-400.otf", Alias = "FontAwesome")]
[assembly: ExportFont("Font Awesome 5 Brands-Regular-400.otf", Alias = "FontAwesome_Brands")] // 商标

// !!!! 本次导入的方正仿宋字体
[assembly: ExportFont("FZFSJW.TTF", Alias = "方正仿宋_简")]
~~~



### 3.全局设置资源

在 App.xaml 中设置程序全局Style, 为常用的控件设置默认的 FontFamily 样式为第二点设置的昵称  __方正仿宋_简__

~~~xaml
<?xml version="1.0" encoding="utf-8" ?>
<Application
    x:Class="Client.App"
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:d="http://xamarin.com/schemas/2014/forms/design"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    mc:Ignorable="d">

    <Application.Resources>
        <ResourceDictionary>
			... 省略上
            
            <Style TargetType="Label">
                <Setter Property="FontFamily" Value="方正仿宋_简" />
            </Style>
            <Style TargetType="Entry">
                <Setter Property="FontFamily" Value="方正仿宋_简" />
            </Style>
            <Style TargetType="Editor">
                <Setter Property="FontFamily" Value="方正仿宋_简" />
            </Style>
            
            ... 省略下
        </ResourceDictionary>
    </Application.Resources>
</Application>
~~~



