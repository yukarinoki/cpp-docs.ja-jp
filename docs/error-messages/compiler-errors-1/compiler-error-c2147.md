---
description: 詳細については、「コンパイラエラー C2147」を参照してください。
title: コンパイラ エラー C2147
ms.date: 11/04/2016
f1_keywords:
- C2147
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
ms.openlocfilehash: 499b90ddad659a2a36652e783901b25f97eb76f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235373"
---
# <a name="compiler-error-c2147"></a>コンパイラ エラー C2147

構文エラー: ' identifier ' は新しいキーワードです

言語で予約済みキーワードになった識別子が使用されました。

次の例では、C2147 が生成されます。

```cpp
// C2147.cpp
// compile with: /clr
int main() {
   int gcnew = 0;   // C2147
   int i = 0;   // OK
}
```
