---
title: コンパイラ エラー C2147
ms.date: 11/04/2016
f1_keywords:
- C2147
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
ms.openlocfilehash: 0a093bbbaf9cf9f72625226f949a27b681005c35
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614488"
---
# <a name="compiler-error-c2147"></a>コンパイラ エラー C2147

構文エラー: 'identifier' は新しいキーワード

言語の予約済みキーワードが、識別子が使用されました。

次の例では、C2147 が生成されます。

```
// C2147.cpp
// compile with: /clr
int main() {
   int gcnew = 0;   // C2147
   int i = 0;   // OK
}
```