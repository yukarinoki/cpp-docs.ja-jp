---
description: 詳細については、「コンパイラエラー C3892」を参照してください。
title: コンパイラ エラー C3892
ms.date: 11/04/2016
f1_keywords:
- C3892
helpviewer_keywords:
- C3892
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
ms.openlocfilehash: 1fe2692e594debebdaf3493414d0e6136c9403a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274269"
---
# <a name="compiler-error-c3892"></a>コンパイラ エラー C3892

' var ': const である変数に割り当てることはできません。

Const 変数は、宣言して初期化した後に変更することはできません。

次の例では、C3892 が生成されます。

```cpp
// C3892.cpp
// compile with: /clr
ref struct Y1 {
   static const int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3892
}
```
