---
title: C または C++ 言語の実行可能ファイルで使う C 関数のエクスポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee1d572bbfaa31ac626bfeb2b6ed7f61604628c8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>C/C++ 言語の実行形式で使う C 関数のエクスポート  
  
C 言語または C++ 言語のモジュールからアクセスすることは、使用する必要があります、c 言語で記述された DLL 内の関数がある場合、 **_ _cplusplus**どの言語を判断するプリプロセッサ マクロのコンパイル中は、およびこれらを宣言C++ 言語のモジュールから使用されている場合、C リンケージを持つ関数です。 この手法を使用して、DLL のヘッダー ファイルを指定すると、これらの関数は、C および C++ のユーザーが変更なしで使用できます。  
  
次のコードは、C および C++ のクライアント アプリケーションで使用できるヘッダー ファイルを示しています。  
  
```h  
// MyCFuncs.h  
#ifdef __cplusplus  
extern "C" {  // only need to export C interface if  
              // used by C++ source code  
#endif  
  
__declspec( dllimport ) void MyCFunc();  
__declspec( dllimport ) void AnotherCFunc();  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
C 関数を C++ 実行可能ファイルにリンクする必要があるあり、関数宣言のヘッダー ファイルで使用していない前述の手法では、C++ ソース ファイル場合、コンパイラが C の関数名で修飾するを防ぐには、次を行います。  
  
```cpp  
extern "C" {  
#include "MyCHeader.h"  
}  
```  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [.Def ファイルを使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [エクスポート方式を使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [_Declspec (dllimport) を使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [装飾名](../build/reference/decorated-names.md)  
  
-   [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)  
  
## <a name="see-also"></a>関連項目  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)