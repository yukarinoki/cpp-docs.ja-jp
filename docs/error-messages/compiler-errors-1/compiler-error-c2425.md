---
description: 詳細については、「コンパイラエラー C2425」を参照してください。
title: コンパイラ エラー C2425
ms.date: 11/04/2016
f1_keywords:
- C2425
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
ms.openlocfilehash: 03e3ca02e0ceff70135ce14ee982d2d5a0009982
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190225"
---
# <a name="compiler-error-c2425"></a>コンパイラ エラー C2425

'トークン' : 'コンテキスト' 内に非定数式があります。

このコンテキストでは、トークンが非定数式の一部を形成していす。

この問題を解決するには、トークンをリテラル定数または計算トークンに置き換えます。

次の例では警告 C2425 が生成されます。

```cpp
// C2425.cpp
// processor: x86
int main() {
   int i = 3;
   __asm {
      mov eax, [ebp - i]   // C2425
      mov eax, [ebp - 3]   // OK
   }
}
```
