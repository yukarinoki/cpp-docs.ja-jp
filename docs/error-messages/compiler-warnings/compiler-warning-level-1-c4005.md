---
title: コンパイラの警告 (レベル 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 76aab2160bd5f7918771dcf63b7297a869da751e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187340"
---
# <a name="compiler-warning-level-1-c4005"></a>コンパイラの警告 (レベル 1) C4005

'identifier': 再定義はマクロ

マクロの識別子が 2 回定義されます。 コンパイラは、2 つ目のマクロ定義を使用します。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. コマンドラインで、コードでは、マクロを定義する、`#define`ディレクティブ。

1. マクロはインクルード ファイルからインポートします。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. 定義を 1 つを削除します。

1. 使用して、 [#undef](../../preprocessor/hash-undef-directive-c-cpp.md)ディレクティブを 2 番目の定義。

次の例では、C4005 が生成されます。

```
// C4005.cpp
// compile with: /W1 /EHsc
#include <iostream>
using namespace std;

#define TEST "test1"
#define TEST "test2"   // C4005 delete or rename to resolve the warning

int main() {
   cout << TEST << endl;
}
```