---
title: .vcxproj ファイルと .props ファイルの構造
description: C++ ネイティブ MSBuild プロジェクトの .vcxproj および props ファイルにプロジェクト情報を格納する方法。
ms.date: 09/30/2020
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
ms.openlocfilehash: 562ef0c1b371d7212f31da1917d19c012e4cbb24
ms.sourcegitcommit: f7fbdc39d73e1fb3793c396fccf7a1602af7248b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "91662283"
---
# <a name="vcxproj-and-props-file-structure"></a>`.vcxproj` および `.props` ファイル構造

[MSBuild](../msbuild-visual-cpp.md)は、Visual Studio の既定のプロジェクトシステムです。Visual C++ の [**ファイル**] [新しいプロジェクト] を選択すると、  >  **New Project** MSBuild プロジェクトが作成されます。このプロジェクトの設定は、拡張子がの XML プロジェクトファイルに格納されてい *`.vcxproj`* ます。 プロジェクトファイルでは、 *`.props`* 設定を格納できるファイルやファイルをインポートすることもでき *`.targets`* ます。

プロジェクトの作成と変更は IDE でのみ行うことをお勧めし *`.vcxproj`* ます。また、可能な限り手動編集を回避することをお勧めします。 ほとんどの場合、プロジェクトファイルを手動で編集する必要はありません。 可能な場合は常に、Visual Studio のプロパティページを使用してプロジェクトの設定を変更する必要があります。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

IDE で不可能なカスタマイズが必要な場合は、カスタムの props またはターゲットを追加することをお勧めします。 カスタマイズを挿入するための便利な場所は、 *`Directory.Build.props`* およびファイルです。このファイルは、 *`Directory.Build.targets`* すべての MSBuild ベースのプロジェクトに自動的にインポートされます。

場合によって *`.vcxproj`* は、プロジェクトファイルまたはプロパティシートを手動で変更する必要があることもあります。 MSBuild を十分に理解していない限り、手動で編集することはお勧めしません。この記事のガイドラインに従ってください。 IDE でファイルを自動的に読み込んで更新するために *`.vcxproj`* 、これらのファイルには、他の MSBuild プロジェクトファイルには適用されないいくつかの制限があります。 手動で編集するように設計されていません。 間違っていると、IDE がクラッシュしたり、予期しない動作が発生したりする可能性があります。

手動による編集シナリオでは、この記事にはおよび関連ファイルの構造に関する基本的な情報が含まれてい *`.vcxproj`* ます。

**重要:**

ファイルを手動で編集する場合は *`.vcxproj`* 、次の点に注意してください。

- ファイルの構造は、この記事に記載されている所定のフォームに従う必要があります。

- Visual Studio C++ プロジェクトシステムでは、現在、ワイルドカードまたはリストをプロジェクト項目内で直接サポートしていません。 たとえば、次の形式はサポートされていません。

   ```xml
   <ItemGroup>
     <None Include="*.txt"/>
     <ClCompile Include="a.cpp;b.cpp"/>
   </ItemGroup>
   ```

   プロジェクトでのワイルドカードのサポートと考えられる回避策の詳細については、「 [ `.vcxproj` ファイルとワイルドカード](vcxproj-files-and-wildcards.md)」を参照してください。

- 現在、Visual Studio C++ プロジェクトシステムでは、プロジェクト項目パスのマクロはサポートされていません。 たとえば、次の形式はサポートされていません。

   ```xml
   <ItemGroup>
     <ClCompile Include="$(IntDir)\generated.cpp"/>
   </ItemGroup>
   ```

   "サポートされていません" は、IDE のすべての操作でマクロが動作する保証がないことを意味します。 異なる構成の値を変更しないマクロは機能しますが、項目が別のフィルターまたはプロジェクトに移動された場合は保存されない可能性があります。 さまざまな構成の値を変更するマクロを使用すると、問題が発生します。 これは、IDE がプロジェクト項目のパスがプロジェクトの構成によって異なることを予期していないためです。

- **プロジェクトプロパティダイアログで**プロジェクトのプロパティを編集するときに、プロジェクトのプロパティを正しく追加、削除、または変更するには、ファイルにプロジェクト構成ごとに個別のグループが含まれている必要があります。 条件は次の形式で指定する必要があります。

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

- プロパティ規則ファイルに指定されているとおりに、各プロパティを適切なラベルでグループに指定する必要があります。 詳しくは、「[プロパティ ページの XML 規則ファイル](property-page-xml-files.md)」をご覧ください。

## <a name="vcxproj-file-elements"></a>`.vcxproj` file 要素

*`.vcxproj`* 任意のテキストエディターまたは XML エディターを使用して、ファイルの内容を検査できます。 Visual Studio のソリューション エクスプローラーでプロジェクトを右クリックし、**[プロジェクトのアンロード]**、**[Foo.vcxproj の編集]** の順に選ぶと表示されます。

最初に注目する点は、最上位の要素が特定の順序で表示されることです。 次に例を示します。

- ほとんどのプロパティ グループおよび項目定義グループは、Microsoft.Cpp.Default.props のインポートの後に出現します。

- すべてのターゲットは、ファイルの最後にインポートされます。

- 複数のプロパティ グループがあり、それぞれが一意のラベルを持ち、特定の順序で出現します。

MSBuild は順次評価モデルに基づいているため、プロジェクトファイル内の要素の順序は非常に重要です。  インポートされたすべてのファイルとファイルを含むプロジェクトファイルが、 *`.props`* *`.targets`* プロパティの複数の定義で構成されている場合、最後の定義は、前の定義よりも優先されます。 次の例では、値 "xyz" はコンパイル中に設定されます。これは、MSBUild エンジンが評価中に最後にそれを検出したためです。

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

次のスニペットは、最小限のファイルを示して *`.vcxproj`* います。 *`.vcxproj`* Visual Studio によって生成されるファイルには、これらの最上位レベルの MSBuild 要素が含まれます。 また、各最上位要素の複数のコピーが含まれている場合もありますが、この順序で表示されます。 すべて `Label` の属性は、編集用の signposts として Visual Studio によってのみ使用される任意のタグです。他の関数はありません。

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003'>
  <ItemGroup Label="ProjectConfigurations" />
  <PropertyGroup Label="Globals" />
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
  <PropertyGroup Label="Configuration" />
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ImportGroup Label="ExtensionSettings" />
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
  <ImportGroup Label="ExtensionTargets" />
</Project>
```

次のセクションでは、これらの各要素の目的と、その目的について説明します。

### <a name="project-element"></a>Project 要素

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project` はルート ノードです。 使用する MSBuild バージョンと、このファイルを MSBuild.exe に渡すときに実行する既定のターゲットを指定します。

### <a name="projectconfigurations-itemgroup-element"></a>ItemGroup の ProjectConfigurations 要素

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations` には、プロジェクトの構成の説明が含まれます。 たとえば、Debug|Win32、Release|Win32、Debug|ARM などです。 プロジェクトの多くの設定は、特定の構成に固有です。 たとえば、デバッグビルドではなく、リリースビルドの最適化プロパティを設定したい場合があります。

`ProjectConfigurations`項目グループはビルド時には使用されません。 Visual Studio IDE でプロジェクトを読み込む必要があります。 この項目グループは、ファイルに移動 *`.props`* して、ファイルにインポートでき *`.vcxproj`* ます。 ただし、その場合、構成を追加または削除する必要がある場合は、ファイルを手動で編集する必要があります *`.props`* 。 IDE を使用することはできません。

### <a name="projectconfiguration-elements"></a>ProjectConfiguration 要素

次のスニペットでは、プロジェクトの構成を示します。 この例では、' Debug | x64 ' は構成名です。 プロジェクト構成名は、の形式である必要があり `$(Configuration)|$(Platform)` ます。 ノードには `ProjectConfiguration` `Configuration` 、との2つのプロパティを設定できます `Platform` 。 これらのプロパティは、構成がアクティブなときにここで指定した値で自動的に設定されます。

```xml
<ProjectConfiguration Include="Debug|x64">
  <Configuration>Debug</Configuration>
  <Platform>x64</Platform>
</ProjectConfiguration>
```

IDE では、 `Configuration` `Platform` すべての項目で使用されるとの値の任意の組み合わせのプロジェクト構成が必要 `ProjectConfiguration` です。 多くの場合、プロジェクトには、この要件を満たすための無意味なプロジェクト構成が含まれている可能性があります。 たとえば、プロジェクトに次のような構成があるものとします。

- Debug|Win32

- Retail|Win32

- Special 32-bit Optimization|Win32

この場合、"Special 32-bit Optimization" は x64 に対しては意味がありませんが、次のような構成も存在する必要があります。

- Debug|x64

- Retail|x64

- Special 32-bit Optimization|x64

**ソリューション構成マネージャー**では、任意の構成に対してビルドと配置のコマンドを無効にできます。

### <a name="globals-propertygroup-element"></a>PropertyGroup の Globals 要素

```xml
<PropertyGroup Label="Globals" />
```

`Globals` 、、などのプロジェクトレベルの設定が含まれてい `ProjectGuid` `RootNamespace` `ApplicationType` `ApplicationTypeRevision` ます。 最後の 2 つは、多くの場合、ターゲット OS を定義します。 プロジェクトは、現在、参照およびプロジェクト項目に条件を設定できないため、1つの OS のみをターゲットにすることができます。 これらのプロパティは、通常、プロジェクト ファイル内の他の場所ではオーバーライドされません。 このグループは構成に依存しません。通常、プロジェクトファイルには1つの `Globals` グループのみが存在します。

### <a name="microsoftcppdefaultprops-import-element"></a>Import の Microsoft.Cpp.default.props 要素

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

この **プロパティシートには** Visual Studio が付属しており、変更することはできません。 プロジェクトの既定の設定が含まれます。 既定値は、ApplicationType によって異なる場合があります。

### <a name="configuration-propertygroup-elements"></a>PropertyGroup の Configuration 要素

```xml
<PropertyGroup Label="Configuration" />
```

`Configuration` プロパティ グループには、添付された構成条件 (`Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"` など) があり、構成ごとに 1 つずつの、複数のコピーが提供されます。 このプロパティ グループは、特定の構成に対して設定されるプロパティをホストします。 構成プロパティは PlatformToolset を含み、**Microsoft.Cpp.props** でのシステム プロパティ シートのインクルードも制御します。 たとえば、プロパティ `<CharacterSet>Unicode</CharacterSet>` を定義した場合、システム プロパティ シート **microsoft.Cpp.unicodesupport.props** がインクルードされます。 「」という行が表示され**ます。** `<Import Condition="'$(CharacterSet)' == 'Unicode'" Project="$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props" />`

### <a name="microsoftcppprops-import-element"></a>Import の Microsoft.Cpp.props 要素

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

**Microsoft**のプロパティシート (直接またはインポートによる) では、ツール固有の多くのプロパティの既定値が定義されています。 例としては、コンパイラの最適化と警告レベルのプロパティ、MIDL ツールの TypeLibraryName プロパティなどがあります。 また、プロパティグループに定義されている構成プロパティに基づいて、さまざまなシステムプロパティシートをインポートします。

### <a name="extensionsettings-importgroup-element"></a>ImportGroup の ExtensionSettings 要素

```xml
<ImportGroup Label="ExtensionSettings" />
```

`ExtensionSettings` グループには、ビルドのカスタマイズの一部であるプロパティ シートのインポートが含まれます。 ビルドのカスタマイズは、ファイル、ファイル *`.targets`* *`.props`* 、および *`.xml`* ファイルの3つまでのファイルによって定義されます。 このインポートグループには、ファイルのインポートが含まれてい *`.props`* ます。

### <a name="propertysheets-importgroup-elements"></a>ImportGroup の PropertySheets 要素

```xml
<ImportGroup Label="PropertySheets" />
```

`PropertySheets` グループには、ユーザー プロパティ シートのインポートが含まれます。 これらのインポートは、Visual Studio のプロパティマネージャービューを通じて追加するプロパティシートです。 これらのインポートは列記されている順序が重要であり、プロパティ マネージャーに反映されます。 通常、プロジェクト ファイルには、この種のインポート グループの複数のインスタンス (プロジェクト構成ごとに 1 つずつ) が含まれます。

### <a name="usermacros-propertygroup-element"></a>PropertyGroup の UserMacros 要素

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros` には、ユーザーが変数として作成し、ビルド プロセスのカスタマイズに使われるプロパティが含まれます。 たとえば、カスタム出力パスを定義するためのユーザー マクロを $(CustomOutputPath) として定義し、それを使って他の変数を定義できます。 このプロパティ グループは、そのようなプロパティを格納します。 Visual Studio では、構成用のユーザーマクロを Visual C++ がサポートしていないため、このグループはプロジェクトファイルに設定されません。 ユーザー マクロは、プロパティ シートでサポートされています。

### <a name="per-configuration-propertygroup-elements"></a>構成ごとの PropertyGroup 要素

```xml
<PropertyGroup />
```

このプロパティ グループには、すべてのプロジェクト構成の構成ごとに 1 つずつ、複数のインスタンスがあります。 各プロパティ グループには、1 つの構成条件が添付されている必要があります。 いずれかの構成がない場合、**[プロジェクトのプロパティ]** ダイアログは正しく動作しません。 前に示したプロパティグループとは異なり、このグループにはラベルがありません。 このグループには、プロジェクトの構成レベルの設定が含まれます。 これらの設定は、指定された項目グループの一部であるすべてのファイルに適用されます。 ビルドのカスタマイズ項目定義のメタデータはここで初期化されます。

この PropertyGroup は、の後に指定する必要があります `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` 。その前にラベルがない他の PropertyGroup は使用できません (それ以外の場合、プロジェクトプロパティの編集は正常に機能しません)。

### <a name="per-configuration-itemdefinitiongroup-elements"></a>構成ごとの ItemDefinitionGroup 要素

```xml
<ItemDefinitionGroup />
```

項目の定義が含まれます。 これらの定義は、構成ごとのラベルのない要素と同じ条件規則に従う必要があり `PropertyGroup` ます。

### <a name="itemgroup-elements"></a>ItemGroup 要素

```xml
<ItemGroup />
```

`ItemGroup` 要素には、プロジェクト内の項目 (ソースファイルなど) が格納されます。 プロジェクト項目 (つまり、規則の定義によってプロジェクト項目として扱われる項目の種類) では、条件はサポートされていません。

メタデータは、すべてが同じであっても、各構成の構成条件を持つ必要があります。 次に例を示します。

```xml
<ItemGroup>
  <ClCompile Include="stdafx.cpp">
    <TreatWarningAsError Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">true</TreatWarningAsError>
    <TreatWarningAsError Condition="'$(Configuration)|$(Platform)'=='Debug|x64'">true</TreatWarningAsError>
  </ClCompile>
</ItemGroup>
```

現在、Visual Studio C++ プロジェクトシステムでは、プロジェクト項目でのワイルドカードはサポートされていません。

```xml
<ItemGroup>
  <ClCompile Include="*.cpp"> <!--Error-->
</ItemGroup>
```

現在、Visual Studio C++ プロジェクトシステムでは、プロジェクト項目のマクロはサポートされていません。

```xml
<ItemGroup>
  <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
</ItemGroup>
```

参照は ItemGroup で指定され、次のような制限があります。

- 参照が条件をサポートしていません。

- 参照メタデータは条件をサポートしていません。

### <a name="microsoftcpptargets-import-element"></a>Import の Microsoft.Cpp.targets 要素

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

ビルド、クリーンなどの C++ ターゲットを (直接またはインポートによって) 定義します。

### <a name="extensiontargets-importgroup-element"></a>ImportGroup の ExtensionTargets 要素

```xml
<ImportGroup Label="ExtensionTargets" />
```

このグループには、ビルド カスタマイズのターゲット ファイルのインポートが含まれます。

## <a name="impact-of-incorrect-ordering"></a>正しくない順序の影響

Visual Studio IDE は、前に説明した順序を持つプロジェクトファイルに依存します。 たとえば、プロパティ ページでプロパティの値を定義すると、IDE は一般に、ラベルが空であるプロパティ グループにそのプロパティの定義を配置します。 この順序により、システムプロパティシートに取り込まれた既定値は、ユーザー定義の値によって上書きされます。 同様に、ターゲットファイルは、前に定義されたプロパティを使用するので、最後にインポートされます。これは通常、プロパティ自体を定義しないためです。 同様に、ユーザープロパティシートは、システムプロパティシート (に含まれています) の後にインポートされ *`Microsoft.Cpp.props`* ます。 この順序により、システムプロパティシートによってもたらされるすべての既定値をユーザーがオーバーライドできるようになります。

ファイルが *`.vcxproj`* このレイアウトに従っていない場合、ビルドの結果は期待どおりではない可能性があります。 たとえば、ユーザーが定義したプロパティシートの後にシステムプロパティシートを誤ってインポートした場合、ユーザー設定はシステムプロパティシートによってオーバーライドされます。

IDE のデザイン時のエクスペリエンスでも、要素の正しい順序の程度に依存します。 たとえば、ファイルにインポートグループがない場合、IDE では、 *`.vcxproj`* `PropertySheets` ユーザーが **プロパティマネージャー**で作成した新しいプロパティシートを配置する場所を特定できないことがあります。 ユーザーシートがシステムシートによって上書きされる可能性があります。 IDE によって使用されるヒューリスティックでは、ファイルレイアウトの不整合が許容される *`.vcxproj`* 場合がありますが、この記事で前に示した構造にはないことを強くお勧めします。

## <a name="how-the-ide-uses-element-labels"></a>IDE が要素のラベルを使用する方法

IDE では、[全般] プロパティページで **Useofatl** プロパティを設定すると、プロジェクトファイルの構成プロパティグループに書き込まれます。 同じプロパティページの **TargetName** プロパティは、構成ごとのラベルのないプロパティグループに書き込まれます。 Visual Studio は、プロパティ ページの xml ファイルで、各プロパティを書き込む場所についての情報を取得します。 **[全般**] プロパティページでは、Visual Studio 2019 Enterprise Edition の英語版を使用していると仮定 `%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml` します。このファイルはです。 プロパティ ページの XML 規則ファイルでは、Rule とそのすべてのプロパティに関する静的な情報が定義されています。 そのような情報の 1 つは、書き込み先ファイル (その値が書き込まれるファイル) での Rule プロパティの優先位置です。 優先位置は、プロジェクト ファイルの要素の Label 属性によって指定されます。

## <a name="property-sheet-layout"></a>プロパティ シートのレイアウト

次の XML スニペットは、プロパティ シート (.props) ファイルの最小限のレイアウトです。 これはファイルに似て *`.vcxproj`* おり、要素の機能は *`.props`* 前の説明から推論できます。

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

独自のプロパティシートを作成するには、フォルダー内のいずれかのファイルをコピー *`.props`* *`VCTargets`* し、目的に応じて変更します。 Visual Studio 2019 Enterprise edition では、既定の *`VCTargets`* パスは `%ProgramFiles%\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\VC\VCTargets` です。

## <a name="see-also"></a>関連項目

[Visual Studio で C++ コンパイラとビルドプロパティを設定する](../working-with-project-properties.md)\
[プロパティページの XML ファイル](property-page-xml-files.md)\
[`.vcxproj` ファイルとワイルドカード](vcxproj-files-and-wildcards.md)
