---
description: '詳細については、「方法: シンボルを管理する」を参照してください。'
title: '方法: シンボルを管理する'
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
ms.openlocfilehash: 2a7bdc6994bfcdadc9b7d1d5b98350fcd47ad6fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118226"
---
# <a name="how-to-manage-symbols"></a>方法: シンボルを管理する

新しいリソースオブジェクトまたはリソースオブジェクトを作成すると、開発環境によって既定のシンボル名 (など) が割り当てら `IDD_DIALOG1` れます。 既定のシンボル名を変更したり、既にリソースに関連付けられているシンボルの名前を変更したりするには、 [プロパティウィンドウ](/visualstudio/ide/reference/properties-window) を使用します。

1つのリソースに関連付けられているシンボルの場合は、[ **プロパティ** ] ウィンドウを使用してシンボルの値を変更することもできます。 [ [リソースシンボル] ダイアログボックス](./creating-new-symbols.md) を使用すると、現在リソースに割り当てられていないシンボルの値を変更できます。

通常、すべてのシンボル定義はに保存され `Resource.h` ます。 ただし、同じディレクトリ内の複数のリソース ファイルを使用する場合などに、このインクルード ファイル名の変更が必要になることがあります。

> [!NOTE]
> プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [方法: リソースを作成する](how-to-create-a-resource-script-file.md)」を参照してください。

## <a name="symbol-name-restrictions"></a>シンボル名の制限

シンボル名に関する制限は、次のとおりです。

- ヘッダーファイル内のシンボル定義の競合を防ぐため、すべての [シンボル](symbols-resource-identifiers.md) はアプリケーションのスコープ内で一意である必要があります。

- シンボル名で有効な文字は、A ～ Z、a ～ z、0 ～ 9、およびアンダー スコア (_) です。

- シンボル名の先頭を数字にすることはできません。また、文字数は247文字に制限されています。

- シンボル名にスペースを含めることはできません。

- シンボル名は大文字と小文字が区別されませんが、最初のシンボル定義の大文字と小文字は保持されます。

   シンボルを定義するヘッダー ファイルは、リソース ファイルで定義されているリソースを参照するために、リソース コンパイラ/エディターと C++ プログラムの両方で使用されます。 大文字か小文字かだけが異なる 2 つのシンボル名の場合、C++ プログラムは 2 つの個別のシンボルと見なしますが、リソース コンパイラ/エディターはどちらの名前も 1 つのシンボルを指していると見なします。

> [!NOTE]
> 次に示す標準のシンボル名スキーム (ID * _ [キーワード]) に従わず、シンボル名がリソーススクリプトコンパイラで認識されているキーワードと同じである場合、リソーススクリプトファイルをビルドしようとすると、診断が困難なランダムエラー生成が発生します。 これを回避するには、標準名前付けスキームに従います。

シンボル名には説明的なプレフィックスがあり、対象となるリソースやオブジェクトの種類を示します。 これらの説明的なプレフィックスは、テキストを組み合わせた ID で始まります。 MFC (Microsoft Foundation Class) ライブラリでは、次の表に示すシンボルの名前付け規則が使用されています。

|カテゴリ|Prefix|使用|
|--------------|------------|---------|
|リソース|IDR_、IDD_、IDC_、IDI_、IDB_|アクセラレータまたはメニュー (および関連付けられているまたはカスタムリソース)、ダイアログボックス、カーソル、アイコン、ビットマップ|
|メニュー項目|ID_|メニュー項目|
|コマンド|ID_|コマンド|
|コントロールと子ウィンドウ|IDC_|コントロール|
|文字列|IDS_|文字列テーブル内の文字列|
|MFC|AFX_|定義済みの MFC シンボル用に予約されています|

### <a name="to-change-a-symbol-name-id"></a>シンボル名 (ID) を変更するには

1. [ [リソースビュー](how-to-create-a-resource-script-file.md#create-resources)で、リソースを選択します。

1. [ **プロパティ** ] ウィンドウで、新しいシンボル名を入力するか、[ **ID** ] ボックスに既存のシンボルの一覧から選択します。

   新しいシンボル名を入力すると、自動的に値が割り当てられます。

> [!NOTE]
> [ [リソースシンボル] ダイアログボックス](./creating-new-symbols.md) を使用すると、現在リソースに割り当てられていないシンボルの名前を変更できます。

## <a name="symbol-value-restrictions"></a>シンボル値の制限

シンボル値には、プリプロセッサディレクティブの通常の方法で表現された任意の整数を指定でき `#define` ます。 シンボル値の例をいくつか次に示します。

```
18
4001
0x0012
-3456
```

アクセラレータ、ビットマップ、カーソル、ダイアログボックス、アイコン、メニュー、文字列テーブル、バージョン情報などのリソースのシンボル値は、0 ~ 32767 の範囲の10進数である必要がありますが、16進数にすることはできません。 一部のリソース (ダイアログ ボックスのコントロールや文字列テーブルの個々の文字列など) のシンボル値には、0 ～ 65,534 または、-32,768 ～ 32,767 の範囲の値を使用できます。 数値範囲の詳細については、「 [テクニカルノート 23: STANDARD MFC Resources](../mfc/tn023-standard-mfc-resources.md)」を参照してください。

リソースシンボルは16ビットの数値です。 これらは符号付きまたは符号なしとして入力できますが、内部的には符号なし整数として使用されるため、負の数は対応する正の値にキャストされます。

シンボル値には、次のような制限があります。

- Visual Studio 開発環境と MFC では、特殊な目的でいくつかの数値の範囲を使用しています。 最上位ビットが設定されたすべての数値 (符号に応じて -32,768 ～ -1 または 32,768 ～ 65,534) は MFC によって予約されています。

- 他のシンボル文字列を使用してシンボル値を定義することはできません。 たとえば、次のシンボル定義はサポートされていません。

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- 引数を持つプリプロセッサマクロを値の定義として使用することはできません。 次の例は、 `ID` コンパイル時にがどのように評価されるかに関係なく、有効な式ではありません。

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

- アプリケーションには、式を使用して定義されたシンボルを含む既存のファイルが存在する可能性があります。

### <a name="to-change-a-symbol-value"></a>シンボル値を変更するには

1. [ [リソースビュー](how-to-create-a-resource-script-file.md#create-resources)で、リソースを選択します。

1. [ **プロパティ** ] ウィンドウで、[ **ID** ] ボックスにシンボル名の後に等号と整数を入力します。次に例を示します。

    ```
    IDC_EDITNAME=5100
    ```

   新しい値は、次回のプロジェクトの保存時に、シンボル ヘッダー ファイルに格納されます。 [ID] ボックスにはシンボル名だけが表示され、等号と値は検証後に表示されません。

## <a name="change-or-delete-symbols"></a>シンボルの変更または削除

[ [リソースシンボル] ダイアログボックス](./creating-new-symbols.md)では、リソースまたはオブジェクトにまだ割り当てられていない既存のシンボルを編集または削除できます。

### <a name="to-change-an-unassigned-symbol"></a>未使用のシンボルを変更するには

1. [ **名前** ] ボックスで、[未割り当て] シンボルを選択し、[ **変更**] を選択します。

1. [ **シンボルの変更** ] ダイアログボックスに表示されるボックスで、シンボルの名前または値を編集します。

> [!NOTE]
> リソースまたはオブジェクトに割り当てられているシンボルを変更するには、リソースエディターまたは [ **プロパティ** ] ウィンドウを使用する必要があります。

### <a name="to-delete-an-unassigned-unused-symbol"></a>割り当てられていない (使用されていない) シンボルを削除するには

[ **リソースシンボル** ] ダイアログボックスで、削除するシンボルを選択し、[ **削除**] を選択します。

> [!NOTE]
> リソースファイル内の未使用のシンボルを削除する前に、プログラム内の他の場所で使用されていないか、コンパイル時に含まれるリソースファイルによって使用されていないことを確認してください。

## <a name="include-symbols"></a>シンボルを含める

別のアプリケーションによって作成されたリソース ファイルを開発環境に初めて読み取るとき、インクルードされるすべてのヘッダー ファイルが読み取り専用とマークされます。 [ [リソースインクルード] ダイアログボックス](./how-to-include-resources-at-compile-time.md) を使用して、読み取り専用のシンボルヘッダーファイルを追加することもできます。

読み取り専用のシンボル定義を使用する状況の 1 つに、複数のプロジェクト間でシンボル ファイルを共有する場合があります。

インクルードされるシンボル ファイルは、単純な整数の代わりに式を使用してシンボル値を定義するシンボル定義を含む既存のリソースがあるときに使用することもできます。 次に例を示します。

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

1. [リソースビュー](how-to-create-a-resource-script-file.md#create-resources)で、 *.rc* ファイルを右クリックし、[[リソースのインクルード](./how-to-include-resources-at-compile-time.md)] を選択します。

1. [読み取り専用の **シンボルディレクティブ** ] ボックスで、コンパイラディレクティブを使用して、 `#include` 読み取り専用のシンボルを保存するファイルを指定します。

   ファイルは呼び出さない `Resource.h` でください。これは通常、メインのシンボルヘッダーファイルで使用されるファイル名です。

   > [!NOTE]
   > [読み取り専用の **シンボルディレクティブ** ] ボックスに入力した内容は、入力したとおりにリソースファイルに表示されます。 入力ミスや構文エラーがないことを確認してください。

   [読み取り専用の **シンボルディレクティブ** ] ボックスを使用すると、シンボルの定義のみを含むファイルを含めることができます。 リソース定義を含めないでください。そうしないと、ファイルの保存時に重複するリソース定義が作成されます。

1. 指定したファイルにシンボルを配置します。

   この方法でインクルードされるファイル内のシンボルは、リソースファイルを開くたびに評価されますが、ファイルを保存するときにディスクに置き換わることはありません。

1. **[OK]** を選択します。

### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>リソースのシンボル用のヘッダー ファイルの名前を変更するには

1. [リソースビュー](how-to-create-a-resource-script-file.md#create-resources)で、 *.rc* ファイルを右クリックし、[[リソースのインクルード](./how-to-include-resources-at-compile-time.md)] を選択します。

1. [ **シンボルヘッダーファイル** ] ボックスに、インクルードファイルの新しい名前を入力します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[リソース識別子 (シンボル)](symbols-resource-identifiers.md)<br/>
[方法: シンボルを作成する](creating-new-symbols.md)<br/>
[定義済みのシンボル Id](predefined-symbol-ids.md)<br/>
