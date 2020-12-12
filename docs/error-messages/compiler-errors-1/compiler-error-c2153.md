---
description: 詳細については、「コンパイラエラーいう c2153」を参照してください。
title: コンパイラ エラー C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: 0b5ded0908f3c12033f1c2b3b034b41b52e847cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181294"
---
# <a name="compiler-error-c2153"></a>コンパイラ エラー C2153

16進定数には少なくとも1つの16進数字が必要です

16進定数0x、0X、および \x は無効です。 少なくとも1つの16進数が x または X の後に続く必要があります。

次の例では、いう c2153 が生成されます。

```cpp
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```
