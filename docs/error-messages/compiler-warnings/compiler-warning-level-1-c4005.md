---
title: コンパイラの警告 (レベル 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 4e95f8deeb61c5a4d56e0643beb6a746f848e33e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164730"
---
# <a name="compiler-warning-level-1-c4005"></a>コンパイラの警告 (レベル 1) C4005

' identifier ': マクロの再定義

マクロ識別子は2回定義されます。 コンパイラは、2番目のマクロ定義を使用します。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. `#define` ディレクティブを使用して、コマンドラインとコードにマクロを定義します。

1. インクルードファイルからインポートされたマクロ。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. 定義の1つを削除します。

1. 2番目の定義の前に[#undef](../../preprocessor/hash-undef-directive-c-cpp.md)ディレクティブを使用します。

次の例では、C4005 が生成されます。

```cpp
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
