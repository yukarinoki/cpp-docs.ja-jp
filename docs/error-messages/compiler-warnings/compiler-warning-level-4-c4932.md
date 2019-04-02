---
title: コンパイラの警告 (レベル 4) C4932
ms.date: 11/04/2016
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: cd37ee67545918991b286d16d0fe27b47414b3c3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769824"
---
# <a name="compiler-warning-level-4-c4932"></a>コンパイラの警告 (レベル 4) C4932

__identifier(identifier) と\__identifier(identifier) を区別することはできません

コンパイラは **_finally** と `__finally` または `__try` と **_try** を [__identifier](../../extensions/identifier-cpp-cli.md)に渡されるパラメーターとして区別することができません。 [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) エラーが発生するため、同じプログラム内で識別子として両方を使用しないようにします。

次の例では C4932 警告が生成されます。

```
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```