---
title: DLL からのエクスポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting DLLs [C++], about exporting from DLLs
- exporting functions [C++], DLLs (exporting from)
- exporting DLLs [C++]
- DLLs [C++], exporting from
- DLL exports [C++]
- functions [C++], exporting
- exports table [C++]
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07efe3d73b3f78dfb30e85ffad6434e2907c36c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367954"
---
# <a name="exporting-from-a-dll"></a>DLL からのエクスポート  
  
.DLL のレイアウトは .exe ファイルとよく似ていますが、重要な相違点が 1 つあります。DLL ファイルには、エクスポート テーブルが含まれています。 エクスポート テーブルには、DLL が別の実行形式に対してエクスポートする各関数の名前が含まれています。 これらの関数は、DLL のエントリ ポイントです。エクスポート テーブルに記述されたエクスポート関数のみが、別の実行形式にアクセスできます。 DLL 内のその他の関数は、その DLL でしか使えません。 DLL のエクスポート テーブルを使用して表示することができます、 [DUMPBIN](../build/reference/dumpbin-reference.md)ツールに/EXPORTS オプション。  
  
 DLL から関数をエクスポートする方法には、次の 2 つがあります。  
  
-   モジュール定義 (.def) ファイルを作成し、DLL をビルドするときに .def ファイルを使用します。 する場合は、このアプローチを使用して[名ではなく序数で DLL から関数をエクスポート](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)です。  
  
-   キーワードを使用して**方式**関数の定義にします。  
  
 いずれかの方法で関数をエクスポートするときに必ず使用して、 [_ _stdcall](../cpp/stdcall.md)呼び出し規約です。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [.Def ファイルを使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C または C++ 言語の実行可能ファイルで使用するための C 関数をエクスポートします。](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [名前ではなく序数で DLL から関数をエクスポートします。](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)  
  
-   [エクスポート方式を使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [リンク方式を使い分け](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
-   [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [アプリケーションへのインポート](../build/importing-into-an-application.md)  
  
-   [インポートして、インライン関数をエクスポートします。](../build/importing-and-exporting-inline-functions.md)  
  
-   [相互インポート](../build/mutual-imports.md)  
  
## <a name="see-also"></a>関連項目  
 [インポートとエクスポート](../build/importing-and-exporting.md)