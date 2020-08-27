---
title: リソースの後処理
description: 構造化例外処理の終了ハンドラー中にリソースを解放する方法。
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: dae92a515db25b9985a890d7d08cc213f88ecfea
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898435"
---
# <a name="cleaning-up-resources"></a>リソースの後処理

終了ハンドラーの実行中に、終了ハンドラーが呼び出される前にどのリソースが取得されたかわからない場合があります。 すべてのリソースが **`__try`** 取得される前に、ステートメントブロックが中断された可能性があります。これにより、すべてのリソースが開かれているわけではありません。

安全にするには、終了処理のクリーンアップを続行する前に、どのリソースが開いているかを確認する必要があります。 推奨される手順は、次のとおりです。

1. 各ハンドルを NULL に初期化します。

1. **`__try`** ステートメントブロックで、リソースを取得します。 ハンドルは、リソースが取得されるときに正の値に設定されます。

1. **`__finally`** ステートメントブロックで、対応する handle 変数または flag 変数が0以外であるか、NULL ではない各リソースを解放します。

## <a name="example"></a>例

たとえば、次のコードでは、終了ハンドラーを使用して3つのファイルを閉じ、メモリブロックを解放します。 これらのリソースは、ステートメントブロックで取得されました **`__try`** 。 リソースをクリーンアップする前に、コードはまずリソースが取得されたかどうかを確認します。

```cpp
// exceptions_Cleaning_up_Resources.cpp
#include <stdlib.h>
#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void fileOps() {
   FILE  *fp1 = NULL,
         *fp2 = NULL,
         *fp3 = NULL;
   LPVOID lpvoid = NULL;
   errno_t err;

   __try {
      lpvoid = malloc( BUFSIZ );

      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );
      err = fopen_s(&fp3, "CARS.DAT", "w+" );
   }
   __finally {
      if ( fp1 )
         fclose( fp1 );
      if ( fp2 )
         fclose( fp2 );
      if ( fp3 )
         fclose( fp3 );
      if ( lpvoid )
         free( lpvoid );
   }
}

int main() {
   fileOps();
}
```

## <a name="see-also"></a>関連項目

[終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
