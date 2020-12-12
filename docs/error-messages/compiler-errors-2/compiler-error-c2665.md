---
description: 詳細については、「コンパイラエラー C2665」を参照してください。
title: コンパイラエラー C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 784fe5ef0f24cd9e5fba99465d46f378b2b517fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210804"
---
# <a name="compiler-error-c2665"></a>コンパイラエラー C2665

' function ': number1 オーバーロードは、パラメーター number2 を型 ' type ' から変換できません

オーバーロードされた関数のパラメーターは、必要な型に変換できません。  考えられる解決策は次のとおりです。

- 変換演算子を指定します。

- 明示的な変換を使用します。

## <a name="example"></a>例

次の例では、C2665 が生成されます。

```cpp
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```
