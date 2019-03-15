---
title: C/C++ 言語の実行形式で使う C 関数のエクスポート
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
ms.openlocfilehash: b7ba2ed30615efb3b05e71cecf0ea69898feb8ba
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812435"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>C/C++ 言語の実行形式で使う C 関数のエクスポート

C 言語または C++ 言語のモジュールからアクセスすることは、使用する必要があります、C で記述された DLL 内の関数がある場合、 **_ _cplusplus**言語を判断するプリプロセッサ マクロがコンパイルされると、これらを宣言C++ 言語のモジュールから使用されている場合、C リンケージを持つ関数です。 この手法を使用して DLL のヘッダー ファイルを提供する場合、変更なしでの C および C++ のユーザーがこれらの関数を使用できます。

次のコードでは、C および C++ のクライアント アプリケーションで使用できるヘッダー ファイルを示します。

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

関数宣言のヘッダー ファイルでは、C++ ソース ファイルでは、前述の手法が未使用 C 関数を C++ 実行可能ファイルにリンクする必要がある場合、コンパイラが C の関数名を修飾するを防ぐために、次を行います。

```cpp
extern "C" {
#include "MyCHeader.h"
}
```

## <a name="what-do-you-want-to-do"></a>実行する操作

- [.Def ファイルを使った DLL からエクスポートします。](exporting-from-a-dll-using-def-files.md)

- [関数を使った DLL からエクスポートします。](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使ったエクスポート/インポート](exporting-and-importing-using-afx-ext-class.md)

- [エクスポート方式の使用](determining-which-exporting-method-to-use.md)

- [使用してアプリケーションをインポートします。](importing-into-an-application-using-declspec-dllimport.md)

- [DLL を初期化します。](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [装飾名](reference/decorated-names.md)

- [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
