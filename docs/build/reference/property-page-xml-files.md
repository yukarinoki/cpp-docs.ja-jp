---
title: プロパティ ページの XML 規則ファイル
description: Visual Studio IDE の C++ プロパティページの XML 規則ファイルと内容の説明。
ms.date: 10/14/2020
helpviewer_keywords:
- property page XML files
ms.openlocfilehash: f8aa893fa2b062da2f1d0784e5a9b1a6f2b30c95
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921400"
---
# <a name="property-page-xml-rule-files"></a>プロパティ ページの XML 規則ファイル

IDE のプロジェクトプロパティページは、既定の rules フォルダー内の XML ファイルによって構成されます。 XML ファイルには、ルールの名前、カテゴリ、個々のプロパティ、データ型、既定値、およびそれらを表示する方法が記述されています。 IDE でプロパティを設定すると、新しい値がプロジェクト ファイルに格納されます。

::: moniker range="msvc-140"

既定の規則フォルダーへのパスは、使用されている Visual Studio のロケールとバージョンによって異なります。 Visual Studio 2015 以前の開発者コマンド プロンプトの場合、ルール フォルダーは *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>`* です。 Visual Studio 2015 の場合、`<version>` 値は *`v140`* です。 `<locale>` は LCID です。たとえば、英語の場合は `1033` です。 インストールされている Visual Studio のエディションおよび言語ごとに異なるパスを使用します。 たとえば、Visual Studio 2015 Community エディションの英語版の既定のルール フォルダー パスは *`C:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\v140\1033\`* になります。

::: moniker-end

::: moniker range="msvc-150"

既定の規則フォルダーへのパスは、使用されている Visual Studio のロケールとバージョンによって異なります。 Visual Studio 2017 の開発者コマンド プロンプトの場合、ルール フォルダーは *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* です。 `<locale>` は LCID です。たとえば、英語の場合は `1033` です。 Visual Studio 2015 以前の開発者コマンド プロンプトの場合、ルール フォルダーは *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* です。`<version>` 値は Visual Studio 2015 の場合は *`v140`* です。 インストールされている Visual Studio のエディションおよび言語ごとに異なるパスを使用します。 たとえば、Visual Studio 2017 Community エディションの英語版の既定のルール フォルダー パスは *`C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\`* になります。

::: moniker-end

::: moniker range=">=msvc-160"

既定の規則フォルダーへのパスは、使用されている Visual Studio のロケールとバージョンによって異なります。 Visual Studio 2019 以降の開発者コマンド プロンプトのルール フォルダーは *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\<locale>\`* です。Visual Studio 2019 の場合、`<version>` 値は *`v160`* です。 `<locale>` は LCID です。たとえば、英語の場合は `1033` です。 Visual Studio 2017 の場合、ルール フォルダーは *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* です。 Visual Studio 2015 以前の開発者コマンド プロンプトの場合、ルール フォルダーは *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* です。 インストールされている Visual Studio のエディションおよび言語ごとに異なるパスを使用します。 たとえば、Visual Studio 2019 Community エディションの英語版の既定のルール フォルダー パスは *`C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Microsoft\VC\v160\1033\`* になります。

::: moniker-end

これらのファイルと Visual Studio IDE の内部動作を理解する必要があるのは、次の2つのシナリオです。

- カスタムプロパティページを作成する場合、または
- Visual Studio IDE を使用せずに、プロジェクトのプロパティをカスタマイズする場合。

## <a name="contents-of-rule-files"></a>規則ファイルの内容

まず、プロジェクトのプロパティページを開きます。 **ソリューションエクスプローラー** でプロジェクトノードを右クリックし、[ **プロパティ** ] を選択します。

![Visual Studio C++ プロジェクトのプロパティダイアログを表示します](../media/cpp-property-page-2017.png)

[ **構成プロパティ** ] の下の各ノードは、" *ルール* " と呼ばれます。 規則は、コンパイラのような1つのツールを表す場合があります。 一般に、という用語は、を実行し、出力を生成する可能性のあるプロパティを持つものを指します。 各ルールは、既定のルールフォルダー内の XML ファイルから設定されます。 たとえば、ここに示されている C/c + + の規則は、 *'cl.xml '* によって設定されます。

各ルールには一連のプロパティがあり、それらは *カテゴリ* 別に分類されています。 ルールの下にある各サブノードは、カテゴリを表します。 たとえば、[ **C/c + +** ] の下の [ **最適化** ] ノードには、コンパイラツールの最適化に関連するすべてのプロパティが含まれています。 プロパティとその値は、右側のウィンドウにグリッド形式で表示されます。

*`cl.xml`* メモ帳または任意の XML エディターで開くことができます。 というルートノードが表示され `Rule` ます。 これは、UI に表示されるプロパティの同じリストと、追加のメタデータを定義します。

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--Copyright, Microsoft Corporation, All rights reserved.-->
<Rule Name="CL" PageTemplate="tool" DisplayName="C/C++" SwitchPrefix="/" Order="10" xmlns="http://schemas.microsoft.com/build/2009/properties" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.Categories>
    <Category Name="General" DisplayName="General" />
    <Category Name="Optimization" DisplayName="Optimization" />
    <Category Name="Preprocessor" DisplayName="Preprocessor" />
    <Category Name="Code Generation" DisplayName="Code Generation" />
    <Category Name="Language" DisplayName="Language" />
    <Category Name="Precompiled Headers" DisplayName="Precompiled Headers" />
    <Category Name="Output Files" DisplayName="Output Files" />
    <Category Name="Browse Information" DisplayName="Browse Information" />
    <Category Name="Advanced" DisplayName="Advanced" />
    <Category Name="All Options" DisplayName="All Options" Subtype="Search" />
    <Category Name="Command Line" DisplayName="Command Line" Subtype="CommandLine" />
  </Rule.Categories>
  <!-- . . . -->
</Rule>
```

プロパティページの UI の [ **構成プロパティ** ] の下にあるすべてのノードに対して1つの XML ファイルがあります。 UI で規則を追加または削除することができます。これは、プロジェクト内の対応する XML ファイルの場所を含めたり、削除したりすることによって行います。 たとえば、次のような方法があり *`Microsoft.CppBuild.targets`* ます (1033 フォルダーより上位の1つのレベルが見つかりました) *`cl.xml`* 。

```xml
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>
```

すべてのデータを削除すると *`cl.xml`* 、次の基本的なフレームワークが作成されるようになります。

```xml
<?xml version="1.0" encoding="utf-8"?>
<Rule>
  <Rule.DataSource />
  <Rule.Categories>
    <Category />
    <!-- . . . -->
  </Rule.Categories>
  <BoolProperty />
  <EnumProperty />
  <IntProperty />
  <StringProperty />
  <StringListProperty />
</Rule>
```

次のセクションでは、各主要な要素と、アタッチできるメタデータのいくつかについて説明します。

### <a name="rule-attributes"></a>ルールの属性

**`<Rule>`** 要素は、XML ファイル内のルートノードです。 多くの属性を持つことができます。

```xml
<Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
          xmlns="http://schemas.microsoft.com/build/2009/properties"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.DisplayName>
    <sys:String>C/C++</sys:String>
  </Rule.DisplayName>
```

- **`Name`** : Name 属性はの ID です `Rule` 。 これは、プロジェクトのすべてのプロパティページ XML ファイル内で一意である必要があります。

- **`PageTemplate`** : この属性の値は、ui テンプレートのコレクションから選択するために UI によって使用されます。 "tool" テンプレートは、標準のグリッド形式でプロパティをレンダリングします。 この属性のその他の組み込みの値は、"debugger" と "generic" です。 これらの値を指定した結果の UI 形式を確認するには、デバッグ ノードと全般ノードをそれぞれ確認します。 "デバッガー" ページテンプレートの UI では、ドロップダウンボックスを使用して、さまざまなデバッガーのプロパティを切り替えます。 "Generic" テンプレートでは、ノードの下に複数のカテゴリサブノードがあるのではなく、すべてのプロパティカテゴリが1ページに表示され `Rule` ます。 この属性は、UI の提案にすぎません。 XML ファイルは、UI に依存しないように設計されています。 UI ごとに異なる目的のためにこの属性を使用することができます。

- **`SwitchPrefix`** : スイッチのコマンドラインで使用されるプレフィックス。 の値を指定すると、、、 `"/"` などのスイッチが表示さ **`/ZI`** **`/nologo`** **`/W3`** れます。

- **`Order`** : `Rule` システム内の他のすべてのルールと比較した、予想される UI クライアントの相対的な位置に対する提案。

- **`xmlns`** : 標準の XML 要素。 3 つの名前空間が一覧表示されます。 これらの属性は、それぞれ XML 逆シリアル化クラス、XML スキーマ、およびシステム名前空間の名前空間に対応しています。

- **`DisplayName`** : ノードのプロパティページの UI に表示される名前。 `Rule` この値はローカライズされます。 `DisplayName` `Rule` `Name` `SwitchPrefix` 内部ローカライズツールの要件により、属性 (やなど) としてではなく、の子要素として作成されました。 XML の観点からは、両方とも同じです。 そのため、単に属性にして煩雑さを軽減することも、そのままにしておくこともできます。

- **`DataSource`** : この重要なプロパティは、プロパティ値の読み取りと書き込みを行う場所と、そのグループ化 (後で説明します) をプロジェクトシステムに指示します。 の場合 *`cl.xml`* 、これらの値は次のとおりです。

    ```xml
    <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
    ```

  - `Persistence="ProjectFile"` のすべてのプロパティを `Rule` プロジェクトファイルまたはプロパティシートファイルに書き込む必要があることをプロジェクトシステムに指示します (プロパティページの生成に使用されたノードによって異なります)。 もう1つの値はであり、 `"UserFile"` これにより値がファイルに書き込まれ *`.user`* ます。

  - `ItemType="ClCompile"` は、プロパティがこの項目の種類の ItemDefinition メタデータまたは項目メタデータ (後者は、プロパティ ページがソリューション エクスプローラーでファイル ノードから生成された場合のみ) として格納されることを示します。 このフィールドが設定されていない場合、プロパティは PropertyGroup の共通プロパティとして書き込まれます。

  - `Label=""` は、プロパティが `ItemDefinition` メタデータとして書き込まれるときに、親 ItemDefinitionGroup のラベルが空になることを示しますます (すべての MSBuild 要素がラベルを持つことができます)。 Visual Studio 2017 以降では、ラベルの付いたグループを使用して、.vcxproj プロジェクト ファイルを移動します。 ほとんどのプロパティを含むグループには、 `Rule` ラベルとして空の文字列があります。

  - `HasConfigurationCondition="true"` は、現在のプロジェクト構成に対してのみ有効になるように、値に構成条件を添えるようにプロジェクト システムに指示します (条件は、親グループまたは値そのものに添えることができます)。 たとえば、プロジェクト ノードのプロパティ ページを開き、 **[構成プロパティ] > [C/C++ の全般]** の下でプロパティ **Treat Warnings As Error** の値を "Yes" に設定します。 次の値がプロジェクト ファイルに書き込まれます。 親 Itemdefinitiongroup に構成条件が添付されていることに注目してください。

    ```xml
    <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
      <ClCompile>
        <TreatWarningAsError>true</TreatWarningAsError>
      </ClCompile>
    </ItemDefinitionGroup>
    ```

     など、特定のファイルのプロパティページでこの値が設定されている場合、 *`stdafx.cpp`* プロパティ値は、次に示すように、プロジェクトファイルの項目の下に記述する必要があり `stdafx.cpp` ます。 構成条件がメタデータ自体に直接接続されていることに注意してください。

    ```xml
    <ItemGroup>
      <ClCompile Include="stdafx.cpp">
        <TreatWarningAsError Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">true</TreatWarningAsError>
      </ClCompile>
    </ItemGroup>
    ```

  ここに記載されていないもう1つの属性 `DataSource` は `PersistedName` です。 この属性を使用すると、別の名前を使用しているプロジェクト ファイル内のプロパティを表すことができます。 既定では、この属性はプロパティのに設定され `Name` ます。

  個々のプロパティは、 `DataSource` その親のをオーバーライドでき `Rule` ます。 その場合、そのプロパティの値の場所は、の他のプロパティとは異なり `Rule` ます。

- ここでは、やなど、の他の属性を示してい `Rule` `Description` ません `SupportsFileBatching` 。 またはその他の要素に適用できる属性の完全なセットは、 `Rule` これらの型のドキュメントを参照することによって取得できます。 または、`Microsoft.Build.Framework.dll` アセンブリ内の `Microsoft.Build.Framework.XamlTypes` 名前空間内の型でパブリック プロパティを調べることもできます。

- **`DisplayName`** 、 **`PageTemplate`** 、および **`Order`** は、この ui に依存しないデータモデルに存在する ui 関連のプロパティです。 これらのプロパティは、プロパティ ページを表示するために使用される任意の UI でほぼ確実に使用されます。 `DisplayName` と `Description` は、XML ファイル内のほぼすべての要素に存在する2つのプロパティです。 また、これら2つのプロパティはローカライズされているもののみです。

### <a name="category-elements"></a>Category 要素

は、 `Rule` 複数の要素を持つことができ `Category` ます。 カテゴリが XML ファイルに表示される順序は、同じ順序でカテゴリを表示するための UI の提案です。 たとえば、UI に表示される [ **C/c + +** ] ノードの下のカテゴリの順序は、の順序と同じです *`cl.xml`* 。 サンプル カテゴリは、次のようになります。

```xml
<Category Name="Optimization">
  <Category.DisplayName>
    <sys:String>Optimization</sys:String>
  </Category.DisplayName>
</Category>
```

このスニペットは、 `Name` `DisplayName` 前に説明した属性と属性を示しています。 ここでも、この例では示されていない属性が他に `Category` もあります。 詳細については、ドキュメントを参照するか、を使用してアセンブリを調べることによって確認でき *`ildasm.exe`* ます。

### <a name="property-elements"></a>Property 要素

ほとんどのルールファイルは、要素で構成さ `Property` れています。 には、のすべてのプロパティの一覧が含まれて `Rule` います。 各プロパティは、基本的なフレームワークに示されている5つの型のうち、、、、およびのいずれかになります `BoolProperty` `EnumProperty` `IntProperty` `StringProperty` `StringListProperty` 。 ファイルには、これらの種類のうちのいくつかしか存在しない場合があります。 プロパティには、詳細に記述できるようにする多数の属性があります。 に `StringProperty` ついては、こちらを参照してください。 残りの部分も同様です。

```xml
<StringProperty Subtype="file" Name="ObjectFileName" Category="Output Files" Switch="Fo">
  <StringProperty.DisplayName>
    <sys:String>Object File Name</sys:String>
  </StringProperty.DisplayName>
  <StringProperty.Description>
    <sys:String>Specifies a name to override the default object file name; can be file or directory name.(/Fo[name])</sys:String>
  </StringProperty.Description>
</StringProperty>
```

スニペット内の属性のほとんどは、前述しました。 新しいものは `Subtype` 、、 `Category` 、および `Switch` です。

- **`Subtype`** は `StringProperty` 、要素と要素に対してのみ使用できる属性です `StringListProperty` 。 コンテキスト情報が提供されます。 たとえば、この値は、 `file` プロパティがファイルパスを表すことを示します。 Visual Studio では、このようなコンテキスト情報を使用して編集エクスペリエンスを強化します。 たとえば、ユーザーがプロパティエディターとして視覚的にファイルを選択できるようにする Windows エクスプローラーウィンドウが用意されている場合があります。

- **`Category`** : このプロパティが分類されるカテゴリ。 UI 内の **[出力ファイル]** カテゴリの下で、このプロパティの検索を試みます。

- **`Switch`** : ルールがコンパイラツールなどのツールを表す場合、ほとんどの `Rule` プロパティはビルド時にツールの実行可能ファイルにスイッチとして渡されます。 この属性の値は、使用するスイッチリテラルを示します。 この例では、 `<StringProperty>` スイッチをにする必要があることを指定して **`Fo`** います。 親の属性と組み合わせる `SwitchPrefix` `Rule` と、このプロパティはとして実行可能ファイルに渡され  **`/Fo"Debug\"`** ます。 これは、プロパティページの UI で C/c + + のコマンドラインに表示されます。

   その他のプロパティの属性は次のとおりです。

- **`Visible`** : プロパティをプロパティページに表示しないが、ビルド時に使用できるようにする場合は、この属性をに設定し `false` ます。

- **`ReadOnly`** : プロパティページでこのプロパティの値の読み取り専用ビューを指定する場合は、この属性をに設定 `true` します。

- **`IncludeInCommandLine`** : ビルド時に、ツールがプロパティの一部を必要としない場合があります。 `false`特定のプロパティが渡されないようにするには、この属性をに設定します。
