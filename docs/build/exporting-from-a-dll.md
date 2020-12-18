---
description: '詳細情報: DLL からのエクスポート'
title: DLL からのエクスポート
ms.date: 11/04/2016
helpviewer_keywords:
- exporting DLLs [C++], about exporting from DLLs
- exporting functions [C++], DLLs (exporting from)
- exporting DLLs [C++]
- DLLs [C++], exporting from
- DLL exports [C++]
- functions [C++], exporting
- exports table [C++]
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
ms.openlocfilehash: 324ca733eab48973dc9ca902f81abfe4ce52a5c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162938"
---
# <a name="exporting-from-a-dll"></a>DLL からのエクスポート

.DLL のレイアウトは .exe ファイルとよく似ていますが、重要な相違点が 1 つあります。DLL ファイルには、エクスポート テーブルが含まれています。 エクスポート テーブルには、DLL が別の実行形式に対してエクスポートする各関数の名前が含まれています。 これらの関数は、DLL のエントリ ポイントです。エクスポート テーブルに記述されたエクスポート関数のみが、別の実行形式にアクセスできます。 DLL 内のその他の関数は、その DLL でしか使えません。 DLL のエクスポート テーブルを表示するには、[DUMPBIN](reference/dumpbin-reference.md) ツールに /EXPORTS オプションを指定します。

DLL から関数をエクスポートする方法には、次の 2 つがあります。

- モジュール定義 (.def) ファイルを作成し、DLL をビルドするときに .def ファイルを使用します。 [名前ではなく序数で DLL から関数をエクスポートする](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)場合は、この方法を使用します。

- 関数の定義で **`__declspec(dllexport)`** キーワードを使用します。

上のどちらかの方法を使って関数をエクスポートする場合は、必ず [__stdcall](../cpp/stdcall.md) の呼び出し規則を使います。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [.def ファイルを使用した DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使用して DLL からエクスポートする](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使用してエクスポートとインポートを行う](exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行可能ファイルで使用する C++ 関数をエクスポートする](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C または C++ 言語の実行可能ファイルで使用する C 関数のエクスポート](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [名前ではなく序数値による DLL 関数のエクスポート](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)

- [エクスポート方式の使い分け](determining-which-exporting-method-to-use.md)

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [アプリケーションへのインポート](importing-into-an-application.md)

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互インポート](mutual-imports.md)

## <a name="see-also"></a>関連項目

[インポートとエクスポート](importing-and-exporting.md)
