---
description: 詳細については、「コンパイラエラー C2896」を参照してください。
title: コンパイラ エラー C2896
ms.date: 11/04/2016
f1_keywords:
- C2896
helpviewer_keywords:
- C2896
ms.assetid: b600407b-cb05-42e3-9069-2aa6960f0eaa
ms.openlocfilehash: 096650ab4ced95ace9bbf51680339ba0258eff45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270902"
---
# <a name="compiler-error-c2896"></a>コンパイラ エラー C2896

' function1 ': 関数テンプレート ' function2 ' を引数として使用することはできません

関数テンプレートに別の関数テンプレートへの引数を指定することはできません。

次の例では、C2896 が生成されます。

```cpp
// C2896.cpp
template<class T1, class T2> void f1(void(*)(T1, T2));
template<class T1, class T2> void f2(T1, T2);

int main() {
   f1(f2);   // C2896
}
```

C2896 は、ジェネリックを使用する場合にも発生する可能性があります。

```cpp
// C2896b.cpp
// compile with: /clr
generic<class T1> void gf1(T1){}
generic<class T1> void gf2(T1){}

int main() {
   gf1(gf2);   // C2896
   gf1(1);   // OK
}
```
