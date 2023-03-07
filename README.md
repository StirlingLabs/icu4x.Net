![icu4x.Net](https://raw.githubusercontent.com/StirlingLabs/icu4x.Net/main/icu4x.jpg)

# Cross-platform UTF
Cross-platform UTF text tools.

The intent here is to make the [ICU4x library](http://blog.unicode.org/2022/09/announcing-icu4x-10.html) -- a new Rust implementation of the International Components for Unicode -- available in the .Net ecosystem via NuPkg.

### Usage

We do not provider a wrapper for C# at this stage, this is simply building the upstream code with C API and packaging it for use.  Our specific use case is to use UTF8 in a consistently-sortable manner on all platforms, which we do in the [StirlingLabs.Utilities](https://github.com/StirlingLabs/Utilities.Net) library.

Native binaries for Windows, Linux & Mac (x64 & ARM in a Universal binary) are made available through NuGet as [3 separate packages](https://www.nuget.org/packages?q=StirlingLabs.icu4x) plus a CLDR data file with "full" locale set, built by CI in this repo.

In order for the UCLDR postcard data file to be propogated from library files into applications, you should add the 'PrivateAssets' tag with a 'None' value:

```xml
<PackageReference Include="StirlingLabs.icu4x.ucldr" Version="23.3.4" PrivateAssets="none" />
```

### Support

Development of this project is supported by [Stirling Labs](https://stirlinglabs.github.io).
