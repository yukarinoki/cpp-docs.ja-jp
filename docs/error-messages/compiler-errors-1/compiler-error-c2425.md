---
title: コンパイラ エラー C2425 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2425
dev_langs:
- C++
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30f0bf6fb90a08647c9547108c17040fbf4c09ba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071361"
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