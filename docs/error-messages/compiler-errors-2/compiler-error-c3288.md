---
description: 詳細については、「コンパイラエラー C3288」を参照してください。
title: コンパイラ エラー C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: 6a9de812a981909c9de3a3bb895294ea9b6968d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144821"
---
# <a name="compiler-error-c3288"></a>コンパイラ エラー C3288

' type ': ハンドル型の無効な逆参照です

ハンドル型の無効な逆参照が検出されました。 ハンドル型を逆参照して、参照に割り当てることができます。 詳細については、「 [参照演算子の追跡](../../extensions/tracking-reference-operator-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3288 が生成されます。

```cpp
// C3288.cpp
// compile with: /clr
ref class R {};
int main() {
   *(System::Object^) nullptr;   // C3288

// OK
   (System::Object^) nullptr;   // OK
   R^ r;
   R% pr = *r;
}
```
