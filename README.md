---
author: Justin Chase
author_email: justin@justinwritescode.com
title: Metapackage SDK
modified: 2023-01-10-12:14:11
created: 2023-01-10-12:14:09
license: MIT
type: readme
keywords: metapackage, sdk, msbuild, dotnet
---

# Metapackage SDK

This package simplifies (and encapsulates) the process of creating a metapackage.

## Usage

Simply add a reference to the `MetapackageSdk` to your project file along with all of your references to other projects and packages.

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <Sdk Name="MetapackageSdk" />
    <ItemGroup Label="Project References">
        <ProjectReference Include="Project.One.csproj" />
        <ProjectReference Include="Project.Two.csproj" />
        <ProjectReference Include="Project.Three.csproj" />
    </ItemGroup>
    <ItemGroup Label="Package References">
        <PackageReference Include="MyCoolPackage" />
        <PackageReference Include="MyKickassPackage" />
        <PackageReference Include="MyReallyCrummyPackageButImStillGonnaReleaseIt" />
    </ItemGroup>
</Project>

Then, run `dotnet pack` and you'll get a metapackage with all of your dependencies.
