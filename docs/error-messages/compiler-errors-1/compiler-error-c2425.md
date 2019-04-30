---
title: コンパイラ エラー C2425
ms.date: 11/04/2016
f1_keywords:
- C2425
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
ms.openlocfilehash: fcbcf06df3330320bf014c132abc543e2e2e8087
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402841"
---
# <a name="compiler-error-c2425"></a>コンパイラ エラー C2425

'トークン' : 'コンテキスト' 内に非定数式があります。

このコンテキストでは、トークンが非定数式の一部を形成していす。

この問題を解決するには、トークンをリテラル定数または計算トークンに置き換えます。

次の例では警告 C2425 が生成されます。

```
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