---
title: コンパイラの警告 (レベル 1) C4087
ms.date: 11/04/2016
f1_keywords:
- C4087
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
ms.openlocfilehash: 84d24d95053b962c1776dc18576e4ed236b63469
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643717"
---
# <a name="compiler-warning-level-1-c4087"></a>コンパイラの警告 (レベル 1) C4087

'function': 関数のパラメーター リストは 'void' で宣言されています

関数の宣言には仮パラメーターが指定されていませんが、関数呼び出しには実パラメーターが指定されています。 余分なパラメーターは、この関数の呼び出し規則に従って渡されます。

この警告は、C コンパイラの場合に表示されます。

## <a name="example"></a>例

```
// C4087.c
// compile with: /W1
int f1( void ) {
}

int main() {
   f1( 10 );   // C4087
}
```