---
title: コンパイラの警告 (レベル 1) C4005 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4005
dev_langs:
- C++
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8be172086e316c991f461b3ac42f58739801cfa7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022969"
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