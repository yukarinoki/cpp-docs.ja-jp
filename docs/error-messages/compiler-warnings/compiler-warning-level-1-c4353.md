---
title: コンパイラの警告 (レベル 1) C4353
ms.date: 11/04/2016
f1_keywords:
- C4353
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
ms.openlocfilehash: 305c1156ae8dc664edba17287786db50bfabbd18
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384193"
---
# <a name="compiler-warning-level-1-c4353"></a>コンパイラの警告 (レベル 1) C4353

標準の拡張機能を使用します。 関数式として定数 0。 組み込みの '_ _noop' 関数を使用してください。

関数の式として定数ゼロ (0) を使用することはできません。 詳細については、次を参照してください。 [_ _noop](../../intrinsics/noop.md)します。

次の例では、C4353 が生成されます。

```
// C4353.cpp
// compile with: /W1
void MyPrintf(void){};
#define X 0
#if X
   #define DBPRINT MyPrint
#else
   #define DBPRINT 0   // C4353 expected
#endif
int main(){
DBPRINT();
}
```