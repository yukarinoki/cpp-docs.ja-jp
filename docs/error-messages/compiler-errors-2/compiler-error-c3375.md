---
title: コンパイラ エラー C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: b3dfc17f9df495fe6907b816bace0dac1eff08cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545276"
---
# <a name="compiler-error-c3375"></a>コンパイラ エラー C3375

'function': あいまいなデリゲート関数です

デリゲートのインスタンス化が静的メンバー関数向けであるか、またはインスタンス関数へのバインドされていないデリゲートとして存在した可能性があるため、コンパイラはこのエラーを発行しました。

詳細については、次を参照してください。[デリゲート (C++ コンポーネント拡張)](../../windows/delegate-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では警告 C3375 が生成されます。

```
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