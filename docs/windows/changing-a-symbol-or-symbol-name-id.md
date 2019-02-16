---
title: '方法: シンボルを管理します。'
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.changing
- vc.editors.symbol.restrictions.name
- vc.editors.symbol.changing.value
- vc.editors.symbol.restrictions.value
- vc.editors.symbol.changing.header
- vc.editors.symbol.changing.unassigned
- vc.editors.symbol.shared.calculated
helpviewer_keywords:
- symbol names
- symbols [C++], names
- restrictions, symbol names
- numeric values
- symbols [C++], numeric values
- numeric values, changing symbols
- symbols [C++], value restrictions
- restrictions, symbol values
- resource files [C++], multiple
- Resource Includes dialog box [C++]
- symbol header files [C++], changing names
- symbols [C++], symbol header files
- Resource.h
- symbols [C++], unassigned
- Change Symbol dialog box [C++]
- unassigned symbols
- symbols [C++], deleting
- symbols [C++], read-only
- symbols [C++], shared
- symbols [C++], calculated
- read-only symbols
- symbol directives
- calculated symbols
- shared symbols
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
ms.openlocfilehash: 4f1c44e8fc2ae34ddcb65ec23ca8d98e11d50ec0
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320589"
---
# <a name="how-to-manage-symbols"></a>方法: シンボルを管理します。

リソースまたはリソース オブジェクトを新規作成すると、IDD_DIALOG1 などの既定のシンボル名が開発環境によって割り当てられます。 使用することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)を既定のシンボル名を変更する、またはリソースに既に関連付けられている任意のシンボルの名前を変更します。

1 つのリソースに関連付けられているシンボルを使用することも、**プロパティ**シンボル値を変更するウィンドウ。 使用することができます、[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)リソースに割り当てられていないシンボルの値を変更します。

通常、すべてのシンボルが定義に保存`Resource.h`します。 ただし、同じディレクトリ内の複数のリソース ファイルを使用する場合などに、このインクルード ファイル名の変更が必要になることがあります。

> [!NOTE]
> 場合は、プロジェクトに .rc ファイル含まれていないを参照してください。[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)です。

## <a name="symbol-name-restrictions"></a>シンボル名の制限

シンボル名に関する制限は、次のとおりです。

- すべて[シンボル](../windows/symbols-resource-identifiers.md)アプリケーションのスコープ内で一意である必要があります。 そうすることで、ヘッダー ファイルでのシンボル定義の競合を避けることができます。

- シンボル名で有効な文字は、A ～ Z、a ～ z、0 ～ 9、およびアンダー スコア (_) です。

- シンボル名を数字で始めることはできませんし、247 文字に制限されています。

- シンボル名は、スペースを含めることはできません。

- シンボル名は大文字小文字が区別されませんが、最初のシンボル定義の大文字と小文字は保持されます。 シンボルを定義するヘッダー ファイルは、リソース ファイルで定義されているリソースを参照するために、リソース コンパイラ/エディターと C++ プログラムの両方で使用されます。 大文字か小文字かだけが異なる 2 つのシンボル名の場合、C++ プログラムは 2 つの個別のシンボルと見なしますが、リソース コンパイラ/エディターはどちらの名前も 1 つのシンボルを指していると見なします。

   > [!NOTE]
   > 以下に概要が示されている標準シンボル名スキーム (ID*_[キーワード]) に従わず、シンボル名がリソース スクリプト コンパイラで使用されているキーワードと同じである場合、リソース スクリプト ファイルをビルドしようとすると、ランダムであるように見えるエラーが発生し、診断が困難になります。 これを回避するには、標準名前付けスキームに従います。

シンボル名には説明的なプレフィックスがあり、対象となるリソースやオブジェクトの種類を示します。 これらの説明的なプレフィックスは、テキストを組み合わせた ID で始まります。 Microsoft Foundation Class (MFC) ライブラリでは、以下の表に示されているシンボルの名前付け規則が使用されています。

|Category|プレフィックス|使用|
|--------------|------------|---------|
|リソース|IDR_ IDD_ IDC_ IDI_ IDB_|アクセラレータまたはメニュー (および関連付けられているかカスタムのリソース) ダイアログ ボックス カーソル アイコン ビットマップ|
|メニュー項目|ID_|メニュー項目|
|コマンド|ID_|コマンド|
|コントロールと子ウィンドウ|IDC_|コントロール|
|文字列|IDS_|文字列テーブル内の文字列|
|MFC|AFX_|定義済みの MFC シンボル用に予約されています|

### <a name="to-change-a-symbol-name-id"></a>シンボル名 (ID) を変更するには

1. [リソース ビュー](../windows/resource-view-window.md)リソースを選択します。

1. **プロパティ**ウィンドウで、新しいシンボル名を入力するか既存のシンボルの一覧から選択、 **ID**ボックス。

   新しいシンボル名を入力する場合、値が割り当てに自動的にします。

使用することができます、[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)リソースに割り当てられていないシンボルの名前を変更します。

## <a name="symbol-value-restrictions"></a>シンボル値の制限

シンボル値には、#define プリプロセッサ ディレクティブに対して通常の方法で表現される整数を指定できます。 シンボル値の例をいくつか次に示します。

```
18
4001
0x0012
-3456
```

リソース (アクセラレータ、ビットマップ、カーソル、ダイアログ ボックス、アイコン、メニュー、文字列テーブル、およびバージョン情報) のシンボル値は、0 ～ 32,767 の範囲の 10 進値である必要があります (16 進値は使用できません)。 一部のリソース (ダイアログ ボックスのコントロールや文字列テーブルの個々の文字列など) のシンボル値には、0 ～ 65,534 または、-32,768 ～ 32,767 の範囲の値を使用できます。

リソース シンボルは、16 ビットの数値です。 符号付きまたは符号なしとして入力することがあります、符号なし整数として内部的には、使用しているただし。 したがって、負の値は対応する正の値にキャストされます。

シンボル値のいくつかの制限を次に示します。

- Visual Studio 開発環境と MFC では、特殊な目的でいくつかの数値の範囲を使用しています。 最上位ビットが設定されたすべての数値 (符号に応じて -32,768 ～ -1 または 32,768 ～ 65,534) は MFC によって予約されています。

- その他の記号文字列を使用してシンボル値を定義することはできません。 たとえば、次のシンボル定義はサポートされていません。

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- プリプロセッサ マクロは、値の定義として引数を使用できません。 例:

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

   内容に関係なく、有効な式のない`ID`コンパイル時に評価されます。

- アプリケーションには、式を使用して定義されたシンボルを含む既存のファイルが存在する可能性があります。 読み取り専用のシンボルとしてシンボルを含める方法の詳細については、次を参照してください。[共有を使用する (読み取り専用) または計算型シンボル](../windows/including-shared-read-only-or-calculated-symbols.md)します。

数値の範囲の詳細については、次を参照してください[TN023:。標準 MFC リソース](../mfc/tn023-standard-mfc-resources.md)します。

### <a name="to-change-a-symbol-value"></a>シンボル値を変更するには

1. [リソース ビュー](../windows/resource-view-window.md)リソースを選択します。

1. **プロパティ**ウィンドウで、型、シンボル名の後に等号 (=)、整数の**ID**ボックスで、たとえば。

    ```
    IDC_EDITNAME=5100
    ```

新しい値は、次回のプロジェクトの保存時に、シンボル ヘッダー ファイルに格納されます。 [ID] ボックスでは、シンボル名だけが表示されます。等号と値が検証している後に表示されません。

## <a name="change-or-delete-symbols"></a>変更または削除記号

[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)、編集またはリソースまたはオブジェクトに既に割り当てられていない既存のシンボルを削除することができます。

### <a name="to-change-an-unassigned-symbol"></a>未使用のシンボルを変更するには

1. **名前**ボックスで未使用のシンボルを選択し、選択**変更**します。

1. シンボルの名前またはで用意されているボックス内の値を編集、**シンボルの変更** ダイアログ ボックス。

   > [!NOTE]
   > シンボルの変更を*は*リソースまたはオブジェクトに割り当てられている、リソース エディターを使用する必要がありますまたは**プロパティ**ウィンドウ。

### <a name="to-delete-an-unassigned-unused-symbol"></a>割り当てられていない (使用されていない) シンボルを削除するには

[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)、削除、および選択する記号を選択して**削除**します。

   > [!NOTE]
   > リソース ファイル内の未使用のシンボルを削除する前に、プログラム内の他の場所や、コンパイル時に含められるリソース ファイルで使用されていないことを確認してください。

## <a name="include-symbols"></a>シンボルを含める

別のアプリケーションによって作成されたリソース ファイルを開発環境に初めて読み取るとき、インクルードされるすべてのヘッダー ファイルが読み取り専用とマークされます。 使用することができますが、 [] ダイアログ ボックスの [リソース インクルード](../windows/resource-includes-dialog-box.md)追加の読み取り専用シンボル ヘッダー ファイルを追加します。

読み取り専用のシンボル定義を使用する状況の 1 つに、複数のプロジェクト間でシンボル ファイルを共有する場合があります。

インクルードされるシンボル ファイルは、単純な整数の代わりに式を使用してシンボル値を定義するシンボル定義を含む既存のリソースがあるときに使用することもできます。 例:

```cpp
#define   IDC_CONTROL1 2100
#define   IDC_CONTROL2 (IDC_CONTROL1+1)
```

計算型シンボルは、次の条件が満たされる場合に環境によって適切に解釈されます。

- 計算型シンボルが読み取り専用シンボル ファイルに配置されている。

- これらの計算型シンボルが既に割り当てられているリソースがリソース ファイルに含まれている。

- 数値式が求められる。

> [!NOTE]
> 文字列または数値式が求められる場合、式は評価されません。

### <a name="to-include-shared-read-only-symbols-in-your-resource-file"></a>共有 (読み取り専用) シンボルをリソース ファイルに含めるには

1. [リソース ビュー](../windows/resource-view-window.md)を .rc ファイルを右クリックして[リソース ファイルのインクルード](../windows/resource-includes-dialog-box.md)ショートカット メニューから。

1. **読み取り専用シンボル ディレクティブ**ボックスで使用して、`#include`コンパイラ ディレクティブをファイルの読み取り専用のシンボルを格納する場所を指定します。

   ファイルを呼び出さないでください`Resource.h`、通常、メイン シンボル ヘッダー ファイルで使用されるファイル名があるためです。

   > [!NOTE]
   > **重要な**入力したとおりにリソース ファイルに含まれるが読み取り専用シンボル ディレクティブ ボックスに入力します。 入力ミスや構文エラーがないことを確認してください。

   使用して、**読み取り専用シンボル ディレクティブ**シンボルの定義のみを含むファイルをインクルードするボックスです。 リソース定義が含まれていませんそれ以外の場合、重複するリソース定義は、ファイルを保存するときに作成されます。

1. 指定したファイルにシンボルを配置します。

   この方法でインクルード ファイル内のシンボルは、リソース ファイルを開くたびに評価されますが、ファイルを保存するときに、ディスク上に置き換えはありません。

1. **[OK]** を選択します。

### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>リソースのシンボル用のヘッダー ファイルの名前を変更するには

1. [リソース ビュー](../windows/resource-view-window.md)を .rc ファイルを右クリックして[リソース ファイルのインクルード](../windows/resource-includes-dialog-box.md)ショートカット メニューから。

1. **シンボル ヘッダー ファイル**ボックスに、インクルード ファイルの新しい名前を入力します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース識別子 (シンボル)](../windows/symbols-resource-identifiers.md)<br/>
[シンボルを作成します。](../windows/creating-new-symbols.md)<br/>
[定義済みシンボル ID](../windows/predefined-symbol-ids.md)<br/>