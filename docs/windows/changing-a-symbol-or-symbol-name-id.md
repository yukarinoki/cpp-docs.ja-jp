---
title: シンボルの変更
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing
- vc.editors.symbol.restrictions.name
- vc.editors.symbol.changing.value
- vc.editors.symbol.restrictions.value
- vc.editors.symbol.changing.header
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
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
ms.openlocfilehash: 7d2890c2d2c05f1ee0309446dfe2de9917f85707
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763987"
---
# <a name="changing-a-symbol"></a>シンボルの変更

リソースまたはリソース オブジェクトを新規作成すると、IDD_DIALOG1 などの既定のシンボル名が開発環境によって割り当てられます。 使用することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)を既定のシンボル名を変更する、またはリソースに既に関連付けられている任意のシンボルの名前を変更します。

1 つのリソースに関連付けられているシンボルを使用することも、**プロパティ**シンボル値を変更するウィンドウ。 使用することができます、[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)リソースに割り当てられていないシンボルの値を変更します。 詳細については、次を参照してください。[未使用のシンボルを変更する](../windows/changing-unassigned-symbols.md)します。

通常、すべてのシンボルが定義に保存`Resource.h`します。 ただし、同じディレクトリ内の複数のリソース ファイルを使用する場合などに、このインクルード ファイル名の変更が必要になることがあります。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="to-change-a-resources-symbol-name-id"></a>リソースのシンボル名 (ID) を変更するには

1. [リソース ビュー](../windows/resource-view-window.md)リソースを選択します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. **プロパティ**ウィンドウで、新しいシンボル名を入力するか既存のシンボルの一覧から選択、 **ID**ボックス。

   新しいシンボル名を入力すると、値が自動的に割り当てられます。

使用することができます、[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)リソースに割り当てられていないシンボルの名前を変更します。 詳細については、次を参照してください。[未使用のシンボルを変更する](../windows/changing-unassigned-symbols.md)します。

### <a name="symbol-name-restrictions"></a>シンボル名の制限

シンボル名に関する制限は、次のとおりです。

- すべて[シンボル](../windows/symbols-resource-identifiers.md)アプリケーションのスコープ内で一意である必要があります。 そうすることで、ヘッダー ファイルでのシンボル定義の競合を避けることができます。

- シンボル名で有効な文字は、A ～ Z、a ～ z、0 ～ 9、およびアンダー スコア (_) です。

- シンボル名を数字で始めることはできず、247 文字までに制限されます。

- シンボル名にスペースを使用することはできません。

- シンボル名で大文字と小文字は区別されませんが、最初のシンボル定義での大文字と小文字の区別は維持されます。 シンボルを定義するヘッダー ファイルは、リソース ファイルで定義されているリソースを参照するために、リソース コンパイラ/エディターと C++ プログラムの両方で使用されます。 大文字か小文字かだけが異なる 2 つのシンボル名の場合、C++ プログラムは 2 つの個別のシンボルと見なしますが、リソース コンパイラ/エディターはどちらの名前も 1 つのシンボルを指していると見なします。

   > [!NOTE]
   > 以下に概要が示されている標準シンボル名スキーム (ID*_[キーワード]) に従わず、シンボル名がリソース スクリプト コンパイラで使用されているキーワードと同じである場合、リソース スクリプト ファイルをビルドしようとすると、ランダムであるように見えるエラーが発生し、診断が困難になります。 これを回避するには、標準名前付けスキームに従います。

シンボル名には説明的なプレフィックスがあり、対象となるリソースやオブジェクトの種類を示します。 これらの説明的なプレフィックスは、テキストを組み合わせた ID で始まります。 Microsoft Foundation Class (MFC) ライブラリでは、以下の表に示されているシンボルの名前付け規則が使用されています。

|カテゴリ|プレフィックス|使用|
|--------------|------------|---------|
|リソース|IDR_ IDD_ IDC_ IDI_ IDB_|アクセラレータまたはメニュー (および関連付けられているかカスタムのリソース) ダイアログ ボックス カーソル アイコン ビットマップ|
|メニュー項目|ID_|メニュー項目|
|コマンド|ID_|コマンド|
|コントロールと子ウィンドウ|IDC_|コントロール|
|文字列|IDS_|文字列テーブル内の文字列|
|MFC|AFX_|定義済みの MFC シンボル用に予約されています|

## <a name="to-change-a-symbol-value-assigned-to-a-single-resource-or-object"></a>1 つのリソースまたはオブジェクトに割り当てられているシンボル値を変更するには

1. [リソース ビュー](../windows/resource-view-window.md)リソースを選択します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. **プロパティ**ウィンドウで、型、シンボル名の後に等号 (=)、整数の**ID**ボックスで、たとえば。

    ```
    IDC_EDITNAME=5100
    ```

新しい値は、次回のプロジェクトの保存時に、シンボル ヘッダー ファイルに格納されます。 検証後は、[ID] ボックスに等号と値は表示されず、シンボル名だけが表示されます。

### <a name="symbol-value-restrictions"></a>シンボル値の制限

シンボル値には、#define プリプロセッサ ディレクティブに対して通常の方法で表現される整数を指定できます。 シンボル値の例をいくつか次に示します。

```
18
4001
0x0012
-3456
```

リソース (アクセラレータ、ビットマップ、カーソル、ダイアログ ボックス、アイコン、メニュー、文字列テーブル、およびバージョン情報) のシンボル値は、0 ～ 32,767 の範囲の 10 進値である必要があります (16 進値は使用できません)。 一部のリソース (ダイアログ ボックスのコントロールや文字列テーブルの個々の文字列など) のシンボル値には、0 ～ 65,534 または、-32,768 ～ 32,767 の範囲の値を使用できます。

リソース シンボルは、16 ビットの値です。 シンボル値は符号付きまたは符号なしとして入力できますが、内部的には符号なし整数として使用されます。 したがって、負の値は対応する正の値にキャストされます。

シンボル値のいくつかの制限を次に示します。

- Visual Studio 開発環境と MFC では、特殊な目的でいくつかの数値の範囲を使用しています。 最上位ビットが設定されたすべての数値 (符号に応じて -32,768 ～ -1 または 32,768 ～ 65,534) は MFC によって予約されています。

- 他のシンボル文字列を使用してシンボル値を定義することはできません。 たとえば、次のシンボル定義はサポートされません。

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- 引数を持つプリプロセッサ マクロを値の定義として使用することはできません。 例:

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

   これは、コンパイル時に `ID` がどのような値に評価されるかに関係なく、有効な式ではありません。

- アプリケーションには、式を使用して定義されたシンボルを含む既存のファイルが存在する可能性があります。 読み取り専用のシンボルとしてシンボルを含める方法の詳細については、次を参照してください。[共有を使用する (読み取り専用) または計算型シンボル](../windows/including-shared-read-only-or-calculated-symbols.md)します。

数値の範囲の詳細については、次を参照してください[TN023:。標準 MFC リソース](../mfc/tn023-standard-mfc-resources.md)します。

## <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>リソースのシンボル用のヘッダー ファイルの名前を変更するには

1. [リソース ビュー](../windows/resource-view-window.md)を .rc ファイルを右クリックして[リソース ファイルのインクルード](../windows/resource-includes-dialog-box.md)ショートカット メニューから。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. **シンボル ヘッダー ファイル**ボックスに、インクルード ファイルの新しい名前を入力します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[定義済みシンボル ID](../windows/predefined-symbol-ids.md)<br/>
[リソース シンボルの表示](../windows/viewing-resource-symbols.md)<br/>
