---
title: 規則セットを使用した実行対象の C++ 規則の指定
ms.date: 07/27/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.native
ms.openlocfilehash: 53e1122cd1aac74401ca956ee24ebcdf79883228
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921907"
---
# <a name="use-rule-sets-to-specify-the-c-rules-to-run"></a>規則セットを使用して実行対象の C++ 規則を指定する

Visual Studio では、コード分析に関連する特定のプロジェクトのニーズに合わせてカスタム *規則セット* を作成および変更できます。 既定の規則セットはに格納され *`%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`* ます。

**Visual Studio 2017 バージョン15.7 以降:** 任意のテキストエディターを使用してカスタム規則セットを作成し、使用しているビルドシステムに関係なく、コマンドラインビルドで適用できます。 詳細については、[`/analyze:ruleset`](../build/reference/analyze-code-analysis.md) を参照してください。

Visual Studio でカスタム C++ 規則セットを作成するには、Visual Studio IDE で C/c + + プロジェクトを開く必要があります。 次に、規則セットエディターで標準規則セットを開き、特定の規則を追加または削除し、必要に応じて、コード分析によって規則に違反したと判断されたときに発生するアクションを変更します。

新規のカスタム規則セットを作成する場合は、新しいファイル名を使用して保存します。 作成したカスタム規則セットは、自動的にプロジェクトに割り当てられます。

## <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>既存の 1 つの規則セットからカスタム規則を作成するには

::: moniker range="<=msvc-150"

1. ソリューションエクスプローラーで、プロジェクトのショートカットメニューを開き、[ **プロパティ** ] を選択します。

1. [ **プロパティページ** ] ダイアログボックスで、[ **構成プロパティ** ] [ > **コード分析** ] > **[全般** ] プロパティページを選択します。

1. [ **規則セット** ] ドロップダウンリストで、次のいずれかの操作を行います。

   - カスタマイズする規則セットを選択します。

     \- または

   - **\<Browse...>** 一覧にない既存の規則セットを指定する場合に選択します。

1. [ **開く** ] を選択すると、ルールセットエディターにルールが表示されます。

::: moniker-end
::: moniker range=">=msvc-160"

1. ソリューションエクスプローラーで、プロジェクトのショートカットメニューを開き、[ **プロパティ** ] を選択します。

1. [ **プロパティページ** ] ダイアログボックスで、[ **構成プロパティ** ] [ > **コード分析** ] [ > **Microsoft** ] プロパティページを選択します。

1. [ **アクティブな規則** ] ドロップダウンリストで、次のいずれかの操作を行います。

   - カスタマイズする規則セットを選択します。

     \- または

   - **\<Browse...>** 一覧にない既存の規則セットを指定する場合に選択します。

1. [ **開く** ] を選択すると、ルールセットエディターにルールが表示されます。

::: moniker-end

## <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>規則セット エディターで規則セットを変更するには

- ルールセットの表示名を変更するには、[ **表示** ] メニューの [ **プロパティウィンドウ** ] をクリックします。 [ **名前** ] ボックスに表示名を入力します。 表示名には、ファイル名と異なる名前を指定できます。

- グループ内のすべての規則をカスタム規則セットに追加するには、グループのチェック ボックスをオンにします。 グループ内のすべての規則を削除するには、チェック ボックスをオフにします。

- 特定の規則をカスタム規則セットに追加するには、その規則のチェック ボックスをオンにします。 規則セットから規則を削除するには、チェック ボックスをオフにします。

- コード分析でルールに違反したときに実行されるアクションを変更するには、ルールの [ **アクション** ] フィールドを選択して、次のいずれかの値を選択します。

     **警告** -警告を生成します。

     **エラー** -エラーが生成されます。

     **Info** -メッセージを生成します。

     **None** -ルールを無効にします。 このアクションは、規則セットから規則を削除するのと同じです。

## <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>規則セット エディターのツール バーを使用して、規則セット エディターに表示されるフィールドのグループ化、フィルター処理、または変更を行うには

- すべてのグループのルールを展開するには、[ **すべて展開** ] を選択します。

- すべてのグループのルールを折りたたむには、[ **すべて折りたたみ** ] を選択します。

- ルールがグループ化されているフィールドを変更するには、[ **グループ化** ] ボックスの一覧からフィールドを選択します。 グループ化されていない規則を表示するには、を選択し **\<None>** ます。

- ルール列のフィールドを追加または削除するには、[ **列のオプション** ] を選択します。

- 現在のソリューションに適用されない規則を非表示にするには、[ **現在のソリューションに適用されない規則を非表示** にする] を選択します。

- エラーアクションが割り当てられているルールの表示と非表示を切り替えるには、[ **コード分析エラーを生成するルールを表示** する] を選択します。

- 警告アクションが割り当てられている規則の表示と非表示を切り替えるには、[ **コード分析警告を生成できる規則を表示** する] を選択します。

- **[なし** ] アクションが割り当てられているルールの表示と非表示を切り替えるには、[無効になっている **ルールを表示** する] を選択します。

- 現在の規則セットに Microsoft の既定の規則セットを追加または削除するには、[ **子規則セットの追加または削除** ] を選択します。

## <a name="to-create-a-rule-set-in-a-text-editor"></a>テキストエディターでルールセットを作成するには

カスタムルールセットは、テキストエディターで作成し、拡張機能のある任意の場所に保存 *`.ruleset`* し、コンパイラオプションを使用してで適用でき [`/analyze:ruleset`](../build/reference/analyze-code-analysis.md) ます。

次の例は、開始点として使用できる基本的な規則セットファイルを示しています。

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description="New rules to apply." ToolsVersion="10.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

## <a name="ruleset-schema"></a>ルールセットスキーマ

次のルールセットスキーマでは、ルールセットファイルの XML スキーマについて説明します。 ルールセットスキーマはに格納されて *`%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Schemas\RuleSet.xsd`* います。 これを使用すると、プログラムによって独自のルールセットを作成したり、カスタムルールセットが正しい形式に準拠しているかどうかを検証したりすることができます。 詳細については、「 [方法: XSD スキーマに基づいて XML ドキュメントを作成](/visualstudio/xml-tools/how-to-create-an-xml-document-based-on-an-xsd-schema)する」を参照してください。

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:annotation>
    <xs:documentation xml:lang="en">
            Visual Studio Code Analysis Rule Set Schema Definition Language.
            Copyright (c) Microsoft Corporation. All rights reserved.
        </xs:documentation>
  </xs:annotation>

  <!-- Every time this file changes, be sure to change the Validate method for the corresponding object in the code -->

  <xs:element name="RuleSet" type="TRuleSet">
  </xs:element>

  <xs:complexType name="TLocalization">
    <xs:all>
      <xs:element name="Name" type="TName" minOccurs="0" maxOccurs="1" />
      <xs:element name="Description" type="TDescription" minOccurs="0" maxOccurs="1" />
    </xs:all>
    <xs:attribute name="ResourceAssembly" type="TNonEmptyString" use="required" />
    <xs:attribute name="ResourceBaseName" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TRuleHintPaths">
    <xs:sequence>
      <xs:element name="Path" type="TNonEmptyString" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>
  
  <xs:complexType name="TName">
    <xs:attribute name="Resource" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TDescription">
    <xs:attribute name="Resource" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TInclude">
    <xs:attribute name="Path" type="TNonEmptyString" use="required" />
    <xs:attribute name="Action" type="TIncludeAction" use="required" />
  </xs:complexType>

  <xs:complexType name="TIncludeAll">
    <xs:attribute name="Action" type="TIncludeAllAction" use="required" />
  </xs:complexType>

  <xs:complexType name="TRule">
    <xs:attribute name="Id" type="TNonEmptyString" use="required" />
    <xs:attribute name="Action" type="TRuleAction" use="required" />
  </xs:complexType>

  <xs:complexType name="TRules">
    <xs:sequence>
      <xs:element name="Rule" type="TRule" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="AnalyzerId" type="TNonEmptyString" use="required" />
    <xs:attribute name="RuleNamespace" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TRuleSet">
    <xs:sequence minOccurs="0" maxOccurs="1">
      <xs:element name="Localization" type="TLocalization" minOccurs="0" maxOccurs="1" />
      <xs:element name="RuleHintPaths" type="TRuleHintPaths" minOccurs="0" maxOccurs="1" />
      <xs:element name="IncludeAll" type="TIncludeAll" minOccurs="0" maxOccurs="1" />
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Include" type="TInclude" minOccurs="0" maxOccurs="unbounded" />
        <xs:element name="Rules" type="TRules" minOccurs="0" maxOccurs="unbounded">
          <xs:unique name="UniqueRuleName">
            <xs:selector xpath="Rule" />
            <xs:field xpath="@Id" />
          </xs:unique>
        </xs:element>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="Name" type="TNonEmptyString" use="required" />
    <xs:attribute name="Description" type="xs:string" use="optional" />
    <xs:attribute name="ToolsVersion" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:simpleType name="TRuleAction">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Error"/>
      <xs:enumeration value="Warning"/>
      <xs:enumeration value="Info"/>
      <xs:enumeration value="Hidden"/>
      <xs:enumeration value="None"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TIncludeAction">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Error"/>
      <xs:enumeration value="Warning"/>
      <xs:enumeration value="Info"/>
      <xs:enumeration value="Hidden"/>
      <xs:enumeration value="None"/>
      <xs:enumeration value="Default"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TIncludeAllAction">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Error"/>
      <xs:enumeration value="Warning"/>
      <xs:enumeration value="Info"/>
      <xs:enumeration value="Hidden"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TNonEmptyString">
    <xs:restriction base="xs:string">
      <xs:minLength value="1" />
    </xs:restriction>
  </xs:simpleType>
  
</xs:schema>

```

スキーマ要素の詳細:

| Schema 要素 | Description |
|--------------------|--------------|
| `TLocalization` | ルールセットファイルの名前、ルールセットファイルの説明、ローカライズされたリソースを含むリソースアセンブリの名前、ローカライズされたリソースのベース名など、ローカライズ情報 |
| `TRuleHintPaths` | ルールセットファイルを検索するためのヒントとして使用されるファイルパス |
| `TName` | 現在のルールセットファイルの名前 |
| `TDescription` | 現在のルールセットファイルの説明 |
| `TInclude` | ルールアクションを含む含まれるルールセットへのパス |
| `TIncludeAll` | すべてのルールのルールアクション |
| `TRule` | ルールのアクションを含むルール ID |
| `TRules` | 1つまたは複数のルールのコレクション |
| `TRuleSet` | ローカライズ情報、ルールヒントパス、すべての情報を含む規則セットファイル形式 (情報、規則情報、名前、説明、ツールのバージョン情報を含む) |
| `TRuleAction` | エラー、警告、情報、非表示、またはなしなどのルールアクションを説明する列挙です。 |
| `TIncludeAction` | エラー、警告、情報、hidden、none、default などのルールアクションを説明する列挙です。 |
| `TIncludeAllAction` | エラー、警告、情報、非表示などのルールアクションを説明する列挙です。 |

ルールセットの例については、「」を参照して、 [テキストエディターで規則セットを作成する](#to-create-a-rule-set-in-a-text-editor)か、に格納されている既定の規則セットのいずれかを作成し `%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets` ます。
