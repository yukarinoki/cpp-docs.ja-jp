---
description: 詳細については、「コンパイラエラー C2120」を参照してください。
title: コンパイラ エラー C2120
ms.date: 11/04/2016
f1_keywords:
- C2120
helpviewer_keywords:
- C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
ms.openlocfilehash: 064c0587275d85c3cff520075352825d17d41aef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170058"
---
# <a name="compiler-error-c2120"></a>コンパイラ エラー C2120

' void ' はすべての型で無効です

型は、 **`void`** 別の型の宣言で使用されています。

次の例では、C2120 が生成されます。

```cpp
// C2120.cpp
int main() {
   void int i;   // C2120
   int j;   // OK
}
```
