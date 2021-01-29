# 解决引用不同版本的DLL

~~~xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0" />
  </startup>

  <runtime>
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
      <!-- 解决引用不同版本的Newtonsoft.Json -->
      <!-- 有两种解决方法, 选择其一即可解决 选择其一即可解决 选择其一即可解决 -->
      
      <!-- 方法一：指定程序集的位置 -->
      <!-- [指定程序集的位置]官方教程 https://docs.microsoft.com/zh-cn/dotnet/framework/configure-apps/specify-assembly-location -->
      <!-- Step 1 指定程序集名称 与 publicKeyToken -->
      <!-- Step 2 为需要使用的版本指定路径 -->
      <!-- Step 3 指定路径DLL文件 -->
      <dependentAssembly>
        <assemblyIdentity name="Newtonsoft.Json" publicKeyToken="30ad4fe6b2a6aeed" />
        <codeBase version="4.0.0.0" href="DLL\Newtonsoft.Json\4_0\Newtonsoft.Json.dll" />
        <codeBase version="12.0.0.0" href="DLL\Newtonsoft.Json\12_0\Newtonsoft.Json.dll" />
      </dependentAssembly>


      <!-- 方法二：指定程序集绑定 -->
      <!-- [指定程序集绑定]官方教程 https://docs.microsoft.com/zh-cn/dotnet/framework/configure-apps/redirect-assembly-versions
      在配置文件中指定程序集绑定
      -->
      <!-- Step 1 指定程序集名称 与 publicKeyToken -->
      <!-- Step 2 将需要转换的版本或版本范围(oldVersion) 重新指定到 新的版本范围(newVersion) -->
      <dependentAssembly>
        <assemblyIdentity name="Newtonsoft.Json" publicKeyToken="30ad4fe6b2a6aeed" />
        <bindingRedirect oldVersion="1.0.0.0-11.0.0.0" newVersion="12.0.0.0" />
      </dependentAssembly>
    </assemblyBinding>

    <!-- 总结 -->
    <!-- 方法一 较为准确, 但麻烦 -->
    <!-- 缺点 需要管理或下载多个不同版本的dll文件 -->
    <!-- 优点 不同dll的代码具体逻辑可能导致结果不相同, 所以指定其需要的dll更为准确 -->

    <!-- 方法二 较为简单灵活, 但有机会执行结果不是预期 -->
    <!-- 优点 只需要一个版本的dll文件 -->
    <!-- 缺点 不同dll的代码具体逻辑可能导致结果不相同 -->
  </runtime>
</configuration>
~~~

