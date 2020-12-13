---
description: 詳細については、「コンパイラエラー C2392」を参照してください。
title: コンパイラ エラー C2392
ms.date: 11/04/2016
f1_keywords:
- C2392
helpviewer_keywords:
- C2392
ms.assetid: 98ced473-6383-46ed-b79c-21857d65dcb2
ms.openlocfilehash: 0a367ed1416b28bb27fc5d79d4a474de219e48e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337561"
---
# <a name="compiler-error-c2392"></a>コンパイラ エラー C2392

' method1 ': 共変の型は、マネージ型または WinRTtypes ではサポートされていません。それ以外の場合、' method2 ' はオーバーライドされます

Windows ランタイムメンバー関数の場合、または [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) オプションを使用してコンパイルする場合、共変の戻り値の型は使用できません。

## <a name="example"></a>例

次の例では、C2392 を生成し、その修正方法を示しています。

```cpp
// C2392.cpp
// compile with: /clr
public ref struct B {
public:
   int i;
};

public ref struct D: public B{};

public ref struct B1 {
public:
   virtual B^ mf() {
      B^ pB = gcnew B;
      pB->i = 11;
      return pB;
   }
};

public ref struct D1: public B1 {
public:
   virtual D^ mf() override {  // C2392
   // try the following line instead
   // virtual B^ mf() override {
   // return type D^ is covariant with B^, not allowed with CLR types
      D^ pD = gcnew D;
      pD->i = 12;
      return pD;
   }
};

int main() {
   B1^ pB1 = gcnew D1;
   B^ pB = pB1->mf();
   D^ pD = dynamic_cast<D^>(pB);
}
```
