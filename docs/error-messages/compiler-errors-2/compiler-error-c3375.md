---
title: コンパイラ エラー C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: ba1dbf08fb56364d2ab5b8c40847ab89484dc005
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781394"
---
# <a name="compiler-error-c3375"></a>コンパイラ エラー C3375

'function': あいまいなデリゲート関数です

デリゲートのインスタンス化が静的メンバー関数向けであるか、またはインスタンス関数へのバインドされていないデリゲートとして存在した可能性があるため、コンパイラはこのエラーを発行しました。

詳細については、[デリゲート (C++ コンポーネント拡張)](../../extensions/delegate-cpp-component-extensions.md)を参照してください。

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