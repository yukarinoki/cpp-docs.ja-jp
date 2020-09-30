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
ms.openlocfilehash: 4dcf46e6bdde66a303afc2c4ec94fc8aefdd5e5d
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506639"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>C/C++ 言語の実行形式で使う C 関数のエクスポート

C で記述された DLL の関数に C 言語または C++ 言語モジュールからアクセスする場合、 **__cplusplus** プリプロセッサ マクロを使用してコンパイル中の言語を判断し、C++ 言語モジュールから使用されている場合、C リンケージでそれらの関数を宣言してください。 この手法を使用し、DLL のヘッダー ファイルを指定する場合、C と C++ のユーザーはこれらの関数を変更せずに使用できます。

次のコードでは、C と C++ クライアント アプリケーションで使用できるヘッダー ファイルを確認できます。

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

C 関数を C++ 実行可能ファイルにリンクする必要があるとき、関数宣言ヘッダー ファイルで上記の手法が使用されていない場合、C++ ソース ファイルで、次を行い、コンパイラが C 関数名を修飾するのを禁止します。

```cpp
extern "C" {
#include "MyCHeader.h"
}
```

## <a name="what-do-you-want-to-do"></a>実行する操作

- [.def ファイルを使用した DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使用した DLL からのエクスポート](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使用したエクスポートとインポート](exporting-and-importing-using-afx-ext-class.md)

- [エクスポート方式の使い分け](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [装飾名](reference/decorated-names.md)

- [extern を使用したリンケージの指定](../cpp/extern-cpp.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
