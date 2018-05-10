---
title: インポートとエクスポート |Microsoft ドキュメント
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
ms.openlocfilehash: 9ee3ffe33dbb99f1f9b4124e2695d2e56dbe5544
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="importing-and-exporting"></a>インポートとエクスポート
アプリケーションにパブリック シンボルをインポートまたは 2 つのメソッドを使用して DLL から関数をエクスポートできます。  
  
-   DLL をビルドする際に、モジュール定義 (.def) ファイルを使用します。  
  
-   キーワードを使用して **_declspec**または**方式**メイン アプリケーションの関数定義で  
  
## <a name="using-a-def-file"></a>.Def ファイルを使用します。  
 モジュール定義ファイル (.def) は、テキスト ファイルです。DLL のさまざまな属性を記述する 1 つ以上のモジュール文が含まれています。 使用しない場合 **_declspec**または**方式**DLL の関数をエクスポートする DLL に .def ファイルが必要です。  
  
 .Def ファイルを使用する[アプリケーションをインポート](../build/importing-using-def-files.md)または[DLL からエクスポート](../build/exporting-from-a-dll-using-def-files.md)です。  
  
## <a name="using-declspec"></a>_ _Declspec を使用します。  
 Visual C++ 使用 **_declspec (dllimport)** と**方式**を置き換える、 **_ _export**キーワードの 16 ビット バージョンの Visual C で以前に使用します。  
  
 使用する必要はありません **_declspec (dllimport)** これが正しくコンパイルするコードの優れたコードを生成するコンパイラを使用します。 コンパイラはかどうか、関数が存在する DLL のか、通常するが DLL の境界を越える関数呼び出しの間接参照のレベルをスキップするコードを生成するために、コンパイラにより決定できるため、優れたコードを生成することです。 ただし、使用する必要があります **_declspec**を DLL で使用される変数をインポートします。  
  
 適切な .def ファイルの EXPORTS セクションに**方式**は必要ありません。 **方式**.def ファイルを使用せず、.exe または .dll ファイルから関数をエクスポートする簡単な方法を提供するようになりました。  
  
 インポートを修正する参照しなければならないページの数を最小限に抑えるには、Win32 のポータブル実行可能ファイル形式は設計されています。 これを行うには、インポート アドレス テーブルと呼ばれる 1 つの場所で任意のプログラムのすべてのインポート アドレスがかかります。 これにより、インポートにアクセスするときに、1 つまたは 2 つのページを変更するローダー。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [アプリケーションへのインポート](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL からのエクスポートします。](../build/exporting-from-a-dll.md)  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)