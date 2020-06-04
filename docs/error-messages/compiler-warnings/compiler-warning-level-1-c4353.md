---
title: コンパイラの警告 (レベル 1) C4353
ms.date: 11/04/2016
f1_keywords:
- C4353
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
ms.openlocfilehash: 9c91a3d21a16cc8891d6f04db49c3a0f0ec26e2c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187194"
---
# <a name="compiler-warning-level-1-c4353"></a>コンパイラの警告 (レベル 1) C4353

非標準の拡張機能が使用されています: 定数0が関数式です。 組み込みの '__noop' 関数を使用してください。

定数ゼロ (0) を関数式として使用することはできません。 詳細については、「 [__noop](../../intrinsics/noop.md)」を参照してください。

次の例では、C4353 が生成されます。

```cpp
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
