---
title: コンパイラの警告 (レベル 4) C4932
description: Microsoft C/c + + コンパイラの警告 C4932 について説明します。
ms.date: 08/25/2020
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: ece2ae14fd8e1198a97f5e772fcce52c47464878
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898298"
---
# <a name="compiler-warning-level-4-c4932"></a>コンパイラの警告 (レベル 4) C4932

> `__identifier(identifier_1)` と `__identifier(identifier_2)` は区別されません。

コンパイラは **`_finally`** 、とまたはを、 **`__finally`** **`__try`** **`_try`** に渡されるパラメーターとして [`__identifier`](../../extensions/identifier-cpp-cli.md) 区別できません。 [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) エラーが発生するため、同じプログラム内で識別子として両方を使用しないようにします。

次の例では C4932 警告が生成されます。

```cpp
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```
