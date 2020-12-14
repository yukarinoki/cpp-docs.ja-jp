---
description: '詳細情報: コンパイラの警告 (レベル 4) C4100'
title: コンパイラの警告 (レベル 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: 753be5e6e56e4ad94d6b742454fe62e303d430dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261997"
---
# <a name="compiler-warning-level-4-c4100"></a>コンパイラの警告 (レベル 4) C4100

'identifier' : 未参照仮パラメーター

仮パラメーターが関数の本体で参照されていません。 未参照のパラメーターは無視されます。

また、コードがプリミティブ型の他の未参照パラメーターでデストラクターを呼び出すと C4100 が出される可能性があります。  これは、Microsoft C++ コンパイラの制限事項です。

次の例では、C4100 が生成されます。

```cpp
// C4100.cpp
// compile with: /W4
void func(int i) {   // C4100, delete the unreferenced parameter to
                     //resolve the warning
   // i;   // or, add a reference like this
}

int main()
{
   func(1);
}
```
