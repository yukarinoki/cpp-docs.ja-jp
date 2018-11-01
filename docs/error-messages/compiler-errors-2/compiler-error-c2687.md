---
title: コンパイラ エラー C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: a30efa264a4e7be387c3c2363940bd5ceca1bcc4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540947"
---
# <a name="compiler-error-c2687"></a>コンパイラ エラー C2687

'type': 例外宣言の 'void' または不完全な型、ポインター、または不完全な型への参照を表すことはできません

型の例外宣言の一部である場合は、定義済みでない void があります。

次の例では、C2687 が生成されます。

```
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

考えられる解決方法:

```
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```