---
title: インポートとエクスポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc07ba1de15795e99a5e2ed75a5df9752026d08e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717003"
---
# <a name="importing-and-exporting"></a>インポートとエクスポート

パブリック シンボルをアプリケーションにインポートまたは 2 つのメソッドを使用して DLL から関数をエクスポートできます。

- DLL をビルドするときに、モジュール定義 (.def) ファイルを使用します。

- キーワードを使用して **_declspec**または**方式**メイン アプリケーションの関数定義で

## <a name="using-a-def-file"></a>.Def ファイルを使用します。

モジュール定義ファイル (.def) は、テキスト ファイルです。DLL のさまざまな属性を記述する 1 つ以上のモジュール文が含まれています。 使用しない場合 **_declspec**または**方式**DLL の関数をエクスポートする DLL に .def ファイルが必要です。

.Def ファイルを使用する[アプリケーションにインポート](../build/importing-using-def-files.md)または[DLL からエクスポート](../build/exporting-from-a-dll-using-def-files.md)します。

## <a name="using-declspec"></a>_ _Declspec を使用します。

C++ での visual **_declspec**と**方式**を置き換える、 **_ _export**キーワードの 16 ビット バージョンの Visual C で以前に使用します。

使用する必要はありません **_declspec**そうですが、正しくコンパイルするコードのより優れたコードを生成するコンパイラを使用します。 コンパイラはかどうか、関数が存在する DLL にか、DLL の境界を越える関数呼び出し内に存在するが通常の間接参照のレベルをスキップするコードを生成するために、コンパイラにより決定できるためより優れたコードを生成できません。 ただし、使用する必要があります **_declspec** DLL で使用される変数をインポートします。

適切な .def ファイルの EXPORTS セクションに**方式**は必要ありません。 **方式**.def ファイルを使用せずに、.exe や .dll ファイルから関数をエクスポートする簡単な方法を提供するようになりました。

インポートを修正するタッチする必要がありますページの数を最小限に抑えるには、Win32 のポータブル実行可能ファイルの形式は設計されています。 これを行うには、インポート アドレス テーブルと呼ばれる 1 つの場所で任意のプログラムのすべてのインポート アドレスを配置します。 これにより、インポートにアクセスするときに、1 つまたは 2 つのページを変更するローダーができます。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [アプリケーションへのインポート](../build/importing-into-an-application-using-declspec-dllimport.md)

- [DLL からのエクスポートします。](../build/exporting-from-a-dll.md)

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)