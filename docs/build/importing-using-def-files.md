---
description: '詳細情報: DEF ファイルを使ったインポート'
title: DEF ファイルを使ったインポート
ms.date: 11/04/2016
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
ms.openlocfilehash: 9eb4face47bf999daa8f969282cc621708a76006
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156152"
---
# <a name="importing-using-def-files"></a>DEF ファイルを使ったインポート

.def ファイルと共に **`__declspec(dllimport)`** を使用することを選択した場合、間違ったコーディングによって問題が発生する可能性を減らすため、CONSTANT の代わりに DATA を使用するように .def ファイルを変更してください。

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   DATA
```

理由を次の表に示します。

|キーワード|インポート ライブラリの出力|Exports|
|-------------|---------------------------------|-------------|
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|

**`__declspec(dllimport)`** と CONSTANT を使用すると、明示的なリンクを可能にする目的で作成される .lib DLL インポート ライブラリに `imp` バージョンと未修飾名の両方が一覧表示されます。 **`__declspec(dllimport)`** と DATA を使用すると、名前の `imp` バージョンのみが一覧表示されます。

CONSTANT を使用した場合、次のコード コンストラクトのいずれかを利用し、`ulDataInDll` にアクセスできます。

```
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/
if (ulDataInDll == 0L)   /*sample code fragment*/
```

\- または -

```
ULONG *ulDataInDll;      /*prototype*/
if (*ulDataInDll == 0L)  /*sample code fragment*/
```

ただし、.def ファイルで DATA を使用する場合、次の定義でコンパイルされたコードのみ、変数 `ulDataInDll` にアクセスできます。

```
__declspec(dllimport) ULONG ulDataInDll;

if (ulDataInDll == 0L)   /*sample code fragment*/
```

CONSTANT の使用は安全度が下がります。間接参照のレベルを上げるのを忘れた場合、変数自体ではなく、インポート アドレス テーブルの変数ポインターにアクセスする可能性があるからです。 この種の問題は多くの場合、アクセス違反として現れます。インポート アドレス テーブルが現在、コンパイラとリンカーによって読み取り専用になるためです。

このケースを説明する目的で、.def ファイルで CONSTANT が確認されると、現行の MSVC リンカーからは警告が発行されます。 CONSTANT を使用する唯一かつ本当の理由は、ヘッダー ファイルによってプロトタイプに **`__declspec(dllimport)`** をリストアップされなかった場合、一部のオブジェクト ファイルを再コンパイルできないことにあります。

## <a name="see-also"></a>関連項目

[アプリケーションへのインポート](importing-into-an-application.md)
