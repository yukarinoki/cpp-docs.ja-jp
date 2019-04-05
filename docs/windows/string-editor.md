---
title: 文字列エディター (C++)
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
ms.openlocfilehash: 47d5835356863383b32baffc4475e01a652e9856
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037186"
---
# <a name="string-editor-c"></a>文字列エディター (C++)

文字列テーブルは、アプリケーションのすべての文字列の ID、値、キャプションの一覧が含まれる Windows リソースです。 たとえば、文字列テーブルにはステータス バーのプロンプトがあります。

アプリケーションの開発中、いくつかの文字列テーブルを使用できます (各言語または条件ごとに 1 つ)。 しかし、実行可能モジュールには、文字列テーブルは 1 つしかありません。 実行中のアプリケーションは、テーブルを異なる DLL に置く場合、複数の文字列テーブルを参照することができます。

文字列テーブルにより、簡単にアプリケーションを異なる言語にローカライズできるようになります。 すべての文字列が文字列テーブルにある場合、ソース コードを変更せずに、文字列 (およびその他のリソース) を変換することにより、アプリケーションをローカライズすることができます。 このような状況が手動での検索とソース ファイル内のさまざまな文字列を置換するよりも高くなります。

> [!NOTE]
> Windows では、空の文字列テーブルの作成を許可しません。 エントリなしの文字列テーブルを作成する場合、そのテーブルはリソース ファイルの保存時に自動的に削除されます。

## <a name="how-to"></a>方法

**文字列エディター**できます。

### <a name="to-find-a-string-resource-in-the-string-table"></a>文字列テーブル内の文字列リソースを検索するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)します。

1. メニューに移動して**編集** > **検索し、置換**選択**検索**します。

1. **検索**ボックス、ドロップダウン リストから、以前の検索文字列を選択または検索する文字列のキャプション テキストまたはリソース識別子を入力します。

1. いずれかの選択、**検索**オプションと選択**次を検索**します。

> [!TIP]
> 使用する[正規](/visualstudio/ide/using-regular-expressions-in-visual-studio)ファイルを検索するときに使用して、**ファイル内の検索**コマンドを**編集**メニュー。
>
> 正規表現パターンに一致またはの右側にボタンを選択する、**検索**検索の正規表現の一覧を表示するボックスです。 この一覧から式を選択すると、検索文字列として設定されます、**検索**ボックス。
>
> 正規表現を使用する場合は必ず、**を使用します。正規表現** チェック ボックスをオンします。

### <a name="to-add-or-delete-a-string-resource"></a>追加または文字列リソースを削除するには

すぐに挿入したり、文字列を使用してテーブルにエントリを削除できます、**文字列エディター**します。 新しい文字列は、テーブルの末尾に配置され、[次へ] の使用可能な識別子が与えられます。 編集することができます、 **ID**、**値**、または**キャプション**プロパティで、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)に応じて。

**文字列エディター**は既に使用されている ID を使用しないようにします。 ID を既に使用して、選択した場合、**文字列エディター**は通知し、たとえば一般的な一意の ID を割り当てる`IDS_STRING58113`します。

#### <a name="to-add-a-string-table-entry"></a>ストリング テーブルのエントリを追加するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)します。

1. 文字列テーブル内で右クリックし、**新しい文字列**します。

1. **文字列エディター**を選択、 **ID**から、 **ID**ドロップダウン リストまたは型、 *ID*は直接します。

1. 編集、**値**、必要な場合。

1. エントリを入力、**キャプション**します。

   > [!NOTE]
   > Null 文字列は、Windows の文字列テーブルに許可されていません。 よう求めるメッセージが表示されます、null 文字列である文字列テーブルにエントリを作成する場合**このテーブルのエントリの文字列を入力してください**します。

#### <a name="to-delete-a-string-table-entry"></a>文字列テーブルのエントリを削除するには

削除し、次のいずれかを実行するエントリを選択します。

- メニューに移動して**編集** > **削除**します。

- 削除する文字列を右クリックして**削除**します。

- キーを押して、**削除**キー。

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>文字列を別の 1 つのリソース スクリプト ファイルに移動するには

1. [両方の .rc ファイルで文字列テーブルを開く](../windows/how-to-create-a-resource-script-file.md)します。

1. を選択する文字列を右クリックして**切り取り**します。

1. ターゲットにカーソルを置き**文字列エディター**ウィンドウ。

1. *.Rc*文字列の移動を右クリックして選択するファイル**貼り付け**します。

> [!NOTE]
> 場合、 **ID**または**値**既存の文字列の移動の競合の**ID**または**値**変換先のファイル、そのいずれかの**ID**または**値**の移動先の文字列を変更します。

### <a name="to-change-the-properties-of-a-string-resource"></a>文字列リソースのプロパティを変更するには

インプレース編集を使用する変更、 **ID**、**値**、および**キャプション**プロパティ。

> [!NOTE]
>  文字列のプロパティを編集することも、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

#### <a name="to-change-a-string-or-its-identifier"></a>文字列または識別子を変更するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)します。

1. ダブルクリックして編集する文字列を選択、 **ID**、**値**、または**キャプション**列、しすることができます。

   - 選択、 **ID**から、 **ID**ドロップダウン リスト、または型、 *ID*は直接します。

   - 別の番号を入力、**値**列。

   - 入力時に編集、**キャプション**列。

#### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>複数の文字列リソースの caption プロパティを変更するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)します。

1. 押しながら変更する文字列を選択、 **Ctrl**キーの 1 つを選択するとします。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、変更するプロパティの新しい値を入力します。

1. **Enter** キーを押します。

### <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>文字列リソースへの書式設定や特殊文字を追加するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)します。

1. 変更する文字列を選択します。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、内のテキストには以下の標準のエスケープ シーケンスのいずれかの追加、**キャプション**ボックス キーを押します**Enter**します。

   |これを取得しています.|これを入力してください.|
   |-----------------|---------------|
   | 改行 | \\n |
   | キャリッジ リターン | \\r |
   | タブ | \\t |
   | 円記号 (\\) | \\\\ |
   | ASCII 文字 | \\ddd (8 進表記) |
   | 警告 (ベル) | \\a |

   > [!NOTE]
   > **文字列エディター** ASCI のエスケープ文字の完全なセットをサポートしていません。 上記のリストにのみ使用できます。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)
<!--
[Strings](https://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)<br/>
[About Strings](/windows/desktop/menurc/about-strings)<br/>
[Customizing window layouts](/visualstudio/ide/customizing-window-layouts-in-visual-studio)-->