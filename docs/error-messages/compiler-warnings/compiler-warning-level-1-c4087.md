---
title: コンパイラの警告 (レベル 1) C4087
ms.date: 11/04/2016
f1_keywords:
- C4087
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
ms.openlocfilehash: d939edfdf00b81837a167ab326ab5a7791e3e374
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164015"
---
# <a name="compiler-warning-level-1-c4087"></a>コンパイラの警告 (レベル 1) C4087

'function': 関数のパラメーター リストは 'void' で宣言されています

関数の宣言には仮パラメーターが指定されていませんが、関数呼び出しには実パラメーターが指定されています。 余分なパラメーターは、この関数の呼び出し規則に従って渡されます。

この警告は、C コンパイラの場合に表示されます。

## <a name="example"></a>例

```c
// C4087.c
// compile with: /W1
int f1( void ) {
}

int main() {
   f1( 10 );   // C4087
}
```
