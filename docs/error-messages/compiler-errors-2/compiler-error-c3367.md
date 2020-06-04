---
title: コンパイラ エラー C3367
ms.date: 11/04/2016
f1_keywords:
- C3367
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
ms.openlocfilehash: bedc94039f8621a93672c0dfa0cad5a54aad796e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201163"
---
# <a name="compiler-error-c3367"></a>コンパイラ エラー C3367

'static_member_function': バインドされていないデリゲートを作成するために静的関数を使用することはできません

バインドされていないデリゲートを呼び出す場合は、オブジェクトのインスタンスを渡す必要があります。 静的メンバー関数はクラス名によって呼び出されるので、バインドされていないデリゲートは、インスタンス メンバー関数でのみインスタンス化できます。

バインドされていないデリゲートの詳細については、「[方法C++: デリゲートを定義および使用する (/cli)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では C3367 が生成されます。

```cpp
// C3367.cpp
// compile with: /clr
ref struct R {
   void b() {}
   static void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::b);   // OK
   Del ^ b = gcnew Del(&R::f);   // C3367
}
```
