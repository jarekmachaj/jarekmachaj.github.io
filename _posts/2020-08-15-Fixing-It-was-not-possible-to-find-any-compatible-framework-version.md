---
layout: post
title: Fixing build error - It was not possible to find any compatible framework version
---

Full error:

```

It was not possible to find any compatible framework version
The framework 'Microsoft.NETCore.App', version '2.0.0' was not found.
  - The following frameworks were found:
      3.1.7 at [/usr/share/dotnet/shared/Microsoft.NETCore.App]

You can resolve the problem by installing the specified framework and/or SDK.

The specified framework can be found at:
  - https://aka.ms/dotnet-core-applaunch?framework=Microsoft.NETCore.App&framework_version=2.0.0&arch=x64&rid=debian.10-x64

```

Easiest way to fix it is to add `<GenerateRuntimeConfigurationFiles>True</GenerateRuntimeConfigurationFiles>`  to .csproj file:

```
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <OutputType>Library</OutputType>
    <GenerateRuntimeConfigurationFiles>True</GenerateRuntimeConfigurationFiles>
  </PropertyGroup>

...
...

```
