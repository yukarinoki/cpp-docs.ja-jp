---
title: コンパイラ エラー C2228
ms.date: 11/04/2016
f1_keywords:
- C2228
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
ms.openlocfilehash: 20e295d09e39a12ed8163ec980fa304cd4167218
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404339"
---
# <a name="compiler-error-c2228"></a>コンパイラ エラー C2228

'.identifier' の左側はクラス、構造体、共用体でなければなりません

ピリオド (.) の左側のオペランドがクラス、構造体または共用体。

次の例では C2228 が生成されます。

```
// C2228.cpp
int i;
struct S {
public:
    int member;
} s, *ps = &s;

int main() {
   i.member = 0;   // C2228 i is not a class type
   ps.member = 0;  // C2228 ps is a pointer to a structure

   s.member = 0;   // s is a structure type
   ps->member = 0; // ps points to a structure S
}
```

マネージド拡張を使用する際に、間違った構文を使用した場合も、このエラーが表示されます。 他の Visual Studio の言語ではドット演算子を使用してマネージド クラスのメンバーにアクセスできますが、C++ でのオブジェクトへのポインターは、-&gt; 演算子を使用してメンバーにアクセスする必要があることを意味します。

誤: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`

正: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`