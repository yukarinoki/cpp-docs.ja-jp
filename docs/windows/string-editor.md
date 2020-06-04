---
title: 文字列エディタ (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.string.F1
- vc.editors.string
helpviewer_keywords:
- String editor
- string tables
- string tables [C++], String editor
- string editing
- string editing, string tables
- resource editors [C++], String editor
- strings [C++], editing
- strings [C++], searching
- strings [C++]
- strings [C++], adding to string tables
- string tables [C++], deleting strings
- strings [C++], deleting in string tables
- string tables [C++], adding strings
- strings [C++], moving between files
- resource script files [C++], moving strings
- string editing, moving strings between resources
- String editor [C++], moving strings between files
- resource identifiers, string properties
- string tables [C++], changing strings
- strings [C++], properties
- String editor [C++], changing properties of multiple strings
- string tables [C++], changing caption of multiple strings
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
ms.openlocfilehash: b0fb077752cf1912e07175c68cdc8acfe758b0c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370239"
---
# <a name="string-editor-c"></a>文字列エディタ (C++)

文字列テーブルは、アプリケーションのすべての文字列の ID、値、キャプションの一覧が含まれる Windows リソースです。 たとえば、文字列テーブルにはステータス バーのプロンプトがあります。

アプリケーションの開発中、いくつかの文字列テーブルを使用できます (各言語または条件ごとに 1 つ)。 しかし、実行可能モジュールには、文字列テーブルは 1 つしかありません。 実行中のアプリケーションは、テーブルを異なる DLL に置く場合、複数の文字列テーブルを参照することができます。

文字列テーブルにより、簡単にアプリケーションを異なる言語にローカライズできるようになります。 すべての文字列が文字列テーブルにある場合、ソース コードを変更せずに、文字列 (およびその他のリソース) を変換することにより、アプリケーションをローカライズすることができます。 この状況は、ソース ファイル内のさまざまな文字列を手動で検索して置換するよりも望ましいものです。

> [!NOTE]
> 空の文字列テーブルの作成は許可されていません。 エントリなしの文字列テーブルを作成する場合、そのテーブルはリソース ファイルの保存時に自動的に削除されます。

## <a name="how-to"></a>操作方法

**ストリング・エディター**を使用すると、以下のことが可能になります。

### <a name="to-find-a-string-resource-in-the-string-table"></a>文字列テーブルで文字列リソースを検索するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)で、文字列テーブルのアイコンをダブルクリックして、文字列テーブルを開きます。

1. [**検索と置換**の**編集]** > メニューに移動し、[**検索**] を選択します。

1. [**検索する文字列**] ボックスで、ドロップダウン リストから前の検索文字列を選択するか、検索する文字列のキャプション テキストまたはリソース識別子を入力します。

1. [**検索**] オプションを選択し、[**次を検索]** を選択します。

> [!TIP]
> ファイルの検索時に[正規表現](/visualstudio/ide/using-regular-expressions-in-visual-studio)を使用するには、[**編集]** メニューの [**ファイルから検索**] を使用します。
>
> パターンに一致する正規表現を入力するか、[**検索する文字列**] ボックスの右側にあるボタンを選択して、正規表現の一覧を表示します。 この一覧から式を選択すると、[**検索する文字列**] ボックスの検索文字列として置換されます。
>
> 正規表現を使用する場合は、[**使用: 正規表現**] チェック ボックスがオンになっていることを確認します。

### <a name="to-add-or-delete-a-string-resource"></a>文字列リソースを追加または削除するには

**文字列エディタ**を使用して、文字列テーブルにエントリをすばやく挿入または削除できます。 新しい文字列はテーブルの最後に配置され、次に使用可能な識別子が与えられます。 必要に応じて、[[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で**ID**、**値**、または**キャプション**のプロパティを編集できます。

**文字列エディタ**では、既に使用されている ID を使用しないようにします。 既に使用されている ID を選択すると、**文字列エディタ**によって通知され、一`IDS_STRING58113`般的な一意の ID が割り当てられます。

#### <a name="to-add-a-string-table-entry"></a>文字列テーブルエントリを追加するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)で、文字列テーブルのアイコンをダブルクリックして、文字列テーブルを開きます。

1. 文字列テーブル内を右クリックし、[**新しい文字列**] を選択します。

1. **[文字列エディタ**] で **、[ID]** ドロップダウン リストから**ID**を選択*するか、ID*を直接入力します。

1. 必要に応じて **、値**を編集します。

1. **キャプション**のエントリを入力します。

   > [!NOTE]
   > Windows 文字列テーブルでは、Null 文字列は使用できません。 文字列テーブルに null 文字列のエントリを作成すると、**このテーブルエントリに文字列を入力するように**求めるメッセージが表示されます。

#### <a name="to-delete-a-string-table-entry"></a>文字列テーブルエントリを削除するには

削除するエントリを選択し、次のいずれかの操作を行います。

- メニューの **[削除の編集]** > **Delete**に移動します。

- 削除する文字列を右クリックし、[**削除**] を選択します。

- **Delete**キーを押します。

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>リソース スクリプト ファイル間で文字列を移動するには

1. [両方の .rc ファイルで文字列テーブルを開きます](../windows/how-to-create-a-resource-script-file.md)。

1. 移動する文字列を右クリックし、[**切り取り**] を選択します。

1. ターゲットの**文字列エディタ**ウィンドウにカーソルを置きます。

1. 文字列の移動先となる *.rc*ファイルで、右クリックして [**貼り付け**] を選択します。

> [!NOTE]
> 移動した文字列の**ID**または**Value**が、移動先ファイルの既存の**ID**または**値**と競合する場合、その**ID**または移動した文字列の**値**が変更されます。

### <a name="to-change-the-properties-of-a-string-resource"></a>文字列リソースのプロパティを変更するには

インプレース編集を使用して **、ID**、**値**、および**キャプション**の各プロパティを変更できます。

> [!NOTE]
> 文字列のプロパティは[、[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で編集することもできます。

#### <a name="to-change-a-string-or-its-identifier"></a>文字列またはその識別子を変更するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)で、文字列テーブルのアイコンをダブルクリックして、文字列テーブルを開きます。

1. 編集する文字列を選択し **、[ID]、[****値**]、または **[キャプション]** 列をダブルクリックすると、次のことができます。

   - **[ID]** ボックス**ID**の一覧から*ID*を選択するか、ID を直接入力します。

   - **[値]** 列に別の数値を入力します。

   - **[キャプション]** 列に編集を入力します。

#### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>複数の文字列リソースの caption プロパティを変更するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)で、文字列テーブルのアイコンをダブルクリックして、文字列テーブルを開きます。

1. Ctrl**キーを**押しながら各文字列を選択して、変更する文字列を選択します。

1. [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で、変更するプロパティの新しい値を入力します。

1. [**Enter**] キーを押します。

### <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>文字列リソースに書式または特殊文字を追加するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)で、文字列テーブルのアイコンをダブルクリックして、文字列テーブルを開きます。

1. 変更する文字列を選択します。

1. [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で、下に表示されている標準エスケープ シーケンスのいずれかを **[キャプション]** ボックスのテキストに追加し **、Enter**キーを押します。

   |これを得るために..|これを入力します。|
   |-----------------|---------------|
   | 改行 | \\n |
   | キャリッジ リターン | \\R |
   | タブ | \\t |
   | 円記号 (\\) | \\\\ |
   | ASCII 文字 | \\ddd (8 進数) |
   | アラート(ベル) | \\a |

   > [!NOTE]
   > **文字列エディタ**は、エスケープされた ASCI 文字の完全なセットをサポートしていません。 上記のリストに表示されている場合のみ使用できます。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター文字列](../windows/resource-editors.md)
[Strings](/windows/win32/menurc/strings)<br/>
[文字列の概要](/windows/win32/menurc/about-strings)<br/>
[ウィンドウ レイアウトをカスタマイズする](/visualstudio/ide/customizing-window-layouts-in-visual-studio)
