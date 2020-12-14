---
description: 詳細については、「コンパイラエラー C2530」を参照してください。
title: コンパイラ エラー C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 07980fb6d87b4e84bc0b253ccd317eba02fa81af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258110"
---
# <a name="compiler-error-c2530"></a>コンパイラ エラー C2530

' identifier ': 参照を初期化する必要があります

宣言されている場合を除き、参照を初期化する必要があります。

- キーワード [extern](../../cpp/extern-cpp.md)を使用します。

- クラス、構造体、または共用体のメンバーとして (およびコンストラクターで初期化されます)。

- 関数の宣言または定義のパラメーターとして。

- 関数の戻り値の型として。

次の例では、C2530 が生成されます。

```cpp
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```
