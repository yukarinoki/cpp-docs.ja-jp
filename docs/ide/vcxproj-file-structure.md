---
title: .vcxproj ファイルと .props ファイルの構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/27/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe466ff9250543a61fde8da41900b152a9874e09
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="vcxproj-and-props-file-structure"></a>.vcxproj と .props ファイルの構造

MSBuild は Visual Studio は; で、既定のプロジェクト システムです。選択すると**ファイル |新しいプロジェクト**Visual C では、設定を持つが、拡張子を持つ XML プロジェクト ファイルに格納されている MSBuild プロジェクトを作成する`.vcxproj`です。 .Props ファイルおよび .targets ファイルの設定を格納するため、プロジェクト ファイルはインポートも可能性があります。 ほとんどの場合、プロジェクト ファイルを手動で編集する必要はありませんで実際には編集しないようにして、手動で MSBuild をよく理解していません。 可能な限りは、プロジェクト設定を変更する、Visual Studio のプロパティ ページを使用する必要があります (を参照してください[のプロジェクト プロパティの操作](working-with-project-properties.md)です。 ただし、場合によっては、プロジェクト ファイルまたはプロパティ シートを手動で変更する必要があります。 そのようなシナリオは、この記事には、ファイルの構造に関する基本的な情報が含まれています。

**重要:** 

.Vcxproj ファイルを手動で編集する場合は、これらの情報に注意してください。

1. ファイルの構造は、この記事に記載されて、所定のフォームに従う必要があります。

1. Visual C プロジェクト システム現在はサポートされていませんワイルドカード プロジェクト項目にします。 たとえば、これはサポートされていません。

   ```xml
   <ClCompile Include="*.cpp"/>
   ```

1. Visual C プロジェクト システム現在はサポートされていませんマクロ プロジェクト項目のパスにします。 たとえば、これはサポートされていません。

   ```xml
   <ClCompile Include="$(IntDir)\generated.cpp"/>
   ```

1. プロジェクトのプロパティを正しく追加、削除、またはで編集する際に変更するために、**プロジェクト プロパティ**ダイアログ ボックスで、ファイルは、各プロジェクト構成に別々 のグループを含める必要があり、条件は、この形式にする必要があります。

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

1. プロパティ規則ファイルで指定されている、適切なラベルを持つグループ内の各プロパティを指定する必要があります。 詳細については、次を参照してください。[プロパティ ページ xml ルール ファイル](property-page-xml-files.md)です。

## <a name="vcxproj-file-elements"></a>.vcxproj ファイルの要素

テキスト エディターまたは XML エディターを使用して、.vcxproj ファイルの内容を検査することができます。 ソリューション エクスプ ローラーでプロジェクトを右クリックして Visual Studio で表示できます選択**プロジェクトのアンロード**選択し**編集 Foo.vcxproj**です。

最初にことを確認することは、最上位要素が特定の順序で表示されることです。 例えば:

- ほとんどのプロパティ グループおよび項目定義グループは、Microsoft.Cpp.Default.props のインポート後に発生します。
- すべてのターゲットは、ファイルの最後にインポートされます。
- 一意のラベルを持つ複数のプロパティ グループがあり、特定の順序で発生しました。

MSBuild は順次評価モデルに基づいているために、プロジェクト ファイル内の要素の順序は非常に重要です。  すべてのインポートされた .props および .targets ファイルを含む、プロジェクト ファイルは、プロパティの複数の定義で構成され、最後の定義は、前のものをオーバーライドします。 次の例では、MSBUild エンジンを検出すると、最後に、評価中にあるために、値"xyz"のコンパイル時に設定されます。

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

次のスニペットは、最小限の .vcxproj ファイルを示しています。 Visual Studio によって生成された、.vcxproj ファイルには、これら MSBuild の最上位の要素が含まれ、(ただし、このようなそれぞれの最上位要素のコピーを複数含めることは) この順序で表示されます。 なお`Label`属性は、任意のタグのみで使用される Visual Studio サインポストとして編集するため。 他の関数がありません。

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

次のセクションでは、これらの各要素の目的と理由に順序付けされてこの方法について説明します。

### <a name="project-element"></a>Project 要素

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project` ルート ノードです。 使用する MSBuild のバージョンともこのファイルは、MSBuild.exe に渡されるときに実行される既定のターゲットを指定します。

### <a name="projectconfigurations-itemgroup-element"></a>ProjectConfigurations ItemGroup 要素

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations` プロジェクト構成の説明が含まれています。 例としては、デバッグ |Win32、リリース |Win32、デバッグ |ARM というようにします。 多くのプロジェクト設定は、特定の構成に固有です。 たとえば、可能性がありますする最適化プロパティが、リリース ビルド、デバッグ ビルドではないを設定します。

`ProjectConfigurations`項目グループは、ビルド時に使用されません。 Visual Studio IDE、プロジェクトを読み込むために必要があります。 次の項目グループの .props ファイルに移動し、.vcxproj ファイルにインポートできます。 ただし、その場合は、構成を追加または削除する場合は、する必要があります手動で編集する .props ファイルです。IDE を使用することはできません。

### <a name="projectconfiguration-elements"></a>ProjectConfiguration 要素

次のスニペットは、プロジェクト構成を示しています。 この例では ' デバッグ | x 64' は、構成の名前。 プロジェクト構成名形式 $(Configuration)|$(Platform). でなければなりません プロジェクト構成ノードは、2 つのプロパティを持つことができます。 構成とプラットフォームです。 これらのプロパティは、構成がアクティブな場合は、ここで指定した値を使用して自動的に設定されます。

   ```xml
   <ProjectConfiguration Include="Debug|x64">
     <Configuration>Debug</Configuration>
     <Platform>x64</Platform>
   </ProjectConfiguration>
   ```

IDE は、すべてのプロジェクト構成アイテムで使用される構成とプラットフォームの値の任意の組み合わせのプロジェクト構成を検索するが必要です。 多くの場合、つまり、プロジェクトでは、この要件を満たすために意味のないプロジェクト構成される場合があります。 たとえば、プロジェクトにこれらの構成がある場合。

- デバッグ |Win32
- 小売 |Win32
- 32 ビットの特別な最適化 |Win32

ことも必要これらの構成では、x64 の意味がありません「特別な 32 ビットの最適化」にもかかわらず。

- Debug|x64
- 小売 | x64
- 32 ビットの特別な最適化 | x64

ビルドを無効にしてコマンドでは、どのような構成を配置、**ソリューション構成マネージャー**です。

### <a name="globals-propertygroup-element"></a>Globals PropertyGroup 要素

```xml
 <PropertyGroup Label="Globals" />
```

`Globals` ProjectGuid、RootNamespace、ApplicationType などのプロジェクト レベルの設定が含まれています/ApplicationTypeRevision です。 最後の 2 つは、多くの場合、ターゲット OS を定義します。 プロジェクトのために参照とプロジェクト項目できない条件がある現在、1 つの OS をターゲットのみできます。 これらのプロパティは、通常でオーバーライドされない他の場所でプロジェクト ファイルです。 このグループは構成に依存するではありませんし、プロジェクト ファイルで 1 つのグローバル グループのみが存在する通常このためです。

### <a name="microsoftcppdefaultprops-import-element"></a>Microsoft.Cpp.default.props Import 要素

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

**Microsoft.Cpp.default.props**プロパティ シートが Visual Studio が付属しており、変更できません。 プロジェクトの既定の設定が含まれています。 ApplicationType、によって、既定値が異なる場合があります。

### <a name="configuration-propertygroup-elements"></a>PropertyGroup 要素の構成

```xml
<PropertyGroup Label="Configuration" />
```

A`Configuration`プロパティ グループには、接続されている構成の状態 (など`Condition=”'$(Configuration)|$(Platform)'=='Debug|Win32'”`)、および構成ごとに 1 つ、複数のコピーで提供されています。 このプロパティ グループでは、特定の構成に設定されているプロパティをホストします。 構成プロパティが PlatformToolset が含まれ、内のシステム プロパティ シートのインクルードを制御も**Microsoft.Cpp.props**です。 たとえば、次のプロパティを定義する`<CharacterSet>Unicode</CharacterSet>`、システム プロパティ シート、 **microsoft です。Cpp.unicodesupport.props**が含まれます。 検査する場合**Microsoft.Cpp.props**、行が表示されます:`<Import Condition=”'$(CharacterSet)' == 'Unicode'”   Project=”$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props”/>`です。

### <a name="microsoftcppprops-import-element"></a>Microsoft.Cpp.props Import 要素

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

**Microsoft.Cpp.props**プロパティ シートに (直接または imports を介して) は、コンパイラの最適化と警告レベル プロパティ、MIDL ツールの TypeLibraryName など多くのツールに固有のプロパティの既定値を定義プロパティ、およびなどです。 また、すぐに上記のプロパティ グループでどの構成プロパティが定義に基づく各種のシステム プロパティ シートをインポートします。

### <a name="extensionsettings-importgroup-element"></a>ExtensionSettings ImportGroup 要素

```xml
<ImportGroup Label="ExtensionSettings" />
```

`ExtensionSettings`グループには、ビルドのカスタマイズの一部であるプロパティ シートのインポートが含まれています。 ビルドのカスタマイズは、最大 3 つのファイルによって定義されます: .targets ファイルに、.props ファイルおよび .xml ファイルです。 このグループ インポートにはには、.props ファイルのインポートが含まれています。

### <a name="propertysheets-importgroup-elements"></a>PropertySheets ImportGroup 要素

```xml
<ImportGroup Label="PropertySheets" />
```

`PropertySheets`グループには、ユーザー プロパティ シートのインポートが含まれています。 これらは、Visual Studio の プロパティ マネージャー ビューを通じて追加したプロパティ シートです。 インポートの表示順序は重要なはされ、プロパティ マネージャーでが反映されます。 通常、プロジェクト ファイルには、このグループの種類のインポート、プロジェクト構成ごとに 1 つの複数のインスタンスが含まれています。

### <a name="usermacros-propertygroup-element"></a>ユーザー マクロ PropertyGroup 要素

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros` プロパティが含まれています、ビルド プロセスをカスタマイズするために使用できる変数として作成します。 たとえば、$(CustomOutputPath) として、カスタムの出力パスを定義し、その他の変数を定義するユーザー マクロを定義できます。 このプロパティ グループでは、このようなプロパティを格納します。 Visual Studio で、このグループが作成されないこと、プロジェクト ファイルで Visual C がユーザー マクロの構成をサポートしていないために注意してください。 ユーザー マクロは、プロパティ シートでサポートされます。

### <a name="per-configuration-propertygroup-elements"></a>PropertyGroup 要素の構成単位

```xml
<PropertyGroup />
```

このプロパティ グループは、すべてのプロジェクト構成の構成ごとに 1 つの複数のインスタンスがあります。 各プロパティ グループには、接続されている 1 つの構成条件が必要です。 構成のいずれかがない場合は、**プロジェクト プロパティ**ダイアログが正しく動作しません。 上記のプロパティ グループとは異なりこのいずれかにラベルがありません。 このグループには、プロジェクトの構成レベルの設定が含まれています。 これらの設定は、指定した項目グループの一部であるすべてのファイルに適用されます。 ビルドのカスタマイズ項目定義のメタデータがここでは初期化されます。

この PropertyGroup が後に続く必要があります`<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />`-h-1 前に、ラベルのない他の PropertyGroup および (それ以外の場合のプロジェクト プロパティの編集は正しく動作しません)。

### <a name="per-configuration-itemdefinitiongroup-elements"></a>構成ごとの ItemDefinitionGroup 要素

```xml
 <ItemDefinitionGroup />
```

項目の定義が含まれています。 これらにより、構成ごとにラベルのない PropertyGroup 要素と同じ条件規則が従う必要があります。

### <a name="itemgroup-elements"></a>ItemGroup 要素

```xml
<ItemGroup />
```

プロジェクト内の項目 (ソース ファイルなど) が含まれています。 条件は、プロジェクト項目 (つまり、項目の種類ルールの定義によって、プロジェクト項目として扱われます) はサポートされません。

メタデータは、それらがすべて同じ場合でも、各構成の構成の条件にすることが必要です。 例えば:

   ```xml
   <ItemGroup>
     <ClCompile Include="stdafx.cpp">
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|x64’">true</TreatWarningAsError>
     </ClCompile>
   </ItemGroup>
   ```

Visual C プロジェクト システム現在はサポートされていませんワイルドカード プロジェクト項目にします。

   ```xml
   <ItemGroup>
     <ClCompile Include="*.cpp"> <!--Error-->
   </ItemGroup>
   ```

Visual C プロジェクト システム現在はサポートされていませんマクロ プロジェクト項目にします。

   ```xml
   <ItemGroup>
     <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
   </ItemGroup>
   ```

参照は、ItemGroup で指定し、これらの制限があります。

- 参照は、条件をサポートしていません。
- 参照メタデータは、条件をサポートしていません。

### <a name="microsoftcpptargets-import-element"></a>Microsoft.Cpp.targets Import 要素

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

定義 (直接または imports を介して) などのビルド ターゲットを Visual C クリーンアップなどします。

### <a name="extensiontargets-importgroup-element"></a>ExtensionTargets ImportGroup 要素

```xml
<ImportGroup Label="ExtensionTargets" />
```

このグループには、カスタマイズのビルド ターゲット ファイルのインポートが含まれています。

## <a name="impact-of-incorrect-ordering"></a>間違った順序の影響

Visual Studio IDE、プロジェクト ファイルが上記で説明した順序によって異なります。 たとえば、プロパティ ページで、プロパティ値を定義するときは IDE に空のラベルのプロパティ グループでのプロパティの定義は配置一般にします。 これにより、システム プロパティ シートの状態に既定値はユーザー定義の値によってオーバーライドされることができます。 同様に、ターゲット ファイルは、上記で定義されたプロパティに消費するためと、一般的に定義していないプロパティ自体から、最後にインポートされます。 同様に、ユーザー プロパティ シートがシステム プロパティ シートの後にインポートされます (を使用して含まれている**Microsoft.Cpp.props**)。 これにより、ユーザーがシステム プロパティ シートで取り出されたすべての既定値をオーバーライドすることができます。

.Vcxproj ファイルにこのレイアウトに従っていない場合ビルド結果可能性があります期待どおりではありません。 たとえば、誤って、システム プロパティ シートをインポートするには、ユーザーが定義されているプロパティ シートの後に場合、ユーザーの設定はシステム プロパティ シートによってオーバーライドされます。

でも、IDE のデザイン時のエクスペリエンスは、要素の適切な順序付けによってある程度依存します。 例では、.vcxproj ファイルがない場合、`PropertySheets`インポート グループ、IDE でユーザーが作成される新しいプロパティ シートを配置する場所を決定できない**プロパティ マネージャー**です。 これは、ユーザー シート システム シートによってオーバーライドされる可能性があります。 IDE で使用されるヒューリスティックでは、.vcxproj ファイルのレイアウトのマイナーの不整合を許容できる、この記事の前半に示した構造から外れるしないように強くお勧めします。

## <a name="how-the-ide-uses-element-labels"></a>IDE が要素のラベルを使用する方法

設定すると、IDE で、 **UseOfAtl**プロパティの [全般] プロパティ ページ、プロジェクト ファイルで構成プロパティ グループに書き込まれるときに、 **TargetName**同じページで、プロパティのプロパティ構成ごとにラベルのないプロパティ グループに書き込まれます。 Visual Studio は、各プロパティの書き込み先の情報については、プロパティ ページの xml ファイルを検索します。 **全般**プロパティ ページ (英語版の Visual Studio Enterprise Edition があると仮定した場合、)、このファイルは`%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml`します。 プロパティ ページ XML ルール ファイルでは、ルールとそのすべてのプロパティに関する静的な情報を定義します。 このような 2 つの情報は、変換先ファイル (その値が書き込まれるファイル) で、規則のプロパティの優先位置です。 優先の位置は、プロジェクト ファイルの要素のラベル属性によって指定されます。

## <a name="property-sheet-layout"></a>プロパティ シートのレイアウト

次の XML スニペットは、プロパティ シート (.props) ファイルの最小のレイアウトです。 .Vcxproj ファイルに似ており、.props 要素の機能は、以前のディスカッションから推論することができます。

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

プロパティ シート、VCTargets フォルダー内の .props ファイルの 1 つをコピーし、目的に応じて変更します。 Visual Studio 2017 年 1 Enterprise edition、VCTargets の既定のパスは`%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets`します。

## <a name="see-also"></a>関連項目

[プロジェクトのプロパティの操作](working-with-project-properties.md)  
[プロパティ ページの XML ファイル](property-page-xml-files.md)  
