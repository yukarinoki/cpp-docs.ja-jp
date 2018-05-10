---
title: プロパティ ページ XML ルール ファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/27/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property page XML files
ms.assetid: dd9d9734-4387-4098-8ba6-85b93507731d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fcee2c416fba6a959785826781aefd96b0d06d75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="property-page-xml-rule-files"></a>プロパティ ページ XML ルール ファイル
IDE でプロジェクト プロパティ ページには、VCTargets フォルダー内の XML ファイルで構成されます。 正確なパスは、Visual Studio のどのについて説明がインストールされ、製品の言語に依存します。 Visual Studio 2017 年 1 Enterprise Edition で英語で、パスは`%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`します。 XML ファイルは、ルール、カテゴリ、および個々 のプロパティ、データ型、既定値の名前、および表示するのにはどのようにについて説明します。 IDE でプロパティを設定すると、新しい値は、プロジェクト ファイルに格納されます。

のみのシナリオでこれらのファイルと、Visual Studio IDE の内部動作が (a) するかを理解する必要がありますが、カスタム プロパティ ページを作成するか、(b)、Visual Studio IDE を介して以外の方法によって、プロジェクトのプロパティをカスタマイズします。 

最初に、プロジェクトのプロパティ ページを開いてみましょう (でプロジェクト ノードを右クリックして**ソリューション エクスプ ローラー**プロパティを選択)。
   
![Visual C プロジェクトのプロパティ](media/cpp-property-page-2017.png)

各ノードの下**構成プロパティ**ルールと呼びます。 ルールが、コンパイラと同様に 1 つのツールを表すことがありますが、プロパティを実行して、いくつかの出力が生成される可能性がありますが持っているものを指します一般。 各規則は VCTargets フォルダー内の xml ファイルから設定されます。 たとえば前に、示した C/C++ 規則は 'cl.xml' によって設定されます。

上記のように、各ルールのカテゴリに分類されるプロパティのセットがします。 各サブ ノード ルールは、カテゴリを表します。 たとえば、C と C++ での最適化ノードには、コンパイラ ツールの最適化に関連するすべてのプロパティが含まれています。 プロパティとその値自体は、右側のウィンドウのグリッド形式で表示されます。

メモ帳または任意の XML エディター (下のスナップショットを参照) で cl.xml を開くことができます。 その下にある追加のメタデータと共に、UI に表示されるように定義されたプロパティの同じリストを持つ規則をという名前のルート ノードが表示されます。

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
...
``` 

プロパティ ページの UI の 構成プロパティは、各ノードに対応する 1 つの XML ファイルがあります。 追加するか、ui を含むまたはプロジェクトに対応する XML ファイルの場所を削除して規則を削除します。 たとえば、Microsoft.CppBuild.targets (1 つのレベルを 1033 フォルダーにある) が cl.xml が含まれます次に示します。

```xml  
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>

``` 
すべてのデータの cl.xml を除外する場合は最終的に次のスケルトン。
```xml  
<?xml version="1.0" encoding="utf-8"?>
<Rule>
  <Rule.DataSource />
  <Rule.Categories>
    <Category />
        ...
  </Rule.Categories>
  <BoolProperty />
  <EnumProperty />
  <IntProperty />
  <StringProperty />
  <StringListProperty />
</Rule>
``` 

次のセクションでは、各主要な要素とそれらに関連付けることができるメタデータの一部について説明します。

1. **ルール:** ルールは、xml ファイルのルート ノードでは、通常、以外の多数の属性を持つことができます。

```xml    
<Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
          xmlns="http://schemas.microsoft.com/build/2009/properties"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.DisplayName>
    <sys:String>C/C++</sys:String>
  </Rule.DisplayName>
```  

   a.  **[名前]:** は Name 属性が、ルールの id。 すべてのプロパティ ページ xml ファイル、プロジェクト間で一意である必要があります。

   b.  **ページ テンプレート:** UI テンプレートのコレクションから選択する UI でこの属性の値を使用します。 「ツール」テンプレートは、標準のグリッド形式でプロパティを表示します。 その他の組み込みの値のこの属性は「デバッガー」と「汎用」です。 参照して、[デバッグ] ノードと [全般] ノードは、それぞれ、これらの値を指定することに起因する UI の形式を確認します。 「デバッガー」ページのテンプレートの UI では、ドロップダウン ボックスを使用して「汎用」テンプレートは、複数のカテゴリ下のサブノード ルールではなく 1 つのページのすべてのさまざまなプロパティのカテゴリが表示されます、別のデバッガーのプロパティの間で切り替えるノードです。 この属性はだけ、提案を送信する UI です。xml ファイルは、独立した UI に設計されています。 さまざまな UI は、この属性を使用して、さまざまな目的の可能性があります。

  c. **SwitchPrefix:** これは、スイッチをコマンドラインで使用されるプレフィックス。 値「/」は、スイッチ、/ZI、/nologo、/W3 などのように見えることになります。

  d. **順序:** これは、この規則が、システムの他のすべてのルールと比較した相対的な場所に見込み UI クライアントに提案します。

  e. **xmlns:** これは、標準的な XAML 要素。 表示された 3 つの名前空間を表示できます。 これらは、XAML の逆シリアル化用の名前空間に対応してクラス、XAML スキーマとシステム名前空間、それぞれします。

  f. **DisplayName:** ルール ノードのプロパティ ページの UI に表示される名前です。 この値はローカライズされます。 作成した DisplayName (名前や SwitchPrefix) などの属性としてではなく、ルールの子要素として内部のローカライズのためツールの要件です。 XAML の観点から、両方は等価です。 そのため、することができますだけに属性を整理したり、現状有姿のままにします。

  g. **データ ソース:** プロパティの値には元の場所からの読み取りと書き込み、およびそのグループ化 (下記参照)、プロジェクト システムに通知する非常に重要なプロパティです。 Cl.xml、これらの値は。

```xml  
       <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
```  
   - `Persistence="ProjectFile` ルールのすべてのプロパティは、プロジェクト ファイルに書き込むかプロジェクト システムか (これによってノードが使用されて、プロパティ ページを生成する) プロパティ シート ファイルを示します。 他の考えられる値は、.user ファイルに値を書き込むの「すぎたり」です。

   - `ItemType="ClCompile"` プロパティは ItemDefinition メタデータまたは (後者のプロパティ ページがソリューション エクスプ ローラーでファイルのノードから生成される場合にのみ) の項目メタデータとして格納されることを示すは、この項目の種類。 このフィールドが設定されていない場合、このプロパティは、PropertyGroup の共通のプロパティとして書き込まれます。

   - `Label=""` プロパティとして書き込まれるときに、ことを示します`ItemDefinition`メタデータ、itemdefinitiongroup 内の親のラベルは空になります (MSBuild のすべての要素は、ラベルを持つことができます)。 Visual Studio 2017 では、ラベルの付いたグループを使用して、.vcxproj プロジェクト ファイルを移動します。 ほとんどの規則のプロパティを含むグループにラベルとして空の文字列があることに注意してください。

   - `HasConfigurationCondition="true"` 値に条件を構成 (条件は、親グループまたは値そのものに付けでした) 現在のプロジェクト構成に対してのみ有効になるようにプロジェクト システムに指示します。 たとえば、プロジェクト ノードをプロパティ ページを開くし、プロパティの値を設定**警告をエラーとして扱う****構成プロパティ > C と C++ の全般**"Yes"にします。 次の値は、プロジェクト ファイルに書き込まれます。 Itemdefinitiongroup 内の親にアタッチされている構成の条件に注意してください。

```xml  
     <ItemDefinitionGroup Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">
        <ClCompile>
           <TreatWarningAsError>true</TreatWarningAsError>
        </ClCompile>
     </ItemDefinitionGroup>
 ```
   Stdafx.cpp などの特定のファイルのプロパティ ページでこの値を設定した場合は、プロパティの値を次に示すように、プロジェクト ファイル、stdafx.cpp アイテムの下書き込まれます。 構成の条件はメタデータ自体に直接接続されて方法に注意してください。

 ```xml  
<ItemGroup>
   <ClCompile Include="stdafx.cpp">
      <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
   </ClCompile>
</ItemGroup>
 ```
   別の属性の**データソース**が上記以外の**PersistedName**です。 この属性を使用して、別の名前を使用してプロジェクト ファイルでプロパティを表すことができます。 既定ではこの属性は、プロパティに設定**名前**です。 

   個々 のプロパティは、その親のルールのデータ ソースを上書きできます。 その場合は、そのプロパティの値の場所はルールでは、その他のプロパティと異なるになります。

   h. ここで示されていない、規則の説明、SupportsFileBatching などの他の属性があります。 ルールまたはその他の要素に適用される属性の完全なセットは、これらの型のドキュメントを参照することにより取得できます。 または、内の型のパブリック プロパティを調べることができます、`Microsoft.Build.Framework.XamlTypes`で名前空間、`Microsoft.Build.Framework .dll`アセンブリ。

   i. **DisplayName**、**ページ テンプレート**、および**順序**これに格納されている UI 関連のプロパティはそれ以外の場合、UI に依存しないデータ モデル。 これらのプロパティはプロパティ ページを表示するために使用できる UI で使用される、ほぼ確実です。 **DisplayName**と**説明**xml ファイル内のほとんどすべての要素に組み込まれている 2 つのプロパティです。 これらはローカライズされている 2 つのプロパティおよび (それらの文字列のローカライズについては、以降の投稿)。

2.  **カテゴリ:** ルールは、複数のカテゴリを持つことができます。 Xml ファイルでカテゴリが表示される順序は、同じ順序で、カテゴリを表示するには、UI に提案です。 たとえば、UI に表示される、C/C++ ノードの下のカテゴリの order – [全般]、最適化、プリプロセッサをしています.  – でその cl.xml と同じです。 サンプル カテゴリは、次のようになります。

```xml  
 <Category Name="Optimization">
    <Category.DisplayName>
        <sys:String>Optimization</sys:String>
    </Category.DisplayName>
 </Category>
```
上記のスニペットで示す、**名前**と**DisplayName**する前に説明されている属性です。 もう一度、その他の属性がある、**カテゴリ**を持つことができます上は使用されません。 わかるそれらについてまたは ildasm.exe を使用してアセンブリを調べることで、ドキュメントを読みです。

3. **プロパティ:** これは、xml ファイルの主要な要素であり、このルールのすべてのプロパティの一覧が含まれています。 各プロパティには、上記の XAML スケルトンで表示される 5 つの可能な型のいずれかを指定できます。 もちろんは、ファイルでそれらの型の一部のみことができます。 プロパティは、表現力豊かな説明することができる属性数にします。 説明のみ、 **StringProperty**ここです。 残りの部分は、非常に似ています。

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
スニペット内の属性のほとんどは、前に記載されています。 新しいものとは、サブタイプ、カテゴリおよびスイッチです。

   a.  **サブタイプ**に対してのみ使用可能な属性は、 **StringProperty**と**StringListProperty**; コンテキスト情報を提供します。 たとえば、"file"の値は、ファイルのパスを表すことを示します。 このようなコンテキスト情報は、ユーザーがファイルの視覚的に選択できるプロパティのエディターとして Windows エクスプ ローラーを提供することで、編集エクスペリエンスを強化するために使用されます。

   b.  **カテゴリ:** これにより、このプロパティが該当するカテゴリが宣言されます。 下でこのプロパティを検索しようとしています、**出力ファイル**UI のカテゴリ。

   c. **スイッチ:** とツールを表しており、ルール – コンパイラ ツールなど – ここで、ルールのほとんどのプロパティに渡されるスイッチとしてツール実行可能ビルド時にします。 この属性の値では、使用されるリテラルのスイッチを示します。 上記のプロパティは、そのスイッチをする必要がありますを指定します**Fo**です。 組み合わせて、 **SwitchPrefix**親ルールでは、このプロパティの属性が、実行可能ファイルとしてに渡される **/Fo"デバッグ\"** (C/C++ のプロパティ ページの UI でのコマンド ラインで表示)。

   その他のプロパティの属性は次のとおりです。

   d. **Visible:** 、何らかの理由たくないかどうか、プロパティに、プロパティ ページ (ただし、ビルド時にまだ使用可能) に表示、この属性を false に設定します。

   e. **読み取り専用:** プロパティ ページで、このプロパティの値の読み取り専用ビューを提供する場合は、この属性を true に設定します。

   f. **IncludeInCommandLine:** いくつかのプロパティは、ビルド時に、ツールに渡される必要はありません。 この属性を false に設定すると、渡されるからできなくなります。


