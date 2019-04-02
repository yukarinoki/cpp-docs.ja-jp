---
title: コンパイラ エラー C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: d076dabe0df91cefb90be5ec9e90f371331a51f1
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771008"
---
# <a name="compiler-error-c3288"></a>コンパイラ エラー C3288

'type': 無効なハンドル型の逆参照

ハンドル型の無効なを逆参照が検出されました。 ハンドル型を逆参照し、参照に割り当てることができます。 詳細については、次を参照してください。[参照演算子の追跡](../../extensions/tracking-reference-operator-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3288 が生成されます。

```
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