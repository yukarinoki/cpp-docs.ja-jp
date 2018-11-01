---
title: コンパイラ エラー C2206
ms.date: 11/04/2016
f1_keywords:
- C2206
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
ms.openlocfilehash: 3ee2dc24dd2472be8b69a389df1cad77337abf90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511788"
---
# <a name="compiler-error-c2206"></a>コンパイラ エラー C2206

'function': typedef は関数の型を定義するためには使えません。

関数型を定義するには、 `typedef` を使用します。

次の例では C2206 が生成されます。

```
// C2206.cpp
typedef int functyp();
typedef int MyInt;
functyp func1 {};   // C2206
int main() {
   MyInt i = 0;   // OK
}
```