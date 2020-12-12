---
description: '詳細情報: コンパイラの警告 (レベル 1) C4005'
title: コンパイラの警告 (レベル 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: a8de4974d87eb5d8396085bb79dfbfe14a177602
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325988"
---
# <a name="compiler-warning-level-1-c4005"></a>コンパイラの警告 (レベル 1) C4005

' identifier ': マクロの再定義

マクロ識別子は2回定義されます。 コンパイラは、2番目のマクロ定義を使用します。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ディレクティブを使用して、コマンドラインとコードにマクロを定義し `#define` ます。

1. インクルードファイルからインポートされたマクロ。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. 定義の1つを削除します。

1. 2番目の定義の前に [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) ディレクティブを使用します。

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
