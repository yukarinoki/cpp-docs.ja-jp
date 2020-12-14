---
description: 詳細については、「コンパイラエラー C2781」を参照してください。
title: コンパイラエラー C2781
ms.date: 11/04/2016
f1_keywords:
- C2781
helpviewer_keywords:
- C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
ms.openlocfilehash: 9d99353b808494b20007784dd6016097afc783d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298007"
---
# <a name="compiler-error-c2781"></a>コンパイラエラー C2781

' 宣言 ': 少なくとも value1 の引数が必要です-value2 が指定されています

変数パラメーターリストを含む関数テンプレートの引数が少なすぎます。

次の例では、C2781 が生成されます。

```cpp
// C2781.cpp
template<typename T>
void f(T, T, ...){}

int main() {
   f(1);   // C2781

   // try the following line instead
   f(1,1);
}
```
