---
title: コンパイラ エラー C2088
ms.date: 11/04/2016
f1_keywords:
- C2088
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
ms.openlocfilehash: 6d53f2896fc3b964a4d2652b3bfd0dcebb4a7226
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550777"
---
# <a name="compiler-error-c2088"></a>コンパイラ エラー C2088

'operator': 'クラス キー' に対して正しくありません

演算子は、構造体または共用体が定義されていません。 このエラーは C コードのみです。

次の例では、C2088 に 3 回が生成されます。

```
// C2088.c
struct S {
   int m_i;
} s;

int main() {
   int i = s * 1;   // C2088
   struct S s2 = +s;   // C2088
   s++;   // C2088
}
```