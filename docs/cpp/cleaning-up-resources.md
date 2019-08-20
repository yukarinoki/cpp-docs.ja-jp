---
title: リソースの後処理
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: 0db21b20b94dc1a3f347bd848c999a961398759b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386123"
---
# <a name="cleaning-up-resources"></a>リソースの後処理

終了ハンドラーの実行中は、終了ハンドラーが呼び出される前に実際に割り当てられたリソースがわからない場合があります。 できますが、 **__try**ステートメント ブロックは、そのすべてのリソースが開かれたようにすべてのリソースが割り当てられた、前に中断されました。

したがって、安全のために、終了処理のクリーンアップに進む前に、どのリソースが実際に開いているかをチェックする必要があります。 推奨される手順は、次のとおりです。

1. 各ハンドルを NULL に初期化します。

1. **__try**ステートメント ブロックに、リソースを割り当てます。 各ハンドルは、リソースが割り当てられると、正の値に設定されます。

1. **__finally**ステートメント ブロック、0 以外の場合は、対応するハンドルまたはフラグ変数を持つ各リソースを解放または not NULL します。

## <a name="example"></a>例

次のコードは終了ハンドラーを使用して、3 つのファイルとで割り当てられたメモリ ブロックを閉じるなど、 **__try**ステートメント ブロックです。 コードでは、リソースをクリーンアップする前に、まずリソースが割り当てられているかどうかを確認しています。

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
