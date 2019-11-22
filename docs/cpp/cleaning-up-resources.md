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
ms.openlocfilehash: 225c3ccaf3342f11ad4eb6d6575ad3ac542acfd2
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246647"
---
# <a name="cleaning-up-resources"></a>リソースの後処理

終了ハンドラーの実行中は、終了ハンドラーが呼び出される前に実際に割り当てられたリソースがわからない場合があります。 It is possible that the **__try** statement block was interrupted before all resources were allocated, so that not all resources were opened.

したがって、安全のために、終了処理のクリーンアップに進む前に、どのリソースが実際に開いているかをチェックする必要があります。 推奨される手順は、次のとおりです。

1. 各ハンドルを NULL に初期化します。

1. In the **__try** statement block, allocate resources. 各ハンドルは、リソースが割り当てられると、正の値に設定されます。

1. In the **__finally** statement block, release each resource whose corresponding handle or flag variable is nonzero or not NULL.

## <a name="example"></a>例

For example, the following code uses a termination handler to close three files and a memory block that were allocated in the **__try** statement block. コードでは、リソースをクリーンアップする前に、まずリソースが割り当てられているかどうかを確認しています。

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

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
