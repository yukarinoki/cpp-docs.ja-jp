---
title: ファイルをフィルターします。
ms.date: 09/25/2019
description: Visual Studio C++ プロジェクトでフィルター ファイルを使用して、ソリューション エクスプローラーでファイルのカスタム論理フォルダーを定義する
helpviewer_keywords:
- vcxproj.filters
- filters file [C++]
ms.openlocfilehash: 57735246b543680243994b99b8c05c9ad1211f38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335936"
---
# <a name="vcxprojfilters-files"></a>ファイルをフィルターします。

*フィルター*ファイル\*(.vcxproj.filters) は、ルート プロジェクト フォルダーにある MSBuild 形式の XML ファイルです。 **ソリューション エクスプローラ**で、どのファイルの種類に移動するかを指定します。 次の図では *、.cpp*ファイルは **[ソース ファイル]** ノードの下にあります。 *.h*ファイルは **[ヘッダー ファイル]** ノードの下にあり *、.ico*ファイルと *.rc*ファイルは **[リソース ファイル] の下にあります**。 この配置は、フィルター ファイルによって制御されます。

![ソリューション エクスプローラーの論理フォルダー](media/solution-explorer-filters.png)

## <a name="creating-a-custom-filters-file"></a>カスタムフィルターファイルの作成

このファイルは自動的に作成されます。 デスクトップ アプリケーションの場合、定義済みの論理フォルダ (フィルタ) は、**ソース ファイル**、ヘッダー**ファイル**、**およびリソース ファイルです**。 UWP などの他の種類のプロジェクトには、既定のフォルダーのセットが異なる場合があります。 Visual Studio では、既知のファイルの種類が各フォルダーに自動的に割り当てられます。 カスタムファイルの種類を含むカスタム名またはフィルタを使用してフィルタを作成する場合は、プロジェクトのルート フォルダまたは既存のフィルタの下に独自のフィルタ ファイルを作成できます。 (**参照**と**外部依存関係**は、フィルタ処理に参加しない特殊なフォルダです。

## <a name="example"></a>例

次の例は、前の例のフィルター ファイルを示しています。 これはフラットな階層を持っています。つまり、ネストされた論理フォルダはありません。 `UniqueIdentifier` ノードは省略可能です。 これにより、Visual Studio オートメーション インターフェイスがフィルターを検索できるようになります。 `Extensions`また、オプションです。 新しいファイルをプロジェクトに追加すると、一致するファイル拡張子を持つ最上位のフィルターに追加されます。 特定のフィルタにファイルを追加するには、フィルタを右クリックし、[**新しいアイテムの追加**] を選択します。

ノード`ItemGroup`を含む`ClInclude`は、プロジェクトが最初に起動されたときに作成されます。 独自の vcxproj ファイルを生成する場合は、すべてのプロジェクト項目にも、フィルター ファイルにエントリがあることを確認します。 ノードの値`ClInclude`は、ファイル拡張子に基づく既定のフィルタリングを上書きします。 Visual Studio を使用してプロジェクトに新しい項目を追加すると、IDE によってフィルター ファイルに個別のファイル エントリが追加されます。 ファイルの拡張子を変更しても、フィルタは自動的に再割り当てされません。

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup>
    <Filter Include="Source Files">
      <UniqueIdentifier>{4FC737F1-C7A5-4376-A066-2A32D752A2FF}</UniqueIdentifier>
      <Extensions>cpp;c;cc;cxx;def;odl;idl;hpj;bat;asm;asmx</Extensions>
    </Filter>
    <Filter Include="Header Files">
      <UniqueIdentifier>{93995380-89BD-4b04-88EB-625FBE52EBFB}</UniqueIdentifier>
      <Extensions>h;hh;hpp;hxx;hm;inl;inc;ipp;xsd</Extensions>
    </Filter>
    <Filter Include="Resource Files">
      <UniqueIdentifier>{67DA6AB6-F800-4c08-8B7A-83BB121AAD01}</UniqueIdentifier>
      <Extensions>rc;ico;cur;bmp;dlg;rc2;rct;bin;rgs;gif;jpg;jpeg;jpe;resx;tiff;tif;png;wav;mfcribbon-ms</Extensions>
    </Filter>
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="MFCApplication1.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="MFCApplication1Dlg.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="stdafx.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="targetver.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="Resource.h">
      <Filter>Header Files</Filter>
    </ClInclude>
  </ItemGroup>
  <ItemGroup>
    <ClCompile Include="MFCApplication1.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
    <ClCompile Include="MFCApplication1Dlg.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
    <ClCompile Include="stdafx.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
  </ItemGroup>
  <ItemGroup>
    <ResourceCompile Include="MFCApplication1.rc">
      <Filter>Resource Files</Filter>
    </ResourceCompile>
  </ItemGroup>
  <ItemGroup>
    <None Include="res\MFCApplication1.rc2">
      <Filter>Resource Files</Filter>
    </None>
  </ItemGroup>
  <ItemGroup>
    <Image Include="res\MFCApplication1.ico">
      <Filter>Resource Files</Filter>
    </Image>
  </ItemGroup>
</Project>
```

入れ子になった論理フォルダを作成するには、次に`ItemGroup`示すように、すべてのノードをフィルタで宣言します。 各子ノードは、最上位の親への完全論理パスを宣言する必要があります。 次の例では、後の`ParentFilter`ノードで参照されるため、空を宣言する必要があります。

```xml
  <ItemGroup>
    <Filter Include="ParentFilter">
    </Filter>
    <Filter Include="ParentFilter\Source Files"> <!-- Full path to topmost parent.-->  
      <UniqueIdentifier>{4FC737F1-C7A5-4376-A066-2A32D752A2FF}</UniqueIdentifier> <!--  Optional-->
      <Extensions>cpp;c;cc;cxx;def;odl;idl;hpj;bat;asm;asmx</Extensions> <!-- Optional -->
    </Filter>
    <Filter Include="Header Files">
      <UniqueIdentifier>{93995380-89BD-4b04-88EB-625FBE52EBFB}</UniqueIdentifier>
      <Extensions>h;hh;hpp;hxx;hm;inl;inc;ipp;xsd</Extensions>
    </Filter>
  </ItemGroup>
```
