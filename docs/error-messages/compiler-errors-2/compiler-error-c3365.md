---
title: コンパイラ エラー C3365
ms.date: 11/04/2016
f1_keywords:
- C3365
helpviewer_keywords:
- C3365
ms.assetid: 875ec3a4-522c-4e3d-9b67-48808b857f6d
ms.openlocfilehash: 355c4530fffa89470ac495aff8bc2822278e2da3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201196"
---
# <a name="compiler-error-c3365"></a>コンパイラ エラー C3365

演算子 'operator': 型 'type1' および 'type2' の異なるオペランドです

異なる型のデリゲートを作成しようとしました。  デリゲートの詳細については[、「C++方法: デリゲートを定義および使用する (/cli)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3365 が生成されます。

```cpp
// C3365.cpp
// compile with: /clr
delegate void D1();
delegate void D2(int);

ref class R {
public:
   void f(){}
   void g(int){}
};

int main() {
   D1^ d1 = gcnew D1(gcnew R, &R::f);
   D2^ d2 = gcnew D2(gcnew R, &R::g);
   D1^ d3 = gcnew D1(gcnew R, &R::f);

   d1 += d2;   // C3365
   d1 += d3;   // OK
   d1();
}
```
