---
title: .vcxproj ファイルとワイルドカード
description: C++ ネイティブ MSBuild プロジェクトシステム .vcxproj ファイルがワイルドカードを処理する方法。
ms.date: 09/30/2020
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
ms.openlocfilehash: 23d36a63f328e14cca59d1d57838173b4dcb0954
ms.sourcegitcommit: f7fbdc39d73e1fb3793c396fccf7a1602af7248b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "91663096"
---
# <a name="vcxproj-files-and-wildcards"></a>`.vcxproj` ファイルとワイルドカード

Visual Studio IDE は、ファイル内のプロジェクト項目内の特定の構成要素をサポートしていません *`.vcxproj`* 。 サポートされていない構造体には、ワイルドカード、セミコロンで区切られたリスト、または複数のファイルに展開される MSBuild マクロが含まれます。 `.vcxproj`C++ ビルドのプロジェクトシステムは、MSBuild よりも制限が厳しいです。 各プロジェクト項目には、独自の MSBuild 項目が必要です。 ファイル形式の詳細につい `.vcxproj` ては、「」 [ `.vcxproj` および「 `.props` ファイル構造](vcxproj-file-structure.md)」を参照してください。

これらのコンストラクトの例は、IDE ではサポートされていません。

```xml
<ItemGroup>
  <None Include="*.txt">
  <ClCompile Include="a.cpp;b.cpp"/>
  <ClCompile Include="@(SomeItems)" />
</ItemGroup>
```

これらの `.vcxproj` コンストラクトを含むプロジェクトファイルが IDE に読み込まれた場合、プロジェクトは最初に機能しているように見えます。 ただし、プロジェクトが Visual Studio によって変更され、ディスクに保存されると、問題が発生する可能性があります。 ランダムなクラッシュや未定義の動作が発生する可能性があります。

Visual Studio 2019 バージョン16.7 では、Visual Studio によってプロジェクトファイルが読み込まれると、 `.vcxproj` プロジェクト項目でサポートされていないエントリが自動的に検出されます。 ソリューションの読み込み中に、[出力] ウィンドウに警告が表示されます。

Visual Studio 2019 バージョン16.7 では、読み取り専用のプロジェクトサポートも追加されます。 読み取り専用のサポートでは、ide で編集可能なプロジェクトの追加の制限を持たない手動で作成されたプロジェクトを IDE で使用できます。

サポートされて `.vcxproj` いない1つ以上のコンストラクトを使用するファイルがある場合は、次のいずれかのオプションを使用して、IDE で警告なしに読み込むことができます。

- すべての項目を明示的に一覧表示する
- プロジェクトを読み取り専用としてマークする
- ワイルドカード項目をターゲットの本文に移動する

## <a name="list-all-items-explicitly"></a>すべての項目を明示的に一覧表示する

現時点では、非読み取り専用プロジェクトの [ソリューションエクスプローラー] ウィンドウには、ワイルドカード拡張項目を表示する方法はありません。 ソリューションエクスプローラーは、プロジェクトがすべての項目を明示的に一覧表示する必要があります。

`.vcxproj`Visual Studio 2019 バージョン16.7 以降で、プロジェクトを自動的にワイルドカードを展開するには、プロパティをに設定し `ReplaceWildcardsInProjectItems` `true` ます。 ルートディレクトリにファイルを作成し、次の内容を使用することをお勧め *`Directory.Build.props`* します。

```xml
<Project>
  <PropertyGroup>
    <ReplaceWildcardsInProjectItems>true</ReplaceWildcardsInProjectItems>
  </PropertyGroup>
</Project>
```

## <a name="mark-your-project-as-read-only"></a>プロジェクトを読み取り専用としてマークする

Visual Studio 2019 バージョン16.7 以降では、プロジェクトを *読み取り*専用としてマークできます。 プロジェクトを読み取り専用としてマークするには、次のプロパティをファイルに追加する *`.vcxproj`* か、またはそれによってインポートされる任意のファイルに追加します。

```xml
<PropertyGroup>
    <ReadOnlyProject>true</ReadOnlyProject>
</PropertyGroup>
```

`<ReadOnlyProject>`この設定は、Visual Studio がプロジェクトを編集および保存できないようにします。そのため、ワイルドカードを含む任意の MSBuild コンストラクトを使用できます。

Visual Studio が *`.vcxproj`* ファイルまたはそのインポートのプロジェクト項目でワイルドカードを検出した場合は、プロジェクトキャッシュが使用できないことを理解しておくことが重要です。 ワイルドカードを使用するプロジェクトが多数ある場合、IDE でのソリューションの読み込み時間が大幅に長くなります。

## <a name="move-wildcard-items-to-a-target-body"></a>ワイルドカード項目をターゲットの本文に移動する

ワイルドカードを使用して、リソースを収集したり、生成されたソースを追加したりすることができます。 ソリューションエクスプローラーウィンドウに表示されている必要がない場合は、代わりに次の手順を使用できます。

1. 項目グループの名前を変更して、ワイルドカードを追加します。 たとえば、の代わりに次のようになります。

   ```xml
   <Image Include="*.bmp" />
   <ClCompile Include="*.cpp" />
   ```

   次のように変更します。

   ```xml
   <_WildCardImage Include="*.bmp" />
   <_WildCardClCompile Include="*.cpp" />
   ```

1. このコンテンツをファイルに追加  *`.vcxproj`* します。または、ルート *`Directory.Build.targets`* ディレクトリ内のファイルに追加し、そのルートの下にあるすべてのプロジェクトに影響を与えます。

   ```xml
   <Target Name="AddWildCardItems"
       AfterTargets="BuildGenerateSources">
     <ItemGroup>
       <Image Include="@(_WildCardImage)" />
       <ClCompile Include="@(_WildCardClCompile)" />
     </ItemGroup>
   </Target>
   ```

   この変更により、ファイルで定義されている項目がビルドに表示され  *`.vcxproj`* ます。 ただし、ソリューションエクスプローラーウィンドウに表示されなくなり、IDE で問題が発生することはありません。

1. エディターでこれらのファイルを開くときに、項目に対して正しい IntelliSense を表示するには  `_WildCardClCompile`   、次の内容を追加します。

   ```xml
   <PropertyGroup>
     <ComputeCompileInputsTargets>
       AddWildCardItems
       $(ComputeCompileInputsTargets)
     </ComputeCompileInputsTargets>
   </PropertyGroup>
   ```

実質的には、ターゲットの本文内のすべての項目に対してワイルドカードを使用できます。 では、  `ItemGroup`   プロジェクト項目として定義されていないワイルドカードをで使用することもでき [`ProjectSchemaDefinition`](https://devblogs.microsoft.com/cppblog/vc-MSBuild-extensibility-example/) ます。

> [!NOTE]
> ワイルドカードをファイルからインポートされたファイルに移動した場合は、[ *`.vcxproj`* ソリューションエクスプローラー] ウィンドウに表示されません。 この変更により、プロジェクトを変更せずに IDE に読み込むこともできます。 ただし、プロジェクトキャッシュを無効にするため、この方法はお勧めしません。

## <a name="see-also"></a>関連項目

[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)<br/>
[プロパティページの XML ファイル](property-page-xml-files.md)
