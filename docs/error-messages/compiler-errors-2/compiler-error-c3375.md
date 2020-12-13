---
description: 詳細については、「コンパイラエラー C3375」を参照してください。
title: コンパイラ エラー C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: d2a9e9904185877e730096d08cb1f7c23c35c0d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335006"
---
# <a name="compiler-error-c3375"></a>コンパイラ エラー C3375

'function': あいまいなデリゲート関数です

デリゲートのインスタンス化が静的メンバー関数向けであるか、またはインスタンス関数へのバインドされていないデリゲートとして存在した可能性があるため、コンパイラはこのエラーを発行しました。

詳細については、「 [delegate (C++ コンポーネント拡張)](../../extensions/delegate-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では警告 C3375 が生成されます。

```cpp
// C3375.cpp
// compile with: /clr
ref struct R {
   static void f(R^) {}
   void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::f);   // C3375
}
```
