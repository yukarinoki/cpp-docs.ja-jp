---
title: コンパイラ エラー C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 2c8164cad25d68ee61ff9fed7170482d5dfc9505
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474790"
---
# <a name="compiler-error-c2530"></a>コンパイラ エラー C2530

'identifier': 参照を初期化する必要があります

既に宣言されていない限り、宣言されているときに、参照を初期化する必要があります。

- キーワードを使用して[extern](../../cpp/using-extern-to-specify-linkage.md)します。

- クラス、構造体、共用体のメンバーとして (およびコンス トラクターで初期化されます)。

- 関数宣言または定義でパラメーター。

- 関数の戻り値の型。

次の例では、C2530 が生成されます。

```
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```