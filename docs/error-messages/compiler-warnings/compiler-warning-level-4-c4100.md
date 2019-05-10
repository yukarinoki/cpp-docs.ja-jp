---
title: コンパイラの警告 (レベル 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: ccb438cf7c80edb1403683ac4817617ffccc690d
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447733"
---
# <a name="compiler-warning-level-4-c4100"></a>コンパイラの警告 (レベル 4) C4100

'identifier' : 未参照仮パラメーター

仮パラメーターが関数の本体で参照されていません。 未参照のパラメーターは無視されます。

また、コードがプリミティブ型の他の未参照パラメーターでデストラクターを呼び出すと C4100 が出される可能性があります。  これは、Microsoft の制限事項C++コンパイラ。

次の例では、C4100 が生成されます。

```
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