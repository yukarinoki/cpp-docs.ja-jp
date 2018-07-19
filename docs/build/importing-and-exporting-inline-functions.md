---
title: インポートして、インライン関数をエクスポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b666d450766a5a285f02517d92d5eb4dc3f29c68
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368578"
---
# <a name="importing-and-exporting-inline-functions"></a>インライン関数のインポートとエクスポート
インポートされた関数は、インラインとして定義することができます。 結果は、標準関数のインライン; を定義すると同じでは約関数の呼び出しは、マクロと同様に、インライン コードに展開されます。 これは、機能は、によってメンバー関数の効率がインラインそのクラスで DLL を C++ のサポート方法、主に便利です。  
  
 インポートされたインライン関数の 1 つの機能は、C++ では、そのアドレスを取得できることです。 コンパイラは、DLL 内のインライン関数のコピーのアドレスを返します。 インポートされたインライン関数の他の機能では、グローバル インポートされたデータとは異なり、インポートされた関数の静的なローカル データを初期化することができます。  
  
> [!CAUTION]
>  バージョン間の競合の可能性があるために、インライン関数をインポートを提供する場合は注意が必要です。 インライン関数は、アプリケーション コードに展開されます。したがって、関数を書き換えた後で場合、それが更新されない、アプリケーション自体を再コンパイルする場合を除き、します。 (通常は、DLL 関数できますを更新するそれらを使用するアプリケーションを再構築しないで。)  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [DLL からのエクスポートします。](../build/exporting-from-a-dll.md)  
  
-   [使用して、DLL からエクスポートします。DEF ファイル](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [エクスポート方式を使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [_Declspec (dllimport) を使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
## <a name="see-also"></a>関連項目  
 [インポートとエクスポート](../build/importing-and-exporting.md)